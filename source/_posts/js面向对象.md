title: js面向对象
date: 2014-05-28 09:19
tags: js
category: javascript
---
```javascript
//封装
function _objEvent() {

    this._callBack = "";//记录回调函数
    this._setCallBack = function (callback)//保存回调寒素
    {
        if (typeof(callback) == "function")//判断回调函数
        {
            this._callBack = callback;//保存回调函数
        }
    }

    this._onclick = function ()//执行保存的回调函数
    {
        if (typeof(this._callBack) == "function")//判断回调函数
        {
            this._callBack();//这里少了个()号执行回调
        }
    }
}
function showkey()//回调函数
{
    alert("miaomiaomiao");
}
var obj1 = new _objEvent();//实例化
obj1._setCallBack(showkey);//给对象设置回调函数
obj1._onclick();//执行回调

//继承
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.sayname = function () {
        alert("sayname");

    }
}
// Person.prototype={
//    hobby:function(){
//       return "片片鱼";
//
//       }
//
//    }
Person.prototype.hobby = function () {
    alert("吃片片鱼");
}
function DDD(name, age) {
    //Person.call(this,name,age)
    this.eat = function () {
        //return "dddd";
        //call(Presson.hobby());
    }

}
DDD.prototype = new Person();
var lxy = new Person("罗雪燕", "21");
//alert(lxy.name+""+lxy.hobby());
var wx = new DDD("王潇", "22");
wx.sayname();
wx.hobby();


```