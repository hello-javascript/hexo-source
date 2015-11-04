title: 常用sql语句
date: 2014-06-27 23:25:41
tags: sql
category: other
---
判断用户名是否存在
```javascript
SELECT name FROM `user` WHERE name='$name' limit 1
```
判断登陆是否成功
```javascript
select uid from user where username='$username' and password='$password' limit 1
```
数据记录筛选
```javascript
sql="select * from 数据表 where 字段名=字段值 order by 字段名 "
sql="select * from 数据表 where 字段名 like ‘%字段值%‘ order by 字段名 "
sql="select top 10 * from 数据表 where 字段名 order by 字段名 "
sql="select * from 数据表 where 字段名 in (‘值1‘,‘值2‘,‘值3‘)"
```
更新数据记录：
```javascript
sql="update 数据表 set 字段名=字段值 where 条件表达式"
sql="update 数据表 set 字段1=值1,字段2=值2 …… 字段n=值n where 条件表达式"
```
删除数据记录：
```javascript
sql="delete from 数据表 where 条件表达式"
sql="delete from 数据表" (将数据表所有记录删除)
```
添加数据记录：
```javascript
sql="insert into 数据表 (字段1,字段2,字段3 …) valuess (值1,值2,值3 …)"
sql="insert into 目标数据表 select * from 源数据表" (把源数据表的记录添加到目标数据表)
```