title: 新浪Sae数据库连接
date: 2014-06-27 22:33:11
tags: sae
category: other
---
```php
<?php
$con = mysql_connect(SAE_MYSQL_HOST_M.':'.SAE_MYSQL_PORT,SAE_MYSQL_USER,SAE_MYSQL_PASS);
if(!$con){ die('could not connect:'.mysql_error()); }mysql_select_db(SAE_MYSQL_DB,$con);
	//$con=mysql_connect("w.rdc.sae.sina.com.cn:3307","root","123456")or die("mysql连接失败");
	//mysql_select_db("app_ralcenxx1")or die("db连接失败");
	//mysql_set_charset("utf-8");PHP5.2后的函数
	mysql_query('set names utf8');
?>
```