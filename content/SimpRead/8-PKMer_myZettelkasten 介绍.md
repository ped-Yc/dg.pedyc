---
title: 8-PKMer_myZettelkasten 介绍
aliases: 
uid: 
author: 
description: 
date-created: 2024-09-19 19:26
date-modified: 2024-09-19 19:27
status: 
tags: 
url: https://pkmer.cn/Pkmer-Docs/02-%E7%9F%A5%E8%AF%86%E7%AE%A1%E7%90%86%E5%9F%BA%E7%A1%80/%E7%9F%A5%E8%AF%86%E7%AE%A1%E7%90%86%E5%9C%86%E6%A1%8C%E8%AE%A8%E8%AE%BA/terry/myzettelkasten-%E4%BB%8B%E7%BB%8D/
tag: []
banner: "/img/pkmer-avatar.png"
banner_icon: 🔖
---

<div class="menu-toggle"> <SidebarToggle client:idle ></SidebarToggle> </div>

知识管理圆桌讨论

* * *

插件 ID：myzettelkasten-%E4%BB%8B%E7%BB%8D myzettelkasten-%E4%BB%8B%E7%BB%8D myzettelkasten %E4%BB%8B%E7%BB%8D：Terry 实践 Zettelkasten 的方式，基于自己对 Zettelkasten 的不同理解，以及不同的笔记工具而不同。

sr-annote { all: unset; }

## [](#%E6%9C%AC%E6%96%87%E5%AF%BC%E8%AF%BB) 本文导读

每个人实践 Zettelkasten 的方式，都会基于自己对 Zettelkasten 的不同理解，以及不同的笔记工具而不同。

我对 Zettelkasten 的理解主要来自《ANTINET Zettelkasten》一书。其中书中提到 A-N-T-I 四原则：

* A-Analog 模拟（纸笔手写笔记）
* N-Numeric-alpha address 数字字母地址（笔记编号）
* T-Tree structure 树状结构
* I-Index 索引关键词（卡片盒入口，导航）

我主要使用 Obsidian 写笔记，除了 A 原则（纸笔手写笔记）不能做到之外，我基本遵循其余的 N-T-I 原则进行 Zettelkasten 实践。

A 原则我也是认同的，但是用纸笔手写笔记对我来说不现实。虽然做不到手写，但是我用 excalidraw 来写笔记，让笔记看起来跟写在纸上的效果一样。

使用 excalidraw 还有一个很重要的原因，就是我对它非常熟悉。它既是我的白板工具，也是我的草图工具。

而且 Excalidraw 跟 Obsidian 的结合近乎完美——这一点非常感谢匈牙利大叔 Zsolt 将 excalidraw 整合到 Obsidian，并结合 Obsidian 为 excalidraw 插件开发了很多十分惊艳的特性。

实践半年下来，我觉得以 N-T-I 原则组织笔记的方式，用来追踪和发展自己各种各样的想法和思考特别有帮助。

为了更好展示我所理解的 Zettelkasten / 卢曼卡片盒原理，也为了更好地跟同样对 Zettelkasten 感兴趣的朋友交流，我特意制作此库。

**本文主要包含以下内容：**

1. 我对 Zettelkasten 的整体印象
2. myZettelkasten 示例库基本介绍

## [](#1%E6%88%91%E5%AF%B9-zettelkasten-%E7%9A%84%E6%95%B4%E4%BD%93%E5%8D%B0%E8%B1%A1)1. 我对 Zettelkasten 的整体印象

### [](#11-%E6%88%91%E5%AF%B9-zettelkasten-%E7%9A%84%E6%95%B4%E4%BD%93%E5%AE%9A%E4%BD%8D)1.1 我对 Zettelkasten 的整体定位

1. 用来追踪和发展自己的想法与思考，无论是短期想法还是长期想法
2. 长期的个人知识库，为项目提供知识，服务于自己当前和未来的项目

