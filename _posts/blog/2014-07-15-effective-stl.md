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