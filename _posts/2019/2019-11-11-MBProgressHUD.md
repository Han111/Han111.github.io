---
layout: post
title: "MBProgressHUD设置背景方框为透明"
subtitle: ''
author: "Han"
header-style: text
tags:
  - iOS
---

先设置hud.bezelView 的style 为MBProgressHUDBackgroundStyleSolidColor，然后再设置其背影色就可以了。默认的style 是MBProgressHUDBackgroundStyleBlur。

废话不多说，直接上代码：

OC：

MBProgressHUD *hud = [MBProgressHUD showHUDAddedTo:self.view animated:YES];

hud.bezelView.style = MBProgressHUDBackgroundStyleSolidColor;

hud.bezelView.backgroundColor = [UIColor clearColor];

Swift：

let hud = MBProgressHUD.showAdded(to:self.view, animated:true)

hud.bezelView.style = .solidColor

hud.bezelView.backgroundColor =UIColor.clear

参考：https://www.jianshu.com/p/9be9bb3d9d69






