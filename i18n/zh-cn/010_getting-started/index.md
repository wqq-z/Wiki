
---
title: 入门指南
---

# 如何使用 Valthrun

要使用 Valthrun 提供的各种游戏增强功能，您需要按照几个步骤来设置所有必要的组件。  
以下步骤将逐一指导您如何使用 Valthrun。

## 必需组件

在使用 Valthrun 之前，您必须获取两个基本组件：

1. **Valthrun 驱动**  
   Valthrun 驱动是 Valthrun 的核心部分。  
   它支持对 Counter-Strike 2 进程的隐蔽任意读取操作，并防止其他软件（如 VAC）检测到这些操作。可用驱动的列表以及如何选择适合的驱动的详细说明，请参见[驱动部分](./driver)。

2. **所需的游戏增强器**  
   Valthrun 提供了多种不同的游戏增强功能。  
   增强功能的列表可以在[应用程序部分](./applications/)找到。

您可以在 [Valthrun 官网](https://valth.run/)下载上述组件的最新版本。

## CS2 游戏内覆盖的快速指南

在获取了必要的文件后，请按照以下步骤运行 Valthrun 覆盖层：
:::tip
懒得手动执行所有这些步骤？
使用 [@valthrunner](https://github.com/valthrunner) 提供的 Valthrunner 脚本一键自动化！  
只需点击一下即可更新 Valthrun、映射驱动、自动启动 CS2 并运行 Valthrun！
更多信息请查看：[Valthrunner 的脚本](./community_script_valthrunner)
:::
:::note
如果您在此快速设置指南中遇到任何问题，请参阅该特定步骤的更详细文档。
:::

1. **设置 Valthrun 驱动**  
   Valthrun 驱动是 Valthrun 的核心。  
   它使得在 Counter-Strike 2 进程上进行不被检测的任意读取操作成为可能，并防止其他软件（如 VAC）的检测。
   有多种方法可以加载内核驱动。如何加载内核驱动的说明记录在[这里](./driver/)。

2. **下载最新的 CS2 游戏内覆盖版本**  
   从 GitHub 下载最新的 CS2 游戏内覆盖：  
   https://github.com/Valthrun/Valthrun/releases/tag/latest  
   文件名为 `controller.exe`。
   :::warning
   确保将 `controller.exe` 放在与驱动接口 `.dll` 文件相同的文件夹中。  
   （例如 `driver.dll`、`driver-zenith.dll` 或 `driver-kernel.dll`）
   :::

3. **确保 Counter-Strike 2 已启动**  
   在启动 Valthrun 覆盖层之前，确保 Counter-Strike 2 (CS2) 已在运行。  
   如果 CS2 尚未运行，请启动游戏，否则控制器将无法运行。

4. **启动覆盖层（`controller.exe`）**  
   当内核驱动成功加载且 CS2 正在运行时，您可以通过运行 `controller.exe` 来启动 Valthrun 覆盖层。  
   如果一切设置正确，您应该会看到一个终端窗口。

以下是覆盖层界面的示例：
![成功截图](@site/docs/_media/screenshot_controller_success.png)

完成这些步骤后，您就可以使用 Valthrun 并享受其为 Counter-Strike 2 提供的游戏增强功能了。  
请务必参考项目的文档和支持资源，以获取关于功能和使用的更多详细信息。
