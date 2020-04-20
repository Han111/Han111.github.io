---
layout: post
title: "解决Unexpected end of JSON input while parsing near 问题"
subtitle: ''
author: "Han"
header-style: text
tags:
  - npm
---

执行npm install命令的时候报错Unexpected end of JSON input while parsing near 

解决：

终端执行命令npm cache clean --force

完成后再执行命令npm install







