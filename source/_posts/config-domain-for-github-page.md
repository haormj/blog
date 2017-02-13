---
title: config-domain-for-github-page
date: 2017-02-09 13:51:56
categories: [config]
tags: [hexo,github pages,domain]
description: 为github上面自己搭建的博客绑定域名
---
## 说明
我是使用hexo来管理个人博客的,以下内容仅供参考
## 步骤
1\. 创建CNAME文件

> 以前我通过在github上setting也是可以的,但是每次重新部署之后,就会发现又要重新设置

```shell
cd path/to/blog/source
touch CNAME
echo "youdomain.com" > CNAME
```

2\. 配置路由
你购买了域名之后,都会为你提供DNS服务,从而你需要在你购买域名的网站上面添加一条A记录,简单的理解就是,当在浏览器中输入你的域名之后,映射到那个ip上面,github提供了以下两个ip

>192.30.252.153
>192.30.252.154

## 参考
[github pages](https://help.github.com/articles/setting-up-an-apex-domain/)
## 小知识
如果md列表排列不按照顺序时
```md
1\.
2\.
```