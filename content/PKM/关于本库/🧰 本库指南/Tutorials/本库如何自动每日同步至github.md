---
title: 本库如何自动每日同步至github
alias: 本库如何自动每日同步至github
uid: 
author: 
description: 
date-created: 2024-08-17 20:45
date-modified: 2024-09-13 11:31
type: 
date created: 2022-08-25
date modified: 2022-08-25
tags: []
---

[[本库如何指定笔记同步至github]]

为什么不使用 [[obsidian git]] 插件？
因为它执行 gti 同步命令的时候，会让 obsidian 变得非常卡。而且本身我只需要用 git 定期备份只 github，其他的 git 版本回退等功能，我都是使用 [[🤖VSCode]] 打开本库执行的，功能更全面，用起来也更得心应手。所以就采用了操作系统级的自动执行 git 命令的方案，而非 obsidian 内置 git 执行的方案。

如何配置操作系统级的自动 git 命令？
随便找一个自动化运行的工具，设置为定时触发以下命令即可：

```zsh
cd /Users/cdd/Works/knowledge-garden
git pull
git add .
git commit -m "auto by keyboard"
git push
```

mac 上常见的工具有：[[keyboard maestro]]、[[hazel]] 等，我使用的前者。配置截图如下：
![[e351a23921a093106433131f1e3887fd_MD5.png]]
