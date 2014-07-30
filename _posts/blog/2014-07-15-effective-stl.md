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

向map插入新元素，优先使用insert，更新元素优先使用operator[]。

iterator可以隐式转化为const_iterator和reverse_iterator。reverse_iterator使用base转为iterator，const_iterator使用advance和distance转为iterator。

```
advance(iter, distance<ConstIterator>(iter, const_iter))
```

对可随机访问的容器(vector,string,deque)的迭代器，这种转换是常数时间，其他容器是线性时间。
在const_iterator和iterator之间总应该优先使用iterator。

remove并不能真正的删除容器中的元素，因为它无法访问到容器的erase，它只是把不符合删除条件的元素移动到前面。unique的行为也是类似的。
remove需要和erase配合使用来真正的删除元素：

```
从v中删除所有等于99的元素
v.erase(remove(v.begin(), v.end(), 99), v.end());
```

如果容器中存储的是动态分配的指针，直接使用remove则几乎肯定会造成泄漏。