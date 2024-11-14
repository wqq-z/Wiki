
---
title: 干扰的 Windows 安全功能
---

# 禁用某些 Windows 安全功能

默认情况下，Windows 启用了多种旨在保护内核免受篡改的功能。  
我强烈建议保持这些功能开启，但要使 Valthrun 正常运行，需要禁用一些功能。  
- 核心隔离
- MSFT 驱动阻止列表
- 基于虚拟化的安全
- 禁用虚拟机管理程序

## 禁用核心隔离
详情请访问：  
https://support.microsoft.com/en-us/windows/a-driver-can-t-load-on-this-device-8eea34e5-ff4b-16ec-870d-61a4a43b3dd5

简要说明：Windows 安全中心/Defender > 设备安全 > 核心隔离详情 > 关闭内存完整性

TODO：为什么？

## MSFT 驱动阻止列表 & Microsoft 易受攻击驱动阻止列表
KDMapper 输出：`NTSTATUS (0xC0000428): Windows 无法验证该文件的数字签名`  
https://www.thewindowsclub.com/microsoft-vulnerable-driver-blocklist-in-windows  
https://community.amd.com/t5/drivers-software/amd-driver-problem/m-p/474646#M144661

简要说明：Windows 安全中心/Defender > 设备安全 > 核心隔离详情 > 关闭 Microsoft 易受攻击驱动阻止列表

注意：您需要在此操作后重新启动电脑。  
TODO：为什么？

## 基于虚拟化的安全
https://www.makeuseof.com/windows-11-disable-vbs/

TODO：为什么？

## 禁用虚拟机管理程序
以管理员身份在 cmd 中运行：
```bcdedit /set hypervisorlaunchtype off
```然后重新启动您的计算机。
