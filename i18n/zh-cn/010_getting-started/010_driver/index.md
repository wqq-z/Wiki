
---
title: Valthrun 驱动
---

# Valthrun 驱动

为了使用户模式应用（例如 [Valthrun CS2 覆盖层](../applications/cs2_overlay) 或 [Valthrun CS2 Web 雷达](../applications/cs2_radar_standalone)）能够访问其他进程的内存，系统需要一个驱动程序。Valthrun 套件提供了多种此类驱动实现，适应目标进程的不同情况和需求。每种实现都设计用于处理特定场景，以确保根据目标进程的安全性和保护措施实现最佳性能和兼容性。

虽然 Valthrun 提供了多种驱动程序，但您只需加载其中一个即可。  
目前最便捷的选择是使用 [Valthrun 内核驱动](./kernel/)。
