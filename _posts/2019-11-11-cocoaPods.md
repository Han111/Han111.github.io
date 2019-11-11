---
layout: post
title: "CocoaPods最新安装和问题解决教程（干货）"
subtitle: ''
author: "Han"
header-style: text
tags:
  - CocoaPods
---

CocoaPods是什么不多说，自己网上去查。今天主要讲CocoaPods的安装问题：

1.（这是原来的，请看下面的更新）首先用淘宝的Ruby镜像来访问CocoaPods，打开终端输入以下命令：

（1）gem sources --remove http://ruby.taobao.org/

（2）gem sources -a https://ruby.taobao.org/

（3）gem sources -l

更新：淘宝源不能用了，可以用Ruby China 社区专注维护的这个源（https://gems.ruby-china.org/ ）。

更新：https://gems.ruby-china.org/需要换成https://gems.ruby-china.com/

首先，执行以下命令删除原来的ruby源：

gem sources --remove https://rubygems.org/

执行命令后可在终端看见以下信息：

https://rubygems.org/ removed from sources

然后下一步添加你找到的可用的镜像源：

gem sources -a https://gems.ruby-china.com/

验证新源是否替换成功：

gem sources -l

只有在终端中出现下面文字才表明你上面的命令是成功的：

*** CURRENT SOURCES ***

2.更新升级gem，如果它的版本过低也可能导致安装失败，在终端输入以下命令：

sudo gem update --system

3.安装CocoaPods:

OS X 10.11以前，在终端输入以下命令：

sudo gem install cocoapods

OS X 10.11以后，在终端输入以下命令：

sudo gem install -n /usr/local/bin cocoapods

4.初始化：

在终端输入以下命令：

pod setup

问题最多的就是这一步，第一次安装完成可能要一个小时左右，所以要耐心等待，如果这一步完成了，那么恭喜你已经成功安装了CocoaPods。想知道自己有没有安装完成，可以在终端输入以下命令：

pod --version

显示出版本就说明成功了。

5.问题梳理：

（1）在终端输入以下命令：

pod repo list

结果为0 repos时说明安装不成功，自己可以查看下自己的安装步骤，看看是哪一步出现了问题。

（2）出现以下错误：

ERROR:  While executing gem ... (Errno::EPERM)

Operation not permitted - /usr/bin/xcodeproj

在网上寻找的解决方法：

在终端中输入：sudo nvram boot-args="rootless=0"; sudo reboot

然后你的电脑会重启

之后再输入sudo gem install cocoapods -V

就可以了。

（3）pod setup时出现以下错误：

[!] /usr/bin/git clone https://github.com/CocoaPods/Specs.git master

Cloning into 'master'...

error: RPC failed; curl 56 SSLRead() return error -36

fatal: The remote end hung up unexpectedly

fatal: early EOF

fatal: index-pack failed

You can try adding it manually in `~/.cocoapods/repos` or via `pod repo add`.

自己按照提示在终端输入以下命令：

pod repo add master https://github.com/CocoaPods/Specs.git

还是报错！

在网上查到的解决办法：在终端输入以下命令：

sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer

后面的地址你可以打开Xcode显示包内容，找到那个文件夹拖到终端里面。

（4）试过以上所有解决办法，还是没有安装成功：

重新安装（其实我就是这样安装成功的）：

首先，删除.cocoapods目录，在终端输入以下命令：

sudo rm -rf ~/.cocoapods/

然后，重新下载安装，在终端输入以下命令：

pod setup

ps：很多人说这两句解决了他们的问题

$ sudo gem install -n /usr/local/bin cocoapods

$ Git clone https://git.coding.net/CocoaPods/Specs.git ~/.cocoapods/repos/master







