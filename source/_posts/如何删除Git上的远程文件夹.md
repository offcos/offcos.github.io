---
title: 如何删除Git上的远程文件夹
date: 2019-12-07 00:01:52
tags:
- git
---
## 方法一
这里以删除test文件夹为案例

```
git rm -r --cached test //--cached不会把本地的test删除
git commit -m 'delete test dir'
git push -u origin master
```
## 方法二
如果误提交的文件夹比较多，方法一也较繁琐
直接修改.gitignore文件,将不需要的文件过滤掉，然后执行命令:

```
git rm -r --cached .
git add .
git commit
git push  -u origin master
```
原文链接：https://blog.csdn.net/cui130/article/details/84033966