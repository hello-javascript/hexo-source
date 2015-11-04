title: JSONP跨域
date: 2014-12-05 20:26:12
tags: 跨域
category: javascript
---
```javascript
function jsonp(res){
console.log(res.name)
}
jsonp({"name":"joe"});//2
```
输出joe
标记为2你可以放到任何域名下的
xxx.js里
xxx.php里
xxx.do里、、、