目前市面上流行的几种笔记组织方法：PARA, Zettelkasten, 中图分类法，我在 [从企业管理角度看待笔记方法](https://pkmer.cn/show/20230709201717#1) 一文中，将它们类比到企业管理的场景，来说明我对这几种方法的理解。感兴趣的朋友可以看看。

### [](#12-myzettelkasten-%E5%88%9D%E4%BD%93%E9%AA%8C%E5%85%B3%E9%94%AE%E8%AF%8D%E5%AF%BC%E8%88%AA%E9%9D%A2%E6%9D%BF)1.2 myZettelkasten 初体验：关键词导航面板

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/a9d8284ea580f7da1ca9a324632d7e67_MD5.png]]

**关键词导航面板说明：**

1. 输入 / 选择关键词，进入卡片盒
2. 导航面板自动生成所选关键词指向的分支（树状结构）
3. Table 中展示这个分支的所有笔记，并显示各个笔记的出入链（引用 / 被引用）
4. 按需选择显示范围：起点（根节点 / 分支入口）和深度（分支入口的下一层 / 最后一层）
5. 按需点击具体笔记链接再展示其详细内容

与关键词索引面板交互的方式，有点像是原始版本的 ChatGPT：输入一个关键词，它返回一个答案。但与 ChatGPT 使用海量外部数据生成答案不同的是，ZK 关键词索引面板返回的答案是基于自己过去的思考，并已形成一定分支结构的笔记串。

myZettelkasten 示例库操作演示可以看：

### [](#13-zk-%E5%85%B3%E9%94%AE%E8%AF%8D%E5%AF%BC%E8%88%AA%E4%B8%8E%E6%A0%87%E7%AD%BE%E5%9B%BE%E8%B0%B1%E7%9A%84%E6%AF%94%E8%BE%83)1.3 ZK 关键词导航与标签、图谱的比较

**标签查找 VS ZK 关键词查找**

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/96995fd98af944baad670eba1c4a3fab_MD5.png]]

通过 Obsidian 的标签搜索，我们得到的是带有该标签较分散的多个笔记，且笔记的关系不够清晰。

而通过 Zettelkasten 的索引关键词，我们得到的是基于自己过去思考，已形成该关键词指向的，具有一定分支结构的笔记串。

**图谱 VS ZK 关键词导航**

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/a5f1c983bd75b6bd250177e4337228e3_MD5.png]]

对于想法的发展，我认为树状结构是根本，更能体现这个想法是怎样一步一步发展过来的。

而链接（跨分支，跨主题）的地位次之，但链接容易产生跨界的惊喜，也很重要。

## [](#2myzettelkasten-%E7%A4%BA%E4%BE%8B%E5%BA%93%E5%9F%BA%E6%9C%AC%E4%BB%8B%E7%BB%8D)2.myZettelkasten 示例库基本介绍

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/8443cdfc5f5202658d595bc3841dca75_MD5.png]]

### [](#21-%E8%AF%BB%E4%B9%A6%E7%AC%94%E8%AE%B0)2.1 读书笔记

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/36677d1c2af669f8c793819488710410_MD5.png]]

* 一本书一个读书笔记文件，按阅读的线性顺序写笔记
* 以无序列表的形式组织，每条笔记加 blockID 方便其他笔记引用
* 原文链接（非必须）
* 日期 / 日志链接（非必须）

### [](#22-%E4%B8%BB%E7%AC%94%E8%AE%B0)2.2 主笔记

可以用 excalidraw 模板或 markdown 模板创建（侧边栏的铅笔按钮和钢笔按钮）

**excalidraw 模板示例**

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/218a22d66f31a942fefb64faef0b20ab_MD5.png]]

**markdown 模板示例**

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/1b9939e04bf6e2e8c863b752ff223097_MD5.png]]

**编号规则：中图分类号 + Zettelkasten 编码，分隔符为 "-"**

**主笔记编号操作实例**：比如我想深入学习 Obsidian，于是我种一棵 Obsidian 树，树根节点为 1。Obsidian 是笔记软件，我在网上找到比较适合它的中图分类号是 TP319 专用应用软件。于是，我就建一个 TP319-1 的主笔记卡 Obsidian，并在笔记左下角添加 Obsidian 官网的链接。

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/bf810d09eb10e1857bd7497d302faa2a_MD5.png]]

