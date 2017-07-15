---
title: vscode
date: 2017-07-15 16:12:25
categories: [config]
tags: [config,vscode]
description: 个人使用vscode配置
---

## 配置文件
```json
// 将设置放入此文件中以覆盖默认设置
{
    "workbench.colorTheme": "One Dark Pro",
    "editor.fontFamily": "Courier New",
    "editor.fontSize": 18,
    "editor.formatOnSave": true,
    "editor.fontWeight": "600",
    "workbench.iconTheme": "easy-icons",
    "editor.lineHeight": 25,
    "http.proxy": "http://192.168.3.7:4444",
    // 在使用函数的同时，后面添加括号
    "go.useCodeSnippetsOnFunctionSuggest": true,
    // 禁止vscode 菜单的快捷键
    "window.enableMenuBarMnemonics": false
}
```

## 快捷键插件
- vscode-emacs-friendly
主要是可以使用emacs快捷键的同时，可以避免在其他地方拷贝东西不出现clipboard中
