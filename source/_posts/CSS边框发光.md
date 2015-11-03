title: CSS边框发光
date: 2014-04-08 15:30:43
tags: css
category: css
---
```javascript
  input[type=text]:focus,input[type=password]:focus,textarea:focus,textarea:hover,input:hover{
        transition:border linear .2s,box-shadow linear .5s;
        -moz-transition:border linear .2s,-moz-box-shadow linear .5s;
        -webkit-transition:border linear .2s,-webkit-box-shadow linear .5s;
        -o-transition:border linear .2s,-webkit-box-shadow linear .5s;
        outline:none;border-color:rgba(0,102,204,0.75);
        box-shadow:0 0 8px rgba(0,153,204,1);
        -moz-box-shadow:0 0 8px rgba(0,153,204,1);
        -webkit-box-shadow:0 0 8px rgba(0,153,204,1);
        -o-box-shadow:0 0 8px rgba(0,153,204,1);
    }
```
