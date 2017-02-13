---
title: shadowsocks-for-deepin
date: 2016-11-07 09:45:22
categories: config
tags: [shadowsocks,deepin]
description: 如何在debain上面安装shadowsocks图形客户端
---
## 步骤
1. 打开链接https://code.launchpad.net/~hzwhuang/+archive/ubuntu/ss-qt5
2. 然后点击下图中的链接
{% qnimg 2016/11/07/1.png %}
3. 我这里选择的是ubuntu16.04版本的，毕竟是长期稳定版
{% qnimg 2016/11/07/2.png %}
4. 点开libqtshadowsocks，下载其中的三个包
{% qnimg 2016/11/07/3.png %}
5. 最后下载shadowsocks-qt5的包
{% qnimg 2016/11/07/4.png %}
6. 在命令行执行dpkg -i来安装 这四个包

## 问题
在安装的过程中可能会出现错误，提示你没有XXX包，这个时候，你只需要运行一下命令即可
```shell
sudo apt-get install XXX
```
然后在重新安装上面的包，下面附上安装成功之后的图片
{% qnimg 2016/11/07/5.png %}
如果还有问题直接戳shadowsocks的github
https://github.com/shadowsocks