我对 Obsidian 主要感兴趣是插件和 css，于是我又建了 TP319-1-1 Obsidian plugins, TP319-1-2 CSS。以此类推，TP319-1-1-1 Canvas 插件，TP319-1-1-2 Dataview 插件。

有一天，我觉得 Obsidian 插件众多，像是一个大杂烩。那这个思考笔记放在哪里好呢？

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/648e288da392ae547137785d4a6ed834_MD5.png]]

这个时候，可以用 TP319-1-1A。

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/5337bd69c40baade0719784885f0ede7_MD5.png]]

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/8b1a0b2db61793f665f9bd757f739c62_MD5.png]]

**特别说明**：

1. 很多实践 Zettelkasten 朋友没有用这种数字字母笔记编号，但我觉得编号的作用巨大，因此我的主笔记都是这种编号
2. 编号背后体现的是树状结构，一个笔记通过其编号，就可以看到这个笔记是怎样生长过来的，它记录了这个笔记的发展过程
3. 索引面板是通过编号来自动生成树状结构的，在此库，很多功能都是基于笔记的编号来设计的
4. 这种编码不是一种严格的分类结构，而是一种生长的树状结构
5. 每一个新笔记，你需要选择挂到一个你认为最合适的位置附近，这代表你选择了怎样的笔记关系，也是你想法 / 思考发展的过程

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/eb393cdf61f130787a367162ade9dead_MD5.png]]

另外，中图分类号也不是必须的，它的作用只是让相近主题树靠的比较近而已。

比如我现在已经种了有 4 棵不同领域的树，有一天我想研究 Notion，如果不用中图分类号，这时我的 Notion 就是 5 号树。而使用分类号，我的 Notion 主题树为 TP319-2，跟 Obsidian TP319-1 离得比较近。

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/507f921cfd184743b6249ce4bb1a3b76_MD5.png]]

### [](#23-%E7%B4%A2%E5%BC%95%E5%85%B3%E9%94%AE%E8%AF%8D)2.3 索引关键词

索引卡用来定位树状结构的入口：

1. 使用文字关键词命名
2. 内容仅包含所指向的分支入口链接

![[SimpRead/_resources/8-PKMer_myZettelkasten 介绍/65e190bba4003788265996acbb7ce30f_MD5.png]]

等笔记到了一定数量之后，主要通过关键词 + 分支笔记串（树状结构）+ 出入链来检索笔记。索引卡的作用和意义需要等笔记数量上来之后才能更好地理解。

## [](#%E6%9C%80%E5%90%8E) 最后

该示例库是基于本人对 Zettelkasten / 卢曼卡片盒原理的理解，结合 Obsidian 插件 / 功能打造的一种实现方式。里面包含了很多我自己的使用习惯，大家不必完全参照：比如用 excalidraw 写笔记。

对 Zettelkasten 原理，数字字母编码，索引关键词等话题感兴趣的朋友可以查看 [OB 中文论坛 Zettelkasten 讨论帖](https://forum-zh.obsidian.md/t/topic/20515/27?u=terry_c)。

**阅后福利**

关于作者 Terry 的一些管理方法和 Demo 库，作者已经提供了示例空间，欢迎大家自己下载体验 [点我获取](https://pan.baidu.com/s/1sngJz9ez1J76-mAFa28RQA?pwd=f83z)

## [](#%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B) 视频教程

### [](#terry%E6%88%91%E7%9A%84zettelkasten%E5%AE%9E%E8%B7%B5%E5%88%86%E4%BA%AB)Terry：我的 Zettelkasten 实践分享

我的 Zettelkasten 实践分享 为什么我选择 ZK 卡 1

我的 Zettelkasten 实践分享 为什么我选择 ZK 卡 2

我的 Zettelkasten 实践分享（工作流 1）

我的 Zettelkasten 实践分享（工作流 2）

我的 Zettelkasten 实践分享（工作流 3）

**讨论**

若阁下有独到的见解或新颖的想法，诚邀您在文章下方留言，与大家共同探讨。

知识管理 myZettelkasten 介绍 Obsidian
