---
layout: post
title: "The app's Info.plist file should contain a NSBluetoothAlwaysUsageDescription"
subtitle: ''
author: "Han"
header-style: text
tags:
  - iOS
---


NSBluetoothAlwaysUsageDescription被拒原因：

iOS13 将废弃 NSBluetoothPeripheralUsageDescription 替换为 NSBluetoothAlwaysUsageDescription

解决办法：

在info.plist中添加新字段NSBluetoothAlwaysUsageDescription，然后重新上传即可

可参考https://blog.csdn.net/trickGenous/article/details/101016096







