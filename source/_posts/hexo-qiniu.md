---
title: 用qiniu作为hexo搭建博客的图床
date: 2016-11-06 22:10:42
categories: config
tags: [hexo,qiniu,github]
description: 笔者使用的是github作为载体，所以空间有限，从而选择了使用qiniu作为图床
---
## 步骤
1. 在浏览器打开：https://github.com/gyk001/hexo-qiniu-sync
  按照readme的内容安装，这里需要注意的是，在添加配置文件的时候，不需要添加
  > plugins:
  >  \- hexo-qiniu-sync
  这个内容，这里会导致hexo命令中的server和deploy有问题。
2. 注册qiniu账号
   在上面填写配置文件的时候，你们应该发现这里是需要填写access_key和secret_key，等我们注册了账号之后，就可以在个人账号中获取，你可以将他们两个放到文件中，然后配置secret_file或者配置access_key和secret_key；还有一点需要注意，那就是填写这个urlPrefix，这个我们就使用qiniu提供给我们的测试链接。

## 问题
如果有任何问题，直接给笔者发送到邮件即可 haormj@qq.com，我看到之后会尽量回复你们的！
   
