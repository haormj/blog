---
title: blog-backup
date: 2017-02-09 11:58:43
categories: [config]
tags: [hexo,blog,backup]
description: 备份自己的blog
---
## 问题
我以前的做法是直接将自己的blog目录拷贝走,但是它带来的问题就是自己很多时候都是解压失败,原因就在与npm包管理,每次解压之后我们都回重新执行npm install,从而我们没有必要拷贝node_modules,这也是自己对npm包管理不熟悉的缘故

> tar: 由于前次错误，将以上次的错误状态退出

## 解决思路
1. 在备份打包的时候拷贝除了node_modules之外的目录
2. 在其他平台上面使用的时候,首先安装nodejs,然后使用npm安装hexo,在blog目录下面执行
```shell
npm install
```
开始你的hacking
## 小知识
和主题有关的东西,直接阅读github上面的README即可
