title: 动态创建一个form表单提交
date: 2015-06-01 17:36:01
tags: 表单
category: JavaScript
---
```javascript
//generate submit form
var tpl_form = '<form action="" method="POST"></form>',
    tpl_hidden = '<input type="hidden" name="" value="" />';

var elForm = $(tpl_form);
elForm.attr('action', YZT_API_MERGE_LOGIN);

for(var k in pLogin) {
    var elHidden = $(tpl_hidden);
    elHidden.attr('name', k);
    elHidden.val(pLogin[k]);
    elForm.append(elHidden);
}

$(document.body).append(elForm);
elForm.submit();
elForm.remove();
```