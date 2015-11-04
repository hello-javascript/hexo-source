title: queue的用法
date: 2014-12-05 20:35:10
tags: 动画
category: javascript
---
先上代码
```javascript
<!DOCTYPE html>
<html>
<head>
    <style>
        div {
            margin: 3px;
            width: 40px;
            height: 40px;
            position: absolute;
            left: 0px;
            top: 30px;
            background: green;
            display: none;
        }
        div.newcolor {
            background: blue;
        }
    </style>
    <script src="http://code.jquery.com/jquery-latest.js"></script>
</head>

<body>
    <button id="start">Start</button>
    <button id="stop">Stop</button>
    <div></div>
    <script>
        $("#start").click(function() {
            $("div").show("slow");
            $("div").animate({
                left: '+=200'
            }, 5000);
            $("div").queue(function() {
                $(this).addClass("newcolor");
                $(this).dequeue();
            });
            $("div").animate({
                left: '-=200'
            }, 1500);
            $("div").queue(function() {
                $(this).removeClass("newcolor");
                $(this).dequeue();
            });
            $("div").slideUp();
        });
        $("#stop").click(function() {
            $("div").queue("fx", []);
            $("div").stop();
        });
    </script>

</body>

</html>
```
`queue`的作用就是在动画执行过程中加入自定义动画（一段动画，或者一个`jquery`代码之类）
用上`queue`一般就要用到`dequeue`，`dequeue`的作用是跳出`queue`函数让代码或者动画继续执行，
有开始动画就有停止动画
`$("div").queue("fx", []);`
就是用来结束`queue`定义的动画，`stop()`只能暂停或停止 `animate`定义的动画