title: float-left的对象如何居中
date: 2015-09-22 10:07:24
tags: 布局
category: javascript
---
[参与测试的浏览器：IE6 / IE7 / IE8 / FF3 / OP9.6 / SF3 / Chrome2 ]


我们在做导航（nav）时，通常会用到float：left;但是这样做的话，让导航文本水平居中确实个麻烦事；

PC端用的多，在手机端，可以不用float，很多新的布局可用

分析如下：

[float:left]有个伟大之处，它使div（或者其他标签）的宽度自适应其内容，但它却有个弊端：无法居中。
[display:inline-block]也有同样的特性，并且可以居中，但连续几个这样的东东，之间却会出现空格。

为了解决这个问题，我们可以把二者结合起来使用：
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>inline-block解决float:left对象无法居中的问题。</title>
    <style type="text/css">
        * { margin:0; padding:0; list-style:none;}
        body { text-align:center;}
        li { float:left; font-size:12px;}
        a { float:left; border:1px solid #000; padding:5px 10px; text-decoration:none; color:#000;}
        ul { display:inline-block; *display:inline; zoom:1; margin-top: 10px}
    </style>
</head>
<body>
<ul>
    <li><a href="#nogo">首页</a></li>
    <li><a href="#nogo">关于</a></li>
    <li><a href="#nogo">产品</a></li>
    <li><a href="#nogo">联系我们</a></li>
    <li><a href="#nogo">留言</a></li>
</ul>
</body>
</html>
```
原文地址http://www.cnblogs.com/hema/archive/2009/12/17/1626497.html