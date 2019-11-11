---
layout: post
title: "Can't find gem cocoapods"
subtitle: ''
author: "Han"
header-style: text
tags:
  - CocoaPods
---

今天pod install后出现了这样一个问题：

Ignoring byebug-10.0.2 because its extensions are not built. Try: gem pristine byebug --version 10.0.2

/Library/Ruby/Site/2.3.0/rubygems.rb:289:in `find_spec_for_exe': can't find gem cocoapods (>= 0.a) with executable pod (Gem::GemNotFoundException)

from /Library/Ruby/Site/2.3.0/rubygems.rb:308:in `activate_bin_path'

from /usr/local/bin/pod:23:in `<main>'

估计是我什么时候一不小心把cocoapods删了。

终端输入以下一条命令解决：

sudo gem install -n /usr/local/bin cocoapods






