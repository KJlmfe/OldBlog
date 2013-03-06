---
layout: post
title: "破解金鹏计费系统"
description: ""
category: 
tags: []
---
{% include JB/setup %}

现在的许多大中院校机房普遍采用金鹏计费系统，有一段时间，我经常往机房跑，天哪！一小时一RMB啊！

抱着一个技术研究的心态，我查询了一些资料，最后，想出了一个破解金鹏计费系统的小方案：

**1.开机，用你的学生账号正常登陆机器**

**2.新建一个txt，在里面敲入如下内容：**

{% highlight bash %}
@echo off
ping -n 10 localhost &gt;nul
:begin
taskkill /im CliGold.exe /f /t
taskkill /im Client.exe /f /t
goto begin
{% endhighlight %}

保存为bat文件

**3.双击这个bat文件，然后快速的注销下机（金鹏系统的注销下机功能，不是电脑自身的注销）**

**4.倒数10秒，期待奇迹的发生吧！！！**

**5.这时进入计算机后，千万不要关闭你刚才打开的bat文件**

破解原理：利用批处理技术，每间隔10秒，杀一下金鹏计费系统的进程

**！！！此方法仅作技术研究使用，请勿非法上机。**
