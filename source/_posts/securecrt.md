---
title: 安装SecureCRT
date: 2017-05-04 10:52:19
categories: [deepin]
tags: [scrt,SecureCRT,破解]
description: 在deepin上安装scrt 同样适用与Ubuntu
---
## 问题
平时使用ssh登录远程的linux主机的时候，每次都需要复制和粘贴密码，还需要指定证书的路径，很烦！
## scrt安装
在写此文章的时候，scrt官方最新版为8.1，在查询了资料之后发现7.3可以破解，但是同样的方法不能够用在8.1上，从而就使用7.3版本
1. 下载scrt7.3
[scrt7.3](http://og4bzcu0f.bkt.clouddn.com/scrt-7.3.7-1034.ubuntu13-64.x86_64.deb)
2. 安装scrt
```shell
sudo dpkg -i /path/to/scrt
```
3. 下载破解脚本
[scrt_crack](http://og4bzcu0f.bkt.clouddn.com/securecrt_linux_crack.pl)
4. 执行破解命令
```shell
sudo perl /path/to/crack /usr/bin/SecureCRT
```
5. 输入license
打开软件，点击输入许可，将刚刚执行crack输出的信息，填写到里面
