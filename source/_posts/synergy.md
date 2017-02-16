---
title: Synergy
date: 2017-02-16 15:33:04
categories: [deepin]
tags: [synergy]
description: mac/windows/linux 共享键盘和鼠标
---
## 简介
Synergy是一个共享键盘和鼠标的软件,可以实现跨操作系统,使用一个键盘和一个鼠标控制多个电脑
## 步骤
1. Synergy有linux/windows/mac,笔者安装的时候,软件的版本都是1.4.16
2. Synergy分为server和client,其中server就是有插键盘和鼠标的电脑,client就是其余电脑.貌似现在是收费的,具体自己去了解.软件安装成功之后,请参考下面步骤.
3. 点击编辑->设置->加密 这里这个选项一定要保证server和client统一,要么设置密码,要么不设置.否则就是
`WARNING: failed to connect to server: Protocol error from server`
{% qnimg 2017/02/16/1.png %}

4. server
- 在插有键盘和鼠标的电脑上面打开Synergy
- 选择服务器端
{% qnimg 2017/02/16/2.png %}
- 点击设置服务器端,看到上面有垃圾桶和电脑的两个图标,如果要添加client就电脑图标拖到指定的位置,如果要删除,就将框中的小图标拖到垃圾桶中
- 重点:在拖完之后,点击进入配置界面,屏幕名很关键,具体在哪里可以找到可以看client端,否则就会出现
`WARNING: failed to connect to server: Connection was refused`
{% qnimg 2017/02/16/3.png %}
- 设置完成之后,应用->开始 即可

5\. client
- 打开其他电脑上面的Synergy软件
- 选择客户端,图中红色的部分就是屏幕名,在设置server端的时候,保证和这个一样就好了
{% qnimg 2017/02/16/4.png %}
- 然后将server的ip地址输入到下面的框中
- 应用->开始

## 误导
我刚开始安装的时候,步骤不对,导致一直报错,在网上查了说是,必须在一个网段内.
例如
server的ip是`192.168.1.5/24`,其他client也必须是`192.168.1.x/24`,这个说法是错误的,目前我的配置成功了,但是server和client不在一个网段内.