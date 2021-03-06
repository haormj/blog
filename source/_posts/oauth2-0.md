---
title: OAuth2.0
date: 2017-03-10 09:22:56
categories: [study]
tags: [oauth2.0,osin]
description: 了解OAuth2.0标准，实现Server端思路
---
## 简介
OAuth2.0是一个授权开发的网络标准，主要是为了解决第三方开发者获取用户信息，同时不将用户的敏感信息暴露给三方
## 流程
首先我们必须清楚OAuth2.0的一些基本流程，为了简单我使用一个简单的例子来说明，设计到的角色有 你，网易，腾讯，我以一个故事的形式来说明。
今天，你打开了网易准备看新闻，然后想要发表自己的评论，这时网易提醒你要进行登陆，出现登陆界面之后，你发现自己并没有在网易注册过账号，但是下面你看到了熟悉的QQ，你点击之后，发现到了腾讯的页面，这种时候让你输入自己的账号和密码，既然是腾讯大哥，你当然会乖乖交上自己的账号和密码，突然你看到下方还有一些复选框，有的是灰色的，有的是你可以点击的，你没有在意，点击了下面的授权按钮，然后你发现自己登陆成功，并且自己网易账号里面的昵称和头像都和自己的qq一样，然后就可以愉快的评论了，这时你可能会想，腾讯大哥好厉害，难道已经收购网易了吗？然后继续看自己的新闻。
故事就这样结束了，也许你不知道，但是这里面就使用了OAuth2.0，在这里我说明下其中的授权码模式的流程，至于其他的，移步到OAuth2.0的[官网](https://tools.ietf.org/html/rfc6749)，里面详细的描述了OAuth2.0的流程，知道你英语不行，这里已经准备了[中文版](https://github.com/jeansfish/RFC6749.zh-cn)。
## 个人理解
腾讯大哥并没有收购网易，只是提供了一个OAuth2.0服务器，可以让网易获取自己用户的一些信息，当然要通过用户的同意。网易首先带着必要的参数访问腾讯的OAuth服务器，然后腾讯收到请求之后，将用户重定向到自己的授权界面，也就是你看到那个有企鹅头像的地方，这时你访问是腾讯的服务器，和网易没有任何的关系，等你输入自己的用户名和密码之后，你点击授权的时候，腾讯就知道你愿意将复选框中的信息提供给网易使用。然后很多事情都是在后台做的，你是不知道的。期间发生的事情是这样的：腾讯知道你要将自己的信息提供给网易之后，就会给网易的服务器发送一个授权码，然后网易的服务器，拿着这个授权码去访问OAuth服务器，获取令牌，拿到token之后，向保存着你资料的腾讯服务器发送请求，同时提供自己上面获取到的token，腾讯的资源服务器收到请求之后，验证token的合法性，如果合法就将你的资料发送给网易的服务器，然后网易拿到你的资料之后，就会给你创建账户，填写的基本信息就是你在注册qq的时候填写的，然后你发现自己可以在网易登陆了，你很奇怪自己没有注册为什么就可以登陆呢？原因就是网易帮你注册的～以上就是授权码的流程。当然OAuth的官方说明中还提供了很多模式，目标就是为了获取token，然后访问资源服务器，获取想要的信息。
## 技术选择
我这里需要实现一个OAuth2.0的服务器，为第三方开发着提供服务。其中OAuth的官网已经提供了很多语言的[实现](https://oauth.net/code/)，你可以选择一个自己熟悉的去开发
