---
layout: post
title: "Win7 cmd脚本一键修改本地连接配置"
description: ""
category: 
tags: []
---
{% include JB/setup %}

在两个地方用电脑办公的同学可能会碰到下面这个情况：

**A地点的本地连接是：自动获取IP**

**B地点的本地连接是：静态IP**

每次切换，都要手动修改，费时费力。

下面提供一个快捷的方法：

建立一个auto.cmd文件，然后用记事本输入如下信息：

{% highlight bash %}
netsh interface ip set address name="本地连接" source=dhcp
netsh interface ip set dns name="本地连接" source=dhcp
{% endhighlight %}

建立一个static.cmd文件，然后用记事本输入如下信息：

{% highlight bash %}
netsh interface ip set address name="本地连接" source=static addr=192.168.17.75 mask=255.255.255.0 gateway=192.168.17.254
netsh interface ip set dns "本地连接" source=static addr=202.118.224.101
{% endhighlight %}

（以上的ip mask gateway dns请根据自身网络环境，进行修改）

对于不同的地点，我们以管理员身份运行不同的脚本实现一键设置。

