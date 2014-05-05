---
layout: post
title: 读书笔记：《深入理解C++11》
description: 第一篇，要开始好好写。。。
category: blog
---


##第4章
- ++i返回左值，i++返回右值。

##第5章

enum：

- enum是非强作用域类型，具名的的enum类型的名字和成员的名字是全局可见的，可能会造成污染。
- enum进行数值比较时总是会默认转为int，所以也可以与其他enum比较，编译器警告但不报错。class中的数据不会被默认转为int。
- 大多数系统中，函数参数是int可以通过寄存器传递，struct/class只能放在栈上，所以enum有此性能优势。
- 符号不确定，不同编译器不同。

enum class/struct：

- 优势：强作用域，不会默认转为int，可以指定除wchar_t外的类型。
- 是POD类型。
- 可以指定更小的基本类型，节省内存。
- 可以指定类型符号，消除编译器差别。

智能指针：

- 可以对unique_ptr使用move
- shared_ptr共享一个堆分配对象的内存，reset只是引用计数-1.

基于跟踪的gc：

- mark-sweep (spidermonkey使用这种方式)
- mark-compact
- mark-copy

c++11的最小垃圾回收：你™在逗我！
##第6章
