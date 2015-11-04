title: 总结一下jquery跨域
date: 2014-06-11 17:08:03
tags: 跨域
category: javascript
---
一直以来没遇到，两次擦肩而过，这里写一下，感觉他们写的都很模糊
后台代码，放到请求的action，让这些代码执行就行
java代码：
```java
callback= request.getParameter("callback");
```
.net代码:
```c#
string callback = Request.QueryString["callback"];
```
php代码：
```php
$callback=$_GET['callback'];
```
统一返回`callback(data)`//callback是获取的callback的值，data是原本要返回的结果集
```javascript
$.ajax({
    type: "get",
    url: "action地址", // 这个就是不同于当前域的一个URL地址
     dataType: "jsonp",
     jsonpCallback:'callback'// 指定回调函数名（值）（默认callback）
     data: "",
    success: function (json) {
        alert(json.Name);

    }
});
```
另一种方式
```javascript
$.getJSON("action地址?callback=?",
   function(result) {
    }
   });//这种方式是可以的，参考http://blog.csdn.net/weizunde/article/details/25037079
```
