title: 页面偏移transform
date:  2014-06-12 09:16:05
tags: css
category: css
---
核心代码就这两句，上面是偏移长度，下面 相当于动画时间
```javascript
$(".box").css({"-webkit-transform":"translateX(150px)"});
$(".box").css( {"-webkit-transition": "all 0.4s"});
```

用这两句可以做[mou](http://caibaojian.com/demo/2014/4/off-canvas-menu.html) 这样的效果
`transform`其它属性可以参考[mou](http://www.daqianduan.com/2959.html)