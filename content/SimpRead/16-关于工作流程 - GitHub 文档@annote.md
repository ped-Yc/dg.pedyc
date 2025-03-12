---
UID: 20250311115125
title: "srAnnote@关于工作流程 - GitHub 文档"
alias: ["srAnnote@关于工作流程 - GitHub 文档"]
type: Simpread
index: 16
---

# 关于工作流程 - GitHub 文档

> [!timeline]+ 简介
>> **元数据**
>---
> **原文**:: [关于工作流程 - GitHub 文档](https://docs.github.com/zh/actions/writing-workflows/about-workflows)
> **日期**:: [[2025-03-11]]
> **标签**:: #SimpRead 
>> **摘要**
>---
> 获取 GitHub Actions 工作流的简要概述，包括触发器、语法和高级功能。

## 笔记

> [!abstract]+ <mark style="background-color: #ffeb3b">Highlight</mark> [🧷](<http://localhost:7026/reading/16#id=1741665096541>)
> **工作流**是一个可配置的自动化过程，它将运行一个或多个作业。 工作流程由签入到存储库的 YAML 文件定义，并在存储库中的事件触发时运行，也可以手动触发，或按定义的时间表触发。
^sran-1741665096541

> [!abstract]+ <mark style="background-color: #ffeb3b">Highlight</mark> [🧷](<http://localhost:7026/reading/16#id=1741700866528>)
> 默认情况下，工作流程中的作业同时并行运行。 如果你有一个作业只能在另一个作业完成后运行，则可以使用 `needs` 关键字来创建此依赖项。 如果其中一个作业失败，则跳过所有从属作业；但如果需要作业继续运行，可以使用 `if` 条件语句来定义。
^sran-1741700866528

> [!abstract]+ <mark style="background-color: #ffeb3b">Highlight</mark> [🧷](<http://localhost:7026/reading/16#id=1741665788348>)
> 如果你的作业定期重用依赖项，你可以考虑缓存这些文件以帮助提高性能。 缓存一旦创建，就可用于同一仓库中的所有工作流程。
^sran-1741665788348


