title: contains实现简单搜索
date: 2014-04-10 16:12:41
tags: js
category: javascript
---
```javascript
<html>
<head>
    <title>提示</title>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js"></script>
</head>
<script>

    //jQuery :contains
    $(function(){
        $("#ddd").focus();
        $("#ddd").keyup(function(e) {
            //alert("44555");
            var val= $(this).val();
            if(val==""){
                window.location.reload();

            }
            $("p:contains("+val+")").css("color","red");
        });
    })
</script>
<body>
<input type="text" placeholder="请输入搜索内容" id="ddd"/>
<ul><li>
    <p>胜多负少东方闪电发送到</p>
    <p>aaaaaaaaaa</p>
    <p>bbbbbbbbbbb</p>
    <p>cccccccccccc</p>
    <p>ddddddddd</p>
</li></ul>
</body>


</html>
```