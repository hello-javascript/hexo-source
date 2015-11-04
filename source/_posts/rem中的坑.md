title: rem中的坑
date: 2014-12-31 12:39:46
tags: rem
category: css
---
这里有一篇专门介绍`rem`的
[w3cplus](http://www.w3cplus.com/css3/define-font-size-with-css3-rem)
要注意的是`rem`是相对于html的font-size,但是当你的浏览器最小PX是12PX，而你html是62.5%就是10px，
`rem`不会相对10px，而是12px，一般用谷歌调试，所以还是设置75%的好
