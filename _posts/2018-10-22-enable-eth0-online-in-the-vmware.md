---
layout: post
title:  "enable eth0 online in the vmware"
date:   2018-10-22 23:57:18 +0800
categories: tips
tags: vmware10 eth0 online
author: yuippe

---

[TOC]

#### 背景

在VMware10中安装好centos6.8，然后通过ping www.baidu.com，发现无法识别域名，本地也没有IP（如下所示），初步定位是网卡没有配置，并且没有开启服务。

![image00]({{ "/self_pic/2018-10-22/2018-10-22_223125.png" | absolute }})

下面针对此情况，进行配置。

#### 解决方案

*步骤如下：*

1. *在vmware选中对应虚拟机，点击设置，然后在硬件tab页中选中网络适配器，将网络连接选中桥接模式*

   ![image01]({{ "/self_pic/2018-10-22/2018-10-23_000234.png" | absolute }})

2. *找到网卡对应配置文件*

   ```shell
   cd /etc/sysconfig/network-scripts/
   vim ifcfg-eth0
   #将ONBOOT=no改为yes
   ```

   ![image03]({{ "/self_pic/2018-10-22/2018-10-22_223338.png" | absolute }})

3. *重新启动网卡*

   ```shell
   /etc/init.d/network restart
   ```

   ![image04]({{ "/self_pic/2018-10-22/2018-10-22_223417.png" | absolute }})

4. *检查网卡信息*

   ```shell
   ifconfig eth0
   ```

   ![image05]({{ "/self_pic\2018-10-22\2018-10-22_223514.png" | absolute }})