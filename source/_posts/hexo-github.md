---
title: github+hexo配置个人博客
date: 2016-11-03 14:21:51
categories: config
tags: [github,hexo]
description: 使用hexo作为博客管理工具，然后发布到github上面共享
---

## 简介
首先我说下使用到的内容:
- github
- hexo
- node.js
在本文中不介绍node.js和git的相关内容，本质上读者也没有必须知道，网上搜索安装即可
## 创建github仓库
在这里面唯一需要注意的就是仓库名称为：用户名.github.io
## 安装hexo
在我们安装了node.js之后，我们便可以使用npm来安装hexo
```code
npm install -g hexo
```
然后我们自己创建一个博客的根目录，并且cd到此目录下，执行以下命令
```code
hexo init
npm install
npm install hexo-deployer-git --save
hexo g
hexo s
```
完成以上命令，我们就可以直接在浏览器中打开localhost:4000访问我们的博客了
## 发布到github
在发布之前，我们在自己博客根目录中找到

> _config.yml

使用编辑器打开，直接拉倒底部可以看到以下内容：

```code
#  Deployment
## Docs: https://hexo.io/docs/deployment.html
   deploy:
    type:
```
直接修改为:
```code
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: git@github.com:haormj/haormj.github.io.git
  branch: master
```
其中注意repository从自己的github上面复制，保存配置文件

```code
hexo clean
hexo g
hexo d
```

然后就可以将本地的内容发布到github上了
## 如何在本地写博客
```code
hexo new filename
cd 博客根目录/source/_posts/
```
编辑filename.md
其中使用的markdown语法，在网上看看就知道了，注意头部':'后面都是需要一个空格的，然后在写内容
## 小知识
如果你不想博客在主页一下就显示出来，有两种解决思路
1. 在头部增加 description标签
2. 在内容中使用
```code
<!-- more  -->
```
来区分摘要和全文
## 参考
> [hexo在github上搭建个人博客详细步骤](http://blog.csdn.net/qq_15807167/article/details/51601234)
