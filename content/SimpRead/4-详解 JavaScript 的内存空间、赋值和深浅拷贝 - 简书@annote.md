---
topic: 
uid: 
title: 4-详解 JavaScript 的内存空间、赋值和深浅拷贝 - 简书@annote
aliases: 
author: jianshu.com
description: JavaScript的内存空间 在JavaScript中，每一个数据都需要一个内存空间。内存空间分为两种，栈内存（stack）与堆内存（heap） 栈是系统自动分配的内存空间...
tags: []
date-created: 2025-02-28
date-modified: 2025-03-08
status: 
alias: ["srAnnote@详解 JavaScript 的内存空间、赋值和深浅拷贝 - 简书"]
---

## 详解 JavaScript 的内存空间、赋值和深浅拷贝 - 简书

> [!md] Metadata
> **标题**:: 详解 JavaScript 的内存空间、赋值和深浅拷贝 - 简书
> **作者**:: jianshu.com
> **日期**:: [[2025-02-28]]
> **原文链接**:: [原文链接](https://www.jianshu.com/p/fed654c4515d)
> **内部链接**:: [内部链接](http://localhost:7026/unread/4)

> [!summary] 描述
> JavaScript 的内存空间 在 JavaScript 中，每一个数据都需要一个内存空间。内存空间分为两种，栈内存（stack）与堆内存（heap） 栈是系统自动分配的内存空间…

### Annotations

> [📌](<http://localhost:7026/reading/4#id=1740715028621>) <mark style="background-color: #ffeb3b">Highlight</mark>
> 引用类型的值是保存在堆内存中的对象，在 JavaScript 中我们不能直接操作对象的堆内存空间。因为引用类型的值都是按引用访问的，所以在操作对象时，实际上是操作对象的引用而不是实际的对象。引用可以理解为保存在栈内存中的一个地址，该地址指向堆内存中的一个实际对象

> [📌](<http://localhost:7026/reading/4#id=1740715068779>) <mark style="background-color: #ffeb3b">Highlight</mark>
> 比较：是引用的比较（就是地址的比较，变量在栈内存中对应的指针地址相等就指向同一个对象）判断是否为同一个对象，示例如下

> [📌](<http://localhost:7026/reading/4#id=1740715180651>) <mark style="background-color: #ffeb3b">Highlight</mark>
> 浅拷贝：重新在堆内存中开辟一个空间，拷贝后新对象获得一个独立的基本数据类型数据，和原对象共用一个原对象内的引用类型数据，改变基本类型数据，两个对象互不影响，改变其中一个对象内的引用类型数据，另一个对象会受到影响

> [📌](<http://localhost:7026/reading/4#id=1740715189584>) <mark style="background-color: #ffeb3b">Highlight</mark>
> 深拷贝：不论是对象内的基本类型还是引用类型都被完全拷贝, 拷贝后两个对象互不影响

> [📌](<http://localhost:7026/reading/4#id=1740715236894>) <mark style="background-color: #ffeb3b">Highlight</mark>
> 那是因为 使用 JSON.stringify() 以及 JSON.parse() 它是不可以拷贝 undefined ， function， RegExp 等等类型的
