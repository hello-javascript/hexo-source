title: 动态table不支持onclick
date: 2014-05-29 19:56:15
tags: js
category: javascript
---
- 不要着急，其实你知道了问题所在，就成功了大半,解决办法，table外面套一个div，IE7、8、9table又不支持冒泡，你获取parent()就可以了
- 打开一个窗口`window.open("/b_eps_portal/"+racl,'newwindow')`