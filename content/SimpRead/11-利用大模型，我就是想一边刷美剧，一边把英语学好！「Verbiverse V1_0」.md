---
title: 11-利用大模型，我就是想一边刷美剧，一边把英语学好！「Verbiverse V1_0」
alias: 11-利用大模型，我就是想一边刷美剧，一边把英语学好！「Verbiverse V1_0」
uid: 
author: 
description: 
date-created: 2024-08-01 10:01
date-modified: 2024-09-13 11:31
type: 
tags: []
---

> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [sspai.com](https://sspai.com/post/90975)

> 前言上一篇文章向大家介绍了开发的一个小工具，最近又完善了下使用起来还是比较顺手的，今天就向大家正式介绍下 VerbiverseV1.0：方便、快捷的利用大模型帮助我们阅读外语文档与观看视频来提升语言能力 ……

前言
--

上一篇 [文章](https://sspai.com/post/89483) 向大家介绍了开发的一个小工具，最近又完善了下使用起来还是比较顺手的，今天就向大家正式介绍下 [**Verbiverse V1.0**](https://github.com/HATTER-LONG/Verbiverse) ：**方便、快捷的利用大模型帮助我们阅读外语文档与观看视频来提升语言能力**。

![](https://cdnfile.sspai.com/2024/07/30/7702f23f68f1f98b8c41c09e3e6f9961.png?imageView2/2/format/webp)PDF 阅读 陌生单词解析![](https://cdnfile.sspai.com/2024/07/30/ebc5d79388d17d4a2423ad589c0faeb3.png?imageView2/2/format/webp)视频字幕解析

背景介绍
----

_**TL;DR**_ **介绍一些 LLM 应用于语言学习相关功能的情况以及开发这个软件的背景。**

开发这个工具的根本原因在于我想要利用 LLM 大模型进行语言学习过程中发现用的非常不爽的点：

1. 与 LLM 对话的练习，由于初学者知识储备不足会导致对话和网上相亲对象聊天一样枯燥，没话找话 😂，而且我使用本地模型时发现，由于参数量少效果也很差；

![](https://cdnfile.sspai.com/2024/07/30/a9e2f4c25d834d5b9cd3f241ad3a0026.png?imageView2/2/format/webp)

    2. 与 LLM 一起阅读或看视频，这样可以避免没有主题的问题，但是我还没找到很有效的工具适合这种使用场景：

1. 遇到不熟悉的单词可以简单询问大模型，它可以给出基于上下文的回答；
2. 还可以将文档作为知识背景与大模型讨论；
3. 避免问答模式的工具使用的繁琐步骤，尽量内置对应场景的提示词；

![](https://cdnfile.sspai.com/2024/07/30/d50ef1da946176b924eaccb022be7cbd.png?imageView2/2/format/webp)

功能介绍
----

功能分为两大部分，一个是辅助阅读文档，一个是视频字幕翻译，从主页入口打开文件或者从历史列表选择打开过的文件即可跳转对应功能页面：

![](https://cdnfile.sspai.com/2024/07/30/c0b1489e1c2c1939580ced0325ab0b2a.png?imageView2/2/format/webp)Home Interface

## LLM 辅助阅读文档

主要提供的功能也很直观，选中不熟悉的单词，鼠标右键选择解释即可，这里两个解释使用的语言可以在设置中配置：

* 如下图解释同样可以应用于右侧与 LLM Chat 的区域；
* 右侧 Chat 区域会在**第一次发送对话时对文档进行向量嵌入**，作为大模型的知识背景；

![](https://cdnfile.sspai.com/2024/07/30/82805bf94084e35a3b47e9cc71b6a61b.png?imageView2/2/format/webp)Read and Chat Interface

选择解释后会弹出一个浮动窗显示大模型返回的信息，鼠标点击其他地方则自动关闭，右上角可以将窗口固定，右下的按钮可以将单词添加单词本中；

![](https://cdnfile.sspai.com/2024/07/30/2b1a88eca6f889af441ff79b6fd1ee88.png?imageView2/2/format/webp)

对话中可以使用检查按钮对你讲要输入的语句进行检查，工具会自动将历史对话一并发给大模型，用来判断输入是否符合语境：

![](https://cdnfile.sspai.com/2024/07/30/54523bb0f4777f9e3a7663349b942d9d.png?imageView2/2/format/webp)

## 观看视频

观看视频需要你准备视频以及 SRT 格式的字幕文件，最好是双语或者纯英语的字幕，ASS 格式可以使用在线工具转为 SRT，工具有很多；

视频播放界面布局如下，左侧分为视频播放区与字幕显示区，右侧则是字幕列表与当前视频文件相同目录下的其他同格式视频：

![](https://cdnfile.sspai.com/2024/07/30/1887d5f15ee9f85d1a270b7ce301452b.png?imageView2/2/format/webp)Video Interface

双击字幕显示栏中的单词则可进行解释，工具会将前后 20 条字幕一起发给大模型进行解析：

![](https://cdnfile.sspai.com/2024/07/30/d03ab0643be3f37be648f7da9cf0126b.png?imageView2/2/format/webp)

点击字幕右侧的机器人图标则可以对当前整句字幕进行解析：

![](https://cdnfile.sspai.com/2024/07/30/00abbf52a8e19acea78ebecb9e96ca29.png?imageView2/2/format/webp)

在视频页面鼠标右键的弹出菜单可以手动指定添加字幕与隐藏字幕第一行（这对控制双语字幕很有用）：

![](https://cdnfile.sspai.com/2024/07/30/f8cc2f3cbc01151fe61783f5aa67046e.png?imageView2/2/format/webp)

其他的一些细节功能包含：

* 双击画面播放、暂停，或空格快捷键；
* 单击隐藏、显示进度条；
* 键盘左右快捷键跳转前后字幕时间点；

上手指南
----

项目源码地址：[HATTER-LONG/Verbiverse: 利用 LLM 大模型辅助阅读 PDF 与观看视频，用以提升语言能力。 (github.com)](https://github.com/HATTER-LONG/Verbiverse)

感兴趣的请给个 STAR ✨ ，谢谢 🙏 ！！！

## 预编译包

提供如下平台预编译程序包，下载对应平台程序包执行即可：

* [Windows x86_64](https://github.com/HATTER-LONG/Verbiverse/releases/latest)
* [ubuntu_22.04 x86_64](https://github.com/HATTER-LONG/Verbiverse/releases/latest)

Windows v1.0 版本 还可以在这里 [123 网盘下载](https://www.123pan.com/s/8RafTd-q77bd.html) 提取码: 1234

> pyinstaller 打包用了 upx ，有时会被杀软报毒，可以添加信任或者通过源码自己重新打包，我提供的这几个包都是 [github action](https://github.com/HATTER-LONG/Verbiverse/actions) 编译生成的。

## 源码运行

1. clone 源码到本地：`git clone https://github.com/HATTER-LONG/Verbiverse.git`
2. 使用 conda 或 python (>=3.9, <=3.12) venv 创建虚拟环境，推荐使用 conda：
    * 使用 conda：`conda create -n Verbiverse python=3.11; conda activate Verbiverse`
    * 使用 venv，进入源码目录后：`python3 -m venv ./.venv; source ./venv/bin/activate`
3. 安装 poetry：
    * 确认已正确启用虚拟环境；
    * `pip install -U pip setuptools; pip install poetry`
4. 安装项目依赖环境：`poetry install`：
    * 需要代理则取消 `pyproject.toml` 中 `[[tool.poetry.source]]` 相关注释;
5. 运行程序：`python main.py`

## 工具设置

> ⚠️ 建议优先使用本地模型或较小的 PDF 文档进行试用，因为工具会在第一次对话开始时对整个文档进行向量嵌入，过大的文件可能会造成大量 token 消耗！！！！

工具的核心功能依赖 LLM，因此在使用前需要配置相应 LLM 的服务信息，工具支持使用本地模型或云端商用模型，当前支持 OpenAI 协议本地工具或商用模型与通义千问商用模型：

使用商用模型，下图以通义千问为例，如需使用 OpenAI 同理填入对应信息即可：

![](https://cdnfile.sspai.com/2024/07/30/cfd50cd639a038539057899d16709db0.png?imageView2/2/format/webp)

使用本地模型，需要选择 OpenAI 协议，填入本地工具的 LLM 服务地址，使用 LM Studio 为例：

> 不清楚本地模型的一些基本概念可以看我的这篇文章：[为你的钱包节流，本地部署 LLM code assistant - 少数派 (sspai.com)](https://sspai.com/post/87839)

* LM Studio 加载对应模型：

![](https://cdnfile.sspai.com/2024/07/30/58f4c154c58e630f022010b9b4d258fb.png?imageView2/2/format/webp)

* 工具配置：

![](https://cdnfile.sspai.com/2024/07/30/dc104153bd954df8b731f3c14f7a8d67.png?imageView2/2/format/webp)

总结
--

距离上一篇文章介绍工具已经过去了将近两个月了，磕磕绊绊算是自认为达到 1.0 版本了，希望对你有所帮助，有什么问题或好的建议欢迎留言！！！

最后在宣传下，感觉好用就给个 Star 吧 🙏 🥹

项目源码地址：[HATTER-LONG/Verbiverse: 利用 LLM 大模型辅助阅读 PDF 与观看视频，用以提升语言能力。 (github.com)](https://github.com/HATTER-LONG/Verbiverse)
