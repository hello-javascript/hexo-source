title: node+Mongoose实现分页
date: 2015-10-19 13:32:33
tags: nodejs
category: javascript
---
如果说hibernate是让程序员用面向对象的思维操作数据库，Mongoose就是让程序员用函数的思想操作数据库。
[node+Mongoose实现分页的原理](http://blog.csdn.net/save____/article/details/8890856)这个人写的是对的，就是有个单词写错了exex应为`exec`
修改后如下
```javascript
    var mongoose = require(“mongoose”);
    mongoose.connect(“mongodb://localhost/adb”); //连接mongodb
    var model = mongoose.model(‘myCollection’,{title:String});

    var start = 1;           //这边可以改为接收参数后的计算
    var pageSize = 10; //每一页显示的数据条数
    model.find().skip(start).limit(pageSize).exec(function(err,datas){
    //dosomething for your page
    //datas 是分页后的数据 这边写你的数据渲染或其他操作
    });
```
