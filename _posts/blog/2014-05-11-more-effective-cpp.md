---
layout: post
title: 读书笔记：《More Effective C++》
description: 很久很久以前读过Effective C++，这第二卷现在才看。。。太懒了怎么办。。。
category: blog
---

1. pointer和reference：不会改变指向，或要重载类似operator[]这样的操作符时，使用reference，其他任何时候都是用pointer。
2. c++转型操作符：static\_cast基本与C风格转型相同，const\_cast只用于改变const和volatile，dynamic\_cast处理继承中的向下转型，reinterpret\_cast与编译器相关不具备移植性，通常用于函数指针的转换，实际上reinterpret\_cast可以随意转换4字节整数，包括int和指针。
3. 数组和多态不要混用。
4. 如非必要，不提供默认构造函数。
5. 



[Joshua]:    http://joshuastray.github.io  "Joshua"
