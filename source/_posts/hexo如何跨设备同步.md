---
title: hexo如何跨设备同步
date: 2019-12-07 00:02:12
tags:
- hexo
- hexo同步
---
## 实现步骤
### 创建分支（在github上操作）
首先在Github上面创建一个分支命名为hexo，hexo是从master拉取，所以分支的文件和master一样。
初始化分支（PC1上面操作）
在已经部署好Hexo环境的PC1上的安装Hexo的根目录下拉取hexo分支，步骤如下：


git clone 仓库地址，将仓库文件拉取到本地，生成的文件名为 username.github.io；

进入username.github.io文件夹，除了.git文件夹以外，其他文件全部删除；

命令 git add . 将修改提交至暂存区；

命令 git commit -m “提交说明”，提交本次修改；

命令 git push origin hexo 将本次修改推送到远端hexo；

将刚才未删除的.git文件夹拷贝至Hexo根目录，删除username.github.io文件夹，此时本地的Hexo目录已与github上面的hexo文件夹关联了，而且默认的.gitignore已经配置了忽略规则，所以已经可以将根目录下的文件同步上去，还是依次调用add、commit、push三个命令将当前的文件推送至远程的hexo分支。

### 同步分支（PC2上面操作）
此时在PC2上执行以下操作：

git clone -b 仓库名 仓库地址；
在clone下来的仓库文件夹中安装和配置hexo环境，依次调用命令：cnpm install hexo、cnpm install、cnpm install hexo-deployer-git；（不需要hexo init）
此时通过命令hexo g、hexo s即可在本地开启同步下来的博客静态页面，并通过 http://localhost:4000/ 访问。

### 发布博文（PC1或者PC2）
后续不管是PC1还是PC2，如果修改了主题或者新增了博文，按照以下步骤即可：
git add . 暂存修改文件；
git commit -m “修改说明” 提交修改；
git push origin hexo 将新增博文原文件推送至hexo分支；
hexo g -d 将博文静态页面发布至maser分支。

原文链接：https://blog.csdn.net/Yongzili/article/details/98535710