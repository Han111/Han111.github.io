---
layout: post
title: "解决报错“RuntimeError - [Xcodeproj] Unknown object version.”"
subtitle: ''
author: "Han"
header-style: text
tags:
  - iOS
---

# 解决报错“RuntimeError - [Xcodeproj] Unknown object version.”

1、报错RuntimeError - [Xcodeproj] Unknown object version.

之前更新了一下Mac系统，然后今天在pod install时提示错误：

RuntimeError - [Xcodeproj] Unknown object version.

查找资料发现原因是：Xcode 版本和 CocoaPods 的版本不兼容，需要更新 CocoaPods 

解决办法：终端输入命令

```ruby
gem install cocoapods --pre
```

如果提示没有权限，修改输入命令为：

```ruby
sudo gem install cocoapods --pre
```

更新完CocoaPods后再次install就可以了。如果还不行，可以尝试下命令：

```ruby
sudo gem install -n /usr/local/bin cocoapods
```

2、报错There are no versions of cocoapods-core (= 1.11.3) compatible with your Ruby & RubyGems. Maybe try installing an older version of the gem you're looking for?

在升级CocoaPods的过程中，又出现了上面2这个报错。

原因：Ruby版本和CocoaPods 的版本不兼容，需要升级Ruby。

解决：我这边是用rvm来更新Ruby版本的。[参考链接](https://www.delftstack.com/zh/howto/ruby/update-ruby-version-in-macos)

01、安装rvm

```ruby
curl -sSL https://get.rvm.io | bash -s stable --ruby
```

02、指定版本安装或安装最新版本

安装最新版本

```ruby
rvm install ruby --latest
```

指定版本安装

```ruby
rvm install 2.7.0
```

3、Ruby升级报错Error running 'requirements_osx_brew_update_system ruby-2.7.0'

然后Ruby升级的时候我又遇到了3这个错误。

解决：先运行下面命令，再安装

```ruby
rvm autolibs read-only
```

