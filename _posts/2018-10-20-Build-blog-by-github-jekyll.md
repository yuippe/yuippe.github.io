### github+jekyll 博客搭建

------

[TOC]

#### 背景

搭建网上博客，记录日常点滴，不仅限于IT相关

#### 步骤

##### 一、github环境准备

1、在[官网](https://github.com/)注册账号

2、找个[模板](https://github.com/yuippe/yuippe.github.io)去Fork下来，(模板随意，自己喜欢即可)

3、点击Settings，修改对应的Repository name，其中前缀需要与自己的账号一致

![image01](self_pic/2018-10-20/2018-10-20-12-39-00.png)

4、向下滚动页面，选择一个主题，如果看到2步骤所示内容，即可远程访问

![image02](self_pic\2018-10-20/2018-10-20_124035.png)

##### 二、git环境+代码拉取

1、本地安装git软件

2、在本地git上生成密钥和公钥，分别是id_rsa/id_rsa.pub，文件路径一般如下所示:

```javascript
C:\Users\<用户名>\.ssh\
##如果没有生成代码
ssh-keygen -t rsa -C "邮箱地址"
#一路回车即可
```

3、登录github，打开setting->SSH and GPG keys，点击右上角New SSH Key，把生成好的公钥id_rsa.pub中的内容放入到key输入框中即可。内容可以通过如下方式获取：

```shell
##打开git bash
cd ~/.ssh
cat id_rsa.pub
```

4、通过git bash进入拉取代码所在目录，然后直接拉取对应代码

```shell
git clone --depth=1 https://github.com/yuippe/yuippe.github.io.git
```

> 备注：
>
> github一般比较慢，可以通过修改etc/hosts方式，最好是中国白天

##### 三、jekyll安装+本地代码运行

1、下载对应[ruby+devkit](https://github.com/oneclick/rubyinstaller2/releases/download/rubyinstaller-2.4.4-2/rubyinstaller-devkit-2.4.4-2-x64.exe)软件，这里我选择的版本是Ruby+DevKit2.4.4-2(x64)

2、下载下来直接安装即可，在安装目录下，将gem升级到最新，[gem国内地址](https://gems.ruby-china.com/)

```powershell
C:\Ruby24-x64\bin
```

3、然后直接安装jekyll即可

```powershell
gem install jekyll
##安装后，进入到拉取下来的代码目录中
cd E:\github\yuippe.github.io
jekyll serve
```

![image03](self_pic/2018-10-20/2018-10-20_131443.png)

> 备注：
>
> 启动时可能有报错，如果是依赖性就 gem install  依赖包 即可

