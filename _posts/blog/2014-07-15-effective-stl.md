---
layout: post
title: 读书笔记：《Effective STL》
description: 
category: blog
---

总是使用empty而不是比较size和0.

连续容器，list， 关联容器删除元素的方法都不同P38.

erase会使当前的iterator失效，在一些循环里需要一点'技巧'：

```
关联容器
for(i = c.begin(); i != c.end();)
{
	if(bad(*i))
		c.erase(i++);
	else
		++i;
}
//连续容器
for(i = c.begin(); i != c.end();)
{
	if(bad(*i))
		i = c.erase(i);
	else
		++i;
}
```

可以使用swap来删除容器中不需要的空间

```
//构造一个临时变量和自己交换
string(s).swap(s);
vector<int>(v).swap(v);
//清空v
vector<int>().swap(v);
```

vector<bool>中并不实际存储bool，而是使用1位来表示一个bool，类似位域。所以它实际上比不是一个标准的容器，很多操作并不适用。可以使用deque<bool>或bitset。