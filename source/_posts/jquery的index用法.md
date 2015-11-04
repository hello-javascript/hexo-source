title: jquery的index用法
date: 2014-12-05 20:36:30
tags: index
category: javascript
---
```javascript
<div class="list">
    <span></span>
    <div></div>
    <span></span>
    <span>11111111111</span>
    <div></div>
    <span></span>
    <span></span>
    <span></span>
    <div></div>
</div>
<script>
    $(".list span").click(function() {
        alert($(this).index());
        alert($(".list span").index(this));
    })
</script>
```
运行结果 2,3
`$(this).index()`   这个是根据当前同级而言来进行索引，
`$(".list span").index(this)`是根据符合左侧选择器要求的筛选出来后，进行索引
来自Flc总结

