---
title: ubuntu16.04使用过程问题和解决方案
date: 2017-07-07 13:43:13
categories: [ubuntu]
tags: [FAQ]
description: 目前在使用ubuntu记录些自己遇到的问题，以及解决方案。
---

电脑配置
```config
i7 7700
8g 内存
三星850 250G 固态
```

1. 鼠标不见？点击图标没反应？
- 问题
	在安装完系统之后，因为个人在很早就开始使用ubuntu了，所以比较熟悉。但是这次有点不同，到了登录界面之后，发现鼠标不见了，而且登录框也是看不见的，但是鼠标在左右移动一定的距离之后，就会出现，这个感觉明显就像是虽然是单个显示器，但感觉是多屏，完全没有边界，进入系统之后，设置系统的显示，发现有两个内容，一个是自己的是显示器，一个是buildin-display，具体也不知道是什么，最后在@sishuai学长的帮助下，成功解决问题，这里记录下解决思路。
- 解决方案

	```shell
	sudo nano /etc/default/grub
	#GRUB_CMDLINE_LINUX_DEFAULT="quiet splash video=eDP-1:d"
	#安装上面注释修改
	sudo update-grub
	reboot
	```

	上面主要的目的就是关闭buildin-display，虽然实际上只有一个显示器，但是ubuntu识别的却是两个，从而直接在这里关闭buildin-display，虽然可以`系统设置->显示`里面关闭buildin-display，但是也不能够解决登录界面的问题。
