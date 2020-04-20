---
layout: post
title: "Xcode11上传ipa报错：App Store Connect Operation Error"
subtitle: ''
author: "Han"
header-style: text
tags:
  - 苹果审核
---

今天上传App到App Store，出现了App Store Connect Operation Error。An error occurred uploading to the App Store。除此之外没有任何其他信息，邮箱也没有苹果发来的报错信息。

经过一番研究发现是iTMSTransporter被损坏了，导致一直上传不了App。最后用xcrun altool命令上传成功。故此记录一下，希望有同样问题出现的人可以少走点弯路。

解决办法参考：

https://www.jianshu.com/p/af9f8f64f1cd

https://www.jianshu.com/p/031cec0feb1a






