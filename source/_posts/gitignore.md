title: .gitignore
date: 2014-12-05 20:24:56
tags: git
category: 工具
---
在使用git的时候，我我们可能会遇到，位于仓库中的某些文件夹不需要提交，我们可以对其过滤
这时候就用到`.gitignore`
在仓库中新建一个`.gitignore`的文件。
在window中创建这个文件可能会弹出请输入键名，
可以在进入git仓库后输入`touch .gitignore` 就创建这个文件了
把需要过滤的文件夹名字写到里面就行了，如果有多个，换行写入