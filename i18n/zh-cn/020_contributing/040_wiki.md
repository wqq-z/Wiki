
---
title: 维基
---

# 贡献到维基

为维基贡献是一个简单的过程，允许个人协作扩展和增强知识库。  
该维基使用 [Docusaurus](https://docusaurus.io) 构建，并存储在 [Valthrun 维基仓库](https://github.com/Valthrun/wiki)中。  
所有维基内容都位于 `docs` 文件夹内，内容文件通常使用 Markdown 编写，便于编辑。

## 添加新页面

要通过添加新页面来贡献到维基，请按照以下步骤操作：

1. 将 Valthrun 维基仓库克隆到本地。
2. 在 `docs` 文件夹中，创建一个新的 Markdown 文件（`.md`），并添加您新页面的内容。

## 预览更改

在最终提交之前，您可以通过以下步骤预览对维基页面所做的更改：

1. 安装 yarn
   bash
   npm i yarn -g
   

2. 安装项目依赖
   bash
   yarn install
   

3. 启动项目的开发模式
   bash
   yarn start
   
   
   :::note
   如果要进行翻译工作，启动项目时必须指定语言：
   bash
   # yarn start --locale <语言代码>
   yarn start --locale zh-cn
   
   :::

Docusaurus 将提供一个 URL，您可以在浏览器中打开该链接。  
对内容文件的任何更改将立即反映在实时预览页面上，  
让您可以查看编辑内容将如何展示给用户。

此实时预览功能提供了一种便捷的方法，让您可以在发布之前审查您的贡献，确保内容准确且格式良好。

## 更多关于 Docusaurus 的信息

有关 Docusaurus 及其功能的更多信息，请参阅官方 Docusaurus 文档：[Docusaurus 文档](https://docusaurus.io/docs/docs-introduction)。  
该资源提供了关于如何有效使用 Docusaurus 构建和维护维基及其他文档项目的详细信息和技巧。
