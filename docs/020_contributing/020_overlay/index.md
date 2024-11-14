---
title: CS2 覆盖层
---

# 构建 Valthrun CS2 覆盖层

## 前置要求

Valthrun 需要 [Rust](https://www.rust-lang.org/learn/get-started) 工具链进行编译。

:::warning
由于 Valthrun 使用了 Rust 的 nightly 功能，因此您必须先切换到 Rust nightly 版本。  
可以通过以下命令切换到 Rust nightly 编译器：
ps1
rustup default nightly

```:::

## 构建覆盖层
ps1
# 初始化所有子模块
git submodule update --init

# 创建 release 版本的覆盖层构建
# 结果将位于 "target/release/controller"
cargo build --release
```

#### 注意

在 https://github.com/rust-lang/rust/issues/111540 尚未完成之前，  
构建的 controller 文件将包含 `valthrun` 以及工作空间路径在最终可执行文件中。  
据我所知，VAC 并不会主动检查特定的字符串，因此这不应该是一个问题。  
但如果您仍然希望移除这些痕迹，您可以相应地设置 RUSTFLAGS 重映射路径前缀标志。
ps1
$WorkspaceCargo=$(cargo locate-project --workspace --message-format=plain)
$env:RUSTFLAGS="-Ctarget-feature=+crt-static -Clink-arg=/PDBALTPATH:C:\build\application.pdb --remap-path-prefix=$($WorkspaceCargo.TrimEnd("Cargo.toml"))=[src] --remap-path-prefix=$env:CARGO_HOME\registry\src\=[crates.io]"
```之后重新构建覆盖层，最终二进制文件中应只包含 `valthrun`而非构建路径（其中可能包含`valthrun` 字样）。
