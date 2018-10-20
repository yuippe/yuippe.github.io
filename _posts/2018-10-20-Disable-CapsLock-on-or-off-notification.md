### Disable CapsLock on/off notification in sony vaio laptop

------

[TOC]

#### 背景

sony e14p老笔记本在按大小键切换时，右下角会出现小提示框。

比较尴尬的是，一切换，当前焦点会转移到这个提示窗口，尤其在写代码时很是郁闷，需要禁用这个提示。



#### 解决方案

*步骤如下：*

1. *输入regedit，在start-run中*

2. *找到HKEY_LOCAL_MACHINE\SOFTWARE\ATHEROS\VistaAddOn\KBNotify*

   ![image01](self_pic/2018-10-20/2018-10-20-12-11-00.png)

3. *将其值从1设置成0*

4. *重启电脑即可*