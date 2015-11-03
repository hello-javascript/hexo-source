title: 第一个jquery插件
date: 2014-06-12 16:37:12
tags: js
category: javascript
---
```javascript
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <title>jquery插件</title>
    <script src="js/jquery-1.7.2.min.js"></script>
    <script src="js/jquery.one.js"></script>
    <script>
        $(function(){
            $(".box").fax({
                showfun:"mouseover",
                content:"raclen"
            })
        })
        /*
         JS实现代码
         $(function(){
         var _li=$(".nav ul li");
         $(".content div").eq(0).show();

         //alert("1111");
         _li.click(function(){
         var _index=$(this).index();
         $(".content div").eq(_index).show().siblings().hide();
         })
         })*/
    </script>

    <style>
        body,box,ul,li{ margin:0px; padding:0px; width:100%;}
        .box{ margin:0 auto; width:400px; height:200px; border:rgba(153,153,153,1) solid 2px; margin-top:40px;}
        .box ul{background:rgba(51,102,255,1);float:left; height:40px;}
        .box ul li {float:left; list-style:none; cursor:pointer; line-height:40px; border-right: rgba(255,255,255,1) solid 1px; width:33%; text-align:center; display: block; color:#fff; }
        .raclen div{ display:none;}
    </style>
</head>
<body>
<div class="box">
    <div class="nav">
        <ul>
            <li>第一个</li>
            <li>第二个</li>
            <li>第三个</li></ul>
    </div>
    <div class="raclen">
        <div>one</div>
        <div>two</div>
        <div>thress</div>
    </div>
</div>
</body>
</html>
```
``````javascript
/*
jquery.one.js byz 之涯
插件就像函数封装一样，写好的东西，换几个参数调用
这里需要注意的是$.extend的用法，后面的覆盖前面的，所以我们可以设置默认值
其它也没什么好说的，插件还是比较简单，容易接受的
$.extend详细用法可以参考http://www.cnblogs.com/RascallySnake/archive/2010/05/07/1729563.html*/

;(function ($)
{
	$.fn.fax=function(options){

		var defaults={showfun:"click",content:"content"};
		var opts=$.extend(defaults,options);//extend后面的会覆盖前面的值
		var obj=$(this);
		var _li=obj.find("ul li");
		$("."+opts.content).find("div").eq(0).show();
		_li.bind(opts.showfun,function(){
			var _index=$(this).index();;
			$("."+opts.content).find("div").eq(_index).show().siblings().hide();

			})
		}
})(jQuery);
```