---
layout: post
title: GL_TRIANGLE_STRIP的环绕规则
description: 记录一下，又忘了。。。
category: blog
---

triangle strip 3个顶点的环绕顺序是根据当前顶点n的奇偶性决定，在默认使用CCW的情况下，如果n是第偶数个顶点，顺序是：
![](http://www.matrix44.net/cms/wp-content/plugins/wpmathpub/phpmathpublisher/img/math_986.5_a95bf33d0e8beec545d37360e1f4d005.png)

如果n是第奇数个顶点，环绕顺序是：
![](http://www.matrix44.net/cms/wp-content/plugins/wpmathpub/phpmathpublisher/img/math_986.5_4591b75f8c6849409d97d8c488140382.png)



[Joshua]:    http://joshuastray.github.io  "Joshua"
