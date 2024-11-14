---
title: CS2 网页雷达
---

# 开发 / 构建雷达

## 前置要求

Valthrun 需要 [Rust](https://www.rust-lang.org/learn/get-started) 工具链进行编译。

:::warning
由于 Valthrun 使用了 Rust 的 nightly 功能，因此您必须先切换到 Rust nightly 版本。  
可以通过以下命令切换到 Rust nightly 编译器：
ps1
rustup default nightly

```:::

## 设置开发环境
:::note
此步骤仅适用于开发环境。
Valthrun 仓库包含了所有发布所需的文件（例如服务器、独立客户端和 HTML 文件）。
:::

要使用雷达功能，您需要执行以下步骤：

1. 启动 pub/sub 服务器：

   cd radar\server-standalone
   cargo r


2. 启动独立雷达客户端（CS2 需要处于开启状态）

   cd radar\client-standalone
   cargo r -- -p ws://127.0.0.1:7229/publish


3. 通过 webpack-dev-server 启动网页

   cd radar\web
   $env:SERVER_URL="ws://127.0.0.1:7229/subscribe"
   $env:NODE_ENV="development"
   yarn start:dev


## 构建雷达
1. 构建 pub/sub 服务器

   cargo build --release radar-server-standalone

   结果将位于 `target/release/radar-server-standalone.exe`

2. 构建雷达客户端

   cargo build --release radar-client-standalone

   结果将位于 `target/release/radar-client-standalone.exe`

3. 构建网页脚本
   ps1
   cd radar\web

   # 注意：
   # 设置 SERVER_URL 为网页客户端应连接的 URL。
   # 本地 HTTP 设置可以使用 "ws://127.0.0.1:7229/subscribe"
   # 或者使用官方服务器 "wss://radar.valth.run/subscribe"
   $env:SERVER_URL="wss://example.com/subscribe"
   $env:NODE_ENV="development"

   yarn build

   结果将位于 `radar/web` 下的 `dist` 文件夹
```
