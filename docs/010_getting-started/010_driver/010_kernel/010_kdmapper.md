---
title: KDMapper
---

# 使用 KDMapper 加载 Valthrun 内核驱动

## 什么是 KDMapper

[KDMapper](https://github.com/TheCruZ/kdmapper) 是推荐用于手动加载 Valthrun 内核驱动到内存中的工具。  
这个简单的工具利用了 `iqvw64e.sys` 英特尔驱动程序来映射未签名的驱动程序，使您能够加载包括 Valthrun 内核驱动在内的任何驱动程序。

## 映射 Valthrun 内核驱动

按照以下步骤使用 KDMapper 映射 Valthrun 内核驱动：

1. **获取 KDMapper**  
   在使用 KDMapper 之前，您需要一个可用的 KDMapper 可执行文件。  
   官方的 KDMapper 仓库不提供下载链接，因此您有两种选择：

   - **自行编译（推荐）**  
     为了更高的安全性和可信度，建议您自行编译 KDMapper。  
     在官方 [KDMapper 仓库](https://github.com/TheCruZ/kdmapper) 中可以找到详细的编译说明。  
     自行编译可以确保您对源代码的控制，并可以验证其完整性。

   - **下载预编译版本**  
     您也可以在[此处](https://github.com/valthrunner/Valthrun/releases/latest)找到 KDMapper 的预编译版本。  
     请注意，此预编译版本**并非由 Valtrun 提供**，而是由用户 @valthrunner 编译并上传的。  
     下载预编译软件时，请保持谨慎并确保您信任该来源。

2. **以管理员身份打开命令行**  
   为了成功使用 KDMapper，请以管理员权限打开命令行。  
   您可以右键点击命令提示符或 PowerShell 并选择 "以管理员身份运行"。

3. **导航到 Valthrun 目录**  
   在使用 KDMapper 加载 Valthrun 内核驱动之前，请确保您位于正确的目录中，即包含 kdmapper.exe 和 valthrun-driver.sys 的目录。  
   使用 `cd` 命令导航到该目录，以确保 KDMapper 能够访问加载驱动程序所需的组件。

4. **使用 KDMapper 加载 `valthrun-driver.sys`**  
   要将 Valthrun 内核驱动加载到内存中，请在命令提示符或 PowerShell 中执行以下命令：
   bash
   kdmapper.exe valthrun-driver.sys

如果一切操作正确，输出应类似如下内容：

```[<] Loading vulnerable driver, Name: SaBVbLkOxDxwTNNOsSPnmMW
[+] NtLoadDriver Status 0x0
[-] Can't find pattern
[+] PiDDBLock found with second pattern
[+] PiDDBLock Ptr 0xfffff80130674912
[+] PiDDBCacheTable Ptr 0xfffff80130568508
[+] PiDDBLock Locked
[+] Found Table Entry = 0xFFFFAC0ED06F4C40
[+] PiDDBCacheTable Cleaned
[+] g_KernelHashBucketList Found 0xFFFFF8013222C088
[+] g_HashCacheLock Locked
[!] g_KernelHashBucketList looks empty!
[+] MmUnloadedDrivers Cleaned: SaBVbLkOxDxwTNNOsSPnmMW
[+] Image base has been allocated at 0xFFFFD0876A42E000
[+] Skipped 0x1000 bytes of PE Header
[<] Calling DriverEntry 0xFFFFD0876A433B10
[+] Callback example called
[+] DriverEntry returned 0x0
[<] Unloading vulnerable driver
[+] NtUnloadDriver Status 0x0
[+] Vul driver data destroyed before unlink
[+] success
```

确保输出中包含 `[+] DriverEntry returned 0x0` 这一行。  
如果出现该行，则表示 Valthrun 内核驱动加载成功。  
然而，如果**输出中未包含此行**，则表示**映射过程失败**。  
在这种情况下，请参阅故障排除部分，以获取解决问题的指南。

## 故障排除

有关如何解决常见 KDMapper 错误的信息，请参阅[此处](../../../troubleshooting/kernel/driver_mapper_errors)。

## 优点 / 缺点

<h2>优点</h2>
使用 KDMapper 是一个相对简单的过程。  
KDMapper 相当可靠，并且不需要反复试验。  
  
<h2>缺点</h2>
使用 KDMapper 有两个主要缺点。
