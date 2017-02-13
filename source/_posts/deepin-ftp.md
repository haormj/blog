---
title: deepin操作系统中ftp的使用
date: 2016-11-08 16:51:33
categories: deepin
tags: [deepin,ftp]
description: 在deepin系统中使用ftp下载东西
---
## 思路
1. 因为deepin操作系统桌面和mac系统的有点相似，同时在应用上也是比其他linux版本要丰富，从而我刚开始就选择了看文档管理器是否能够打开，结果是不可以的；
2. 接下就就是尝试ftp命令了
   ```shell
   sudo apt-get install ftp
   ftp 10.128.48.10
   ```
   然后输入用户名和密码就可以了，如果是匿名登陆：
   > 用户名：anonymous
   > 密码：空

   登陆之后，就可使用ftp ?来查看帮助，主要是中文显示乱码，这是因为ftp服务器编码为gbk，所以自己尝试着修改字符集，最后虽然失败了，但是有以下两点经验：
   ```SHELL
   sudo dpkg-reconfigure locales
   sudo locale-gen
   ```
   你在搜索字符集的解决方案的时候，是有八九会使用到以上两个命令，但是你可能会发现自己系统上没有这两个命令，但是locale已经安装了。就是因为没有加 sudo的问题；
3. 上面两种方法失败之后，就到deepin的应用商店搜索了ftp，安装了filezilla，连接上ftp之后，我遇到了两个问题：
   - 中文显示乱码
       文件->站点管理器->字符集->使用自定义字符集->gbk
   - 在ftp上面下载成功之后，文件打开出错，有可能是传输类型选择错误
       传输->传输类型->自动