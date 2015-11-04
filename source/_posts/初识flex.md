title: 初识flex
date: 2015-01-23 12:52:40
tags: flex
category: css
---
页面改版，我想到最近看的`flex`，就拿来试试，结果很棒，告别浮动 ，清除浮动这些麻烦事，并且，占多大的地方，都帮你算好了。
但是浏览器兼容是个坑
在谷歌中`display: flex;`
`safari`中 `display: -webkit-flex;`
安卓浏览器 `display: -webkit-box;`
在样式中得
`display: -webkit-box;`
`display: -webkit-flex;`
`display: flex;`
自上而下，看来最古老的写法得写到上面，样式是下面的覆盖上面的。
发现
`safari`（一种旧的谷歌浏览器）
安卓浏览器（一种老版谷歌浏览器）非块级标签设置`display: flex;`无效
UC浏览器（一种古老谷歌浏览器）非块级标签设置`display: flex;`无效