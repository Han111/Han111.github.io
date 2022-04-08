---
layout: post
title: "解决CocoaPods was not able to update错误"
subtitle: ''
author: "Han"
header-style: text
tags:
  - iOS
---

解决CocoaPods was not able to update错误 

今天在更新Pod时出现这样一个错误：
[!] CocoaPods was not able to update the `xxx` repo. If this is an unexpected issue and persists you can inspect it running `pod repo update --verbose`

记录下自己的解决办法：
1、首先终端输入命令：pod repo list
这个命令会列出你当前的repo和git地址。

2、看下你的这个不能更新的xxx repo是不是git地址不能访问了，如果是这个原因让管理员给你开通下访问权限。

3、如果是换地址了或不再用到这个xxx repo，可以将其删除：
终端输入命令：pod repo remove xxx

4、删除成功后再重新执行更新命令