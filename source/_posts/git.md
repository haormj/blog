---
title: git
date: 2017-02-13 17:21:06
categories: [study]
tags: [git]
description: 个人经常使用到的一些git命令
---
## 常用命令
### 生成ssh key
```shell
ssh-keygen -t rsa -C "haormj@qq.com"
```

### 配置
```gitconfig
[http]
	sslVerify = false
[alias]
	st = status
	ci = commit
	co = checkout
	br = branch
	lg = log --oneline --graph --decorate
[user]
	name = haormj
	email = haormj@qq.com
[core]
	editor = emacs -nw
	fileMode = false
```

上面我重点我稍微解释下几个配置:
- sslVerify:git在clone或者是推送的时候,如果你使用的是https协议,他会对这个地址进行检查,从而例如我们自己搭建的git服务器就使用不了,从而关闭这个检测功能就是配置这个参数
- fileMode:你使用git进行版本管理,这个配置的意思就是说,当文件的权限发生变化的时候,要不要对其进行跟踪提交

### 创建
1. 创建远程的本地分支
`git branch develop origin/develop`
2. 创建标签
`git tag -a vx.x.x`

### 删除
1. 删除远程分支
`git push origin --delete <branch_name>`
2. 删除远程标签
`git push origin --delete <tag_name>`

### 远程
1. 推送标签到远程
`git push origin vx.x.x`

