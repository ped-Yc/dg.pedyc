---
title: <% tp.file.creation_date() %>
uid: <% tp.file.creation_date("YYYYMMDDHHmm") %>
tags:
  - diary
---

<%*
let 一言 = ""
let 来源 = ""
let 作者 = ""

await fetch('https://v1.hitokoto.cn/?c=d&c=h&c=i&c=j')
.then(response => response.json())
.then(data => {
	一言 = data.hitokoto
	来源 = data.from
	作者 = data.from_who === null ? ' 佚名 ' : data.from_who
})
-%>

> [!quote] 一言<br/>
 <% 一言 %> —— 《<% 来源 %>》 · <% 作者 %>

## ☁行云（今日要做什么？）
- TODO
- TODO

## :LiFootprints:跬步（今日做了什么？）
- DONE
- DONE

## ☀日新（习惯养成）
- TODO
- DONE

## :LiSunMoon:温故（每日总结）
> [!NOTE] 今日复盘
> NOTE
