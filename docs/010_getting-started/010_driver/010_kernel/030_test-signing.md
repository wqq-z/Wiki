---
title: Windows 测试签名
---

# 使用 Windows 测试签名模式加载 Valthrun 内核驱动

## 什么是 Windows 测试签名

Windows 测试签名是一种 Windows 操作系统的模式，允许用户加载和测试未经过微软数字签名的驱动程序。在正常情况下，Windows 要求驱动程序必须经过数字签名，以确保其真实性和完整性。测试签名模式放宽了这一要求，使得自签名的驱动程序可以被加载。

## 如何启用 Windows 测试签名模式

要在 Windows 中启用测试签名模式，请按照以下步骤进行：

1. **打开提升权限的命令提示符**  
   右键单击开始按钮，选择“命令提示符 (管理员)”或“Windows PowerShell (管理员)”，以管理员权限打开命令提示符窗口。

2. **启用测试签名模式**  
   在命令提示符窗口中，输入以下命令并按 Enter 键：

   cmd
   bcdedit /set testsigning on

3. **重启计算机**  
   输入完命令后，您需要重新启动计算机以使更改生效。  
   您可以通过输入以下命令并按 Enter 来重启：

   cmd
   shutdown /r /t 0

4. **验证测试签名模式**  
   计算机重启后，Windows 应处于测试签名模式。  
   您可以通过查看桌面右下角是否显示“测试模式”水印来验证。  
   如果您在桌面右下角看到“Test Mode”的水印，则表示测试签名模式已启用。

## 加载 Valthrun 内核驱动

要加载 Valthrun 内核驱动，请执行以下步骤：

1. **打开提升权限的命令提示符**  
   右键单击开始按钮，选择“命令提示符 (管理员)”或“Windows PowerShell (管理员)”，以管理员权限打开命令提示符窗口。

2. **注册并启动 Valthrun 内核驱动**  
   在命令提示符窗口中，输入以下命令并按 Enter 键：

   cmd
   sc create valthrun type= kernel binpath="C:\Users...\valthrun-driver.sys"
   sc start valthrun
