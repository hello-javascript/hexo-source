title: replace函数真强大
date: 2015-07-12 15:12:43
tags:　replace
category: javascript
---
写了一个把样式表的px转换成rem的东西，因为上周写的页面在平安银行APP里面显示有问题，
<meta name="viewport" content="width=640,user-scalable=no">这个meta不识别的，
还是得用rem布局，就写了个这个，后期闲下来试试写个node或者gulp插件来做这个东西
```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
<input type="text" id="con"/><input type="button" id="btn" value="开始"/>

<div id="res"></div>
<script>
    document.querySelector('#btn').addEventListener('click', function () {
        var txt = document.querySelector('#con').value;
        var reg = /(\d+\.\d+)px|(\d+)px/ig;

        function med() {
            console.log(arguments);
            var s1 = arguments[0];
            return parseFloat(s1) / 100 + 'rem'
        }

        var txt2 = txt.replace(reg, med);
        console.log(txt2);
        document.querySelector('#res').innerHTML = txt2;
    })

</script>
</body>
</html>
```