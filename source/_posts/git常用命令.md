title: git常用命令
date: 2014-12-05 20:31:58
tags: git
category: 工具
---
clone一个仓库

git clone https://github.com/XXXXXX/jsCode.git

修改的东西添加到仓库

git add . 提交所有文件

git commit -m ‘修改标记’

git pull 更新仓库

git push 提交更新

git branch 查看本地所有分支

git status 查看当前状态

git branch -a 查看所有的分支

git checkout -b dev 建立一个新的本地分支dev

git merge origin/dev 将分支dev与当前分支进行合并

git checkout dev 切换到本地dev分支

git rm 文件名(包括路径) 从git中删除指定文件

git rm  [文件夹]/* 可以删除文件夹所有文件，然后文件夹不见了

git commit -m “remove”  移除文件(从Git中删除)

删除步骤

1、本地删除

2、git add .

3、git commit -am ‘remove’ 一次性提交

4、git push
