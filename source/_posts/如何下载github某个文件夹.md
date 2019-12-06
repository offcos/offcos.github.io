---
title: 如何下载github某个文件夹
date: 2019-12-07 00:01:31
tags:
- github
- github下载文件夹
---
## 第一步:
复制gitHub repository的地址到剪切版
https://github.com/CoreyMSchafer/code_snippets

## 第二步:
修改url地址，比如我要下载子目录13-Deployment-Linode，那么在后面追加地址/trunk/Django_Blog/13-Deployment-Linode，完整的地址如下：

https://github.com/CoreyMSchafer/code_snippets/trunk/Django_Blog/13-Deployment-Linode

## 第三步:
进入命令行输入｀svn checkout｀ 去下载文件夹内容

```
svn checkout https://github.com/CoreyMSchafer/code_snippets/trunk/Django_Blog/13-Deployment-Linode
```
## 参考：
https://help.github.com/articles/support-for-subversion-clients/