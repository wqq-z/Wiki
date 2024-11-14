---
title: Zenith 驱动
---

# Valthrun Zenith 驱动

:::note
Valthrun Zenith 驱动正在开发中，目前尚未公开发布。  
加入 [Valthrun Discord](/general/discord) 并关注更新。
:::

Valthrun Zenith 驱动设计用于读取和写入任意物理或虚拟内存。该实现对 Windows 操作系统完全透明，通过劫持 Windows 的虚拟化基础安全 (VBS) 功能，从而绕过常规的操作系统级别检测机制。

## 初始 Zenith 驱动设置

要加载 Valthrun Zenith 驱动，用户必须使用 Valthrun Zenith UEFI 加载器创建一个可引导的 USB 闪存盘。该 USB 闪存盘预装了 Valthrun Zenith 安装程序，作为引导介质来初始化驱动。请按照以下步骤创建引导介质：

:::warning
此部分的文档尚未完成。  
请关注后续更新。
:::

## 系统启动/重启时加载 Zenith 驱动

Valthrun Zenith 驱动在系统关闭时会被卸载。要重新加载它，请在启动时通过 Valthrun Zenith UEFI 加载器引导系统。您可以在每次启动时手动选择 Valthrun Zenith EFI 加载器，或调整系统的启动顺序，使 USB 加载器具有优先级，从而在每次启动时自动加载 Zenith 驱动。
