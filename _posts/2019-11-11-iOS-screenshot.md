---
layout: post
title: "iOS检测截图"
subtitle: ''
author: "Han"
header-style: text
tags:
  - iOS
---

在项目中，有的时候会有这样一个需求，就是检测手机系统截图的操作，并作出相应的处理。iOS7以后苹果为大家提供了一个获取截图的通知，会在截图后调用。

OC：

[[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(takeScreenshotAction) name:UIApplicationUserDidTakeScreenshotNotification object:nil];

Swift：

NotificationCenter.default.addObserver(self, selector: #selector(ViewController.takeScreenshotAction), name: NSNotification.Name.UIApplicationUserDidTakeScreenshot, object:nil)







