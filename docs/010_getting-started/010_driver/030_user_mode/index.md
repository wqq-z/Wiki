---
title: 用户模式驱动
---

# Valthrun 用户模式驱动

:::danger
此驱动仅用于开发目的。  
除非您清楚自己在做什么，否则请勿使用此驱动。
:::

Valthrun 用户模式驱动是一种内存驱动实现，利用 `NtReadVirtualMemory` 和 `NtWriteVirtualMemory` 函数来读取和写入其他进程的内存。与 Valthrun 驱动套件中的其他驱动相比，此驱动无需特殊设置或加载方法，提供了一种更为简便的内存操作方法。

然而，需要注意的是，Valthrun 用户模式驱动仅适用于开发用途或未受保护的进程，因为它不具备内核驱动或 Zenith 驱动相同的安全性或隐蔽性。有关更多实现细节，请参阅代码：[Valthrun 用户模式驱动实现](https://github.com/Valthrun/Valthrun/blob/master/kernel/um-driver-impl)。

## 设置用户模式驱动

由于 Valthrun 用户模式驱动的唯一用途是开发，因此并不进行分发。建议用户自行编译驱动并参考源码以获取进一步的实现细节，源码可以在[这里](https://github.com/Valthrun/Valthrun/blob/master/kernel/um-driver-impl)找到。
