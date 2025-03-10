---
title: 6-深入理解函数式编程（上） - 美团技术团队@annote
date-created: 2025-03-06
date-modified: 2025-03-08
alias: ["srAnnote@深入理解函数式编程（上） - 美团技术团队"]
index: 6
type: Simpread
UID: 20250307013311
---

## 深入理解函数式编程（上） - 美团技术团队

> [!timeline]+ 简介
>
> > **元数据**
>
> ---
> **原文**:: [深入理解函数式编程（上） - 美团技术团队](https://tech.meituan.com/2022/10/13/dive-into-functional-programming-01.html)
> **日期**:: [[2025-03-07]]
> **标签**:: #SimpRead
>
> > **摘要**
>
> ---
> 函数式编程是一种历史悠久的编程范式。

### 笔记

> [!abstract]+ <mark style="background-color: #ffeb3b">Highlight</mark> [🧷](<http://localhost:7026/reading/6#id=1741282909285>)
> ECMAScript 2015 规范引入了箭头函数，它没有 **this**，没有 **arguments**。只能作为一个**表达式（expression）**而不能作为一个**声明式（statement）**，表达式产生一个箭头函数引用，该箭头函数引用仍然有 **name** 和 **length** 属性，分别表示箭头函数的名字、形参（parameters）长度。一个箭头函数就是一个单纯的运算式，箭头函数我们也可以称为 **lambda 函数**，它在书写形式上就像是一个**λ演算式**。
^sran-1741282909285

> [!abstract]+ <mark style="background-color: #ffeb3b">Highlight</mark> [🧷](<http://localhost:7026/reading/6#id=1741285735884>)
> 回到 JavaScript 本身，我们要探究**函数**本身能不能带给我们更多的东西？我们在 JavaScript 中有很多创建函数的方式：
^sran-1741285735884
