---
title: java-errors
date: 2017-03-06 19:15:59
categories: [java]
tags: [error,java]
description: java的一些常见错误
---
## 简介
记录平时写java程序的时候，遇到的一些错误，以及解决思路。
## 错误
###  错误1
1. error
```error
this compilation unit is not on the build path of a java project
```
2. solution
上面是因为你在打开java项目的时候，文件里面缺失`.classpath`和`.project`文件所导致的；我们使用eclipse新建一个项目，然后将新项目中的这两个文件，复制到以前的项目中，然后打开`.project`文件，修改下projectName就可以了
