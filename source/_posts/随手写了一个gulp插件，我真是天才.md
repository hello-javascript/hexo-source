title: 随手写了一个gulp插件，我真是天才
date: 2015-07-12 16:54:22
tags:　gulp
category: javascript
---
作用就是把px转换成rem，今天加班收获不少O(∩_∩)O哈哈~
![gulp](/img/201511041406.png)
```javascript
var through = require('through2');
module.exports = function () {
    return through.obj(function (file, enc, cb) {
        if (file.isNull()) {
            this.push(file);
            return cb();
        }

        if (file.isStream()) {
            this.emit('error', new gutil.PluginError(PLUGIN_NAME, 'Streaming not supported'));
            return cb();
        }
        var reg=/(\d+)px/ig;
        function med(){
            var s1=arguments[1];
            return parseFloat(s1)/100+'rem'
        }
        var content=file.contents.toString().replace(reg,med);
        file.contents = new Buffer(content);

        this.push(file);

        cb();
    });
};
```
`file.contents.toString()`这句话的意思就是获取文件的内容，然后转换成字符串

放在这https://github.com/ralcen/jsCode/blob/master/gulp_bulid/gulp-pxtworem.js
为了匹配小数的情况，更新了一下正则表达式
 `var reg = /(\d+\.\d+)px|(\d+)px/ig;`
med函数也有所更改，具体看github里面的代码