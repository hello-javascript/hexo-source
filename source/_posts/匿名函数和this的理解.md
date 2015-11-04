title: 匿名函数和this的理解
date: 2014-07-30 15:08:36
tags: js
category: javascript
---
![mahua](/img/201511041056.png)
运行结果
![mahua](/img/201511041057.png)
```javascript
    　var name = "The Window";
    　　var object = {
    　　　　name : "My Object",
    　　　　getNameFunc : function(){
    　　　　
    　　　　　　return function(){
    　　　　　　　　return this.name;
    　　　　　　};
    　　　　}
    　　};
    //object.getNameFunc()()因为匿名函数的this指向window（没有其他的干扰）
    console.log("object.getNameFunc()()="+object.getNameFunc()());
    //普通函数的对象是windows，其实这里的test（）,相当于window.test()
    var test=object.getNameFunc();
    console.log("test()="+test());
    //这个this指向的是object，object.name就是My Object了
    object.other=object.getNameFunc();
    console.log("object.other()="+object.other());
    //下面这个this指向是o。o.name没有值，也没有name定义所以是undefined
    var o={};
    o.other=object.getNameFunc();
    console.log("o.other()="+o.other());

```