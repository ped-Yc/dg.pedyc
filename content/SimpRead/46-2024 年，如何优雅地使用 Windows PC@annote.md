---
title: "2024 年，如何优雅地使用 Windows PC"
alias: 46-2024 年，如何优雅地使用 Windows PC@annote
uid: 
author: 
description: 
date-created: 2024-09-11 21:11
date-modified: 2024-09-13 11:31
type: Simpread
banner: "https://cdnfile.sspai.com/2024/07/07/28161ba4cc52fe55e81478cd2b9ad964.avif "
banner_icon: 🔖
created-date: 2024-09-10T23:58:38+0800
idx: 46
tag: []
tags: 
---

## 2024 年，如何优雅地使用 Windows PC

> [!example]- [🧷内部链接](<http://localhost:7026/unread/46>) [🌐外部链接](<>)
> URI:: [🧷](<http://localhost:7026/unread/46>) [🌐](<>)
> intURI:: [🧷内部链接](<http://localhost:7026/reading/46>)

%%

> [!example]+ **Comments**
>
> ```dataview
> TABLE 
>     WITHOUT ID
>     link(Source, dateformat(date(Source), "yyyy-MM-dd")) as Date___, 
>     regexreplace(rows.Comments,"^@@\[\[.+?\]\]\s","") as "Comments"
> FROM "journals"
> WHERE  contains(cmnt, this.file.name)
> FLATTEN cmnt as Comments
> WHERE contains(Comments, this.file.name)
> GROUP BY file.link as Source
> SORT rows.file.day desc
> ```
>  **Description**:: 工欲善其事，必先利其器。利用工具想做好一件事，首先要对工具本身足够了解掌握。充分利用计算机自身的特性，再加上保持良好的习惯，最终一定会从日积月累的行动中受益。
%%

> [!md] Metadata
> **标题**:: [2024 年，如何优雅地使用 Windows PC](https://sspai.com/post/90272)
> **日期**:: [[2024-09-10]]

### Annotations

> [!srhl2] [[SR46@2024 年，如何优雅地使用 Windows PC|📄]] <mark style="background-color: #ffeb3b">Highlights</mark> [🧷](<http://localhost:7026/unread/46#id=1725983984909>) [🌐](<#id=1725983984909>)
> 拿到一台新电脑或重装系统之后，不必急于安装软件，如果之前注册过微软账号，建议直接用这个账号登录系统。Edge 浏览器和 OneDrive 云盘会在后台自动同步旧电脑上的设置记录等文件数据，也等于为这一次的变动做好自动备份。
> ^sran-1725983984909

> [!srhl5] [[SR46@2024 年，如何优雅地使用 Windows PC|📄]] <mark style="background-color: #a8ea68">Highlights</mark> [🧷](<http://localhost:7026/unread/46#id=1725985144045>) [🌐](<#id=1725985144045>)
> - 任务栏：隐藏搜索按钮、任务视图按钮，小组件，聊天。
> - 开始菜单：隐藏最近添加的应用、常用应用。
> - 文件夹选项：设置首次开启显示为「此电脑」，显示文件扩展名。
>
> - 📝试一试哈
> ^sran-1725985144045

> [!srhl2] [[SR46@2024 年，如何优雅地使用 Windows PC|📄]] <mark style="background-color: #ffeb3b">Highlights</mark> [🧷](<http://localhost:7026/unread/46#id=1725984474636>) [🌐](<#id=1725984474636>)
> 长期使用电脑，你一定能够感受到，用键盘操作比用鼠标点来点去速度快得多。人生苦短，无论是系统还是软件中，多记几个快捷键，形成习惯后真的可以节约太多时间。
> ^sran-1725984474636

> [!srhl2] [[SR46@2024 年，如何优雅地使用 Windows PC|📄]] <mark style="background-color: #ffeb3b">Highlights</mark> [🧷](<http://localhost:7026/unread/46#id=1725984830468>) [🌐](<#id=1725984830468>)
> Windows 11 针对 Intel 12 代之后的 CPU 提供了许多高级电源设置选项，可以更好的平衡 CPU 的性能和功耗。但这些设置默认是隐藏的，根据 [这篇文章](https://sspai.com/link?target=https%3A%2F%2Fcn.windows-office.net%2F%3Fp%3D17342) 可以做更细致的调整。
> ^sran-1725984830468

> [!srhl2] [[SR46@2024 年，如何优雅地使用 Windows PC|📄]] <mark style="background-color: #ffeb3b">Highlights</mark> [🧷](<http://localhost:7026/unread/46#id=1725984898275>) [🌐](<#id=1725984898275>)
> 对于不经常使用或者对启动速度影响较大的应用，建议禁止其开机启动。可以在任务管理器（Ctrl + Alt + Del）的「启动」 选项卡中查看并管理开机启动项。在这里，你可以禁用或启用任何已安装的应用程序在开机时启动。禁用不必要的启动项可以提高系统的启动速度。
> ^sran-1725984898275

> [!srhl2] [[SR46@2024 年，如何优雅地使用 Windows PC|📄]] <mark style="background-color: #ffeb3b">Highlights</mark> [🧷](<http://localhost:7026/unread/46#id=1725984922696>) [🌐](<#id=1725984922696>)
> 很多「电脑管家」「垃圾清理大师」 之类的优化软件，正是抓住了人们的心理作用。仔细想想看，如果一台电脑由于存在「垃圾文件」 必然严重影响使用体验，已经属于设计缺陷了，那么微软必然会内置一些功能来排除它，也大概率比第三方公司做得更稳妥。微软也确实这么做了。
> ^sran-1725984922696
