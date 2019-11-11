---
layout: post
title: "Your app uses the "prefs:root="审核被拒"
subtitle: ''
author: "Han"
header-style: text
tags:
  - 苹果审核
---

近期上线一个app，苹果发来一封邮件提示为审核被拒：

Guideline 2.5.1 - Performance - Software Requirements

Your app uses the "prefs:root=" non-public URL scheme, which is a private entity. The use of non-public APIs is not permitted on the App Store because it can lead to a poor user experience should these APIs change.

Continuing to use or conceal non-public APIs in future submissions of this app may result in the termination of your Apple Developer account, as well as removal of all associated apps from the App Store.

Next Steps

To resolve this issue, please revise your app to provide the associated functionality using public APIs or remove the functionality using the "prefs:root" or "App-Prefs:root" URL scheme.

If there are no alternatives for providing the functionality your app requires, you can file an enhancement request.

原因是App Store上不允许使用非公共API，现在不允许"prefs:root="这种写法了。

解决办法：

1、全局搜索prefs:root=，改掉这些代码。

2、中间进行一次转码操作，此方法未亲自测试。具体可看：https://www.jianshu.com/p/a94cd8103bba







