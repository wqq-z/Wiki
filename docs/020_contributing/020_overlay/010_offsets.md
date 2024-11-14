---
title: 更新（过期的）偏移量
---

# 更新偏移量

## 什么是偏移量

在计算机科学中，偏移量是一个整数，表示一个对象（例如数组或其他数据结构）中从对象的起始位置到特定元素或点的距离（位移）[^3]。  
Valthrun 广泛使用偏移量来从不同的 CS2 结构中提取数据，以增强您的游戏体验。

由于添加、重新排序或删除[变量](<https://en.wikipedia.org/wiki/Variable_(computer_science)>)会导致这些偏移量发生变化，因此每次 CS2 更新都会导致偏移量发生轻微变化。  
因此，Valthrun 控制器也需要随之更新[^2]。

## 偏移量的使用和 CS2 的 schema 系统

CS2 拥有一个便捷的系统，可以检索服务器和客户端之间共享变量的所有偏移量。  
这些变量以前被称为 `netvars`，现在称为 schema 变量。

大多数用于游戏增强的信息都可以通过检索这些共享变量来获得。因此，大多数情况下，仅更新这些偏移量就足够了。

在某些情况下，需要访问本地客户端数据，例如玩家的骨骼状态。  
为了解析这些偏移量，Valthrun 主要依赖于[模式扫描](https://www.unknowncheats.me/forum/general-programming-and-reversing/133228-implement-pattern-scanning-obtain-offsets-dynamically.html)。  
尽管模式扫描在跨多个版本解析偏移量方面相当可靠，但模式可能会失效并需要更新，有时创建模式也可能不可行[^1]。

因此，一些偏移量是[硬编码的](https://en.wikipedia.org/wiki/Hard_coding)。  
这些硬编码的偏移量大多不太可能发生变化，但如果它们发生变化，则必须手动更新。

经验法则：  
硬编码的偏移量通常不会随更新而改变。  
可能随更新而改变的偏移量要么通过 schema 系统检索，要么通过模式扫描检索。

## 更新基于 schema 的偏移量

大多数容易变化的偏移量可以通过使用 CS2 schema 系统来检索。  
基于该系统提供的信息，我们可以自动生成所有类和函数定义。  
包含所有这些定义的源码可以在[这里](https://github.com/WolverinDEV/Valthrun/blob/master/cs2-schema/generated/cs2_schema.json)找到。更新此文件相当简单：

1. 导出当前 CS2 schema  
   将当前 schema 导出到 "cs2_schema.json"。

   注意：  
   这需要游戏正在运行且内核驱动已加载！
   ps
   .\controller.exe dump-schema --all-classes cs2_schema.json

2. 更新 `cs2_schema.json`  
   将 `cs2-schema/generated/cs2_schema.json` 中的 `cs2_schema.json` 替换为新导出的 schema。

3. 重新编译控制器  
   按照[这里](../overlay/)的说明重新编译控制器。

大多数情况下，您应该可以正常使用并为 CS2 的下一个更新做好准备。  
如果 Valthrun 仍然表现异常或生成错误，这可能表明某些硬编码的偏移量发生了变化。  
如果是这种情况，您可以尝试追踪问题（通过分析和调试源代码）并解析新的偏移量，或者等待其他人来解决这个问题 :)  
（PS：您可以请他喝杯咖啡 :P）

[^1]: 或者是开发者当时太懒，没有实现模式匹配……
[^2]:
    内核驱动仅提供基本的内存读取功能，不需要了解目标应用程序的任何信息。  
    因此，CS2 更新*永远不会*影响内核驱动。

[^3]: Offset (computer*science)（[Wikipedia](https://en.wikipedia.org/wiki/Offset*(computer_science))）
