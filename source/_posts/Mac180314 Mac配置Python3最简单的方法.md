---
title: Mac配置Python3最简单的方法
catalog: true
comments: true
date: 2018-03-14 14:00:00
subtitle: The easiest way to configure Python3 for Mac
header-img: mac-bg.png
tags:
- Python3
- Python2
- MacBook
categories:
- Mac
---

![The First Title Picture](Mac180314 Mac配置Python3最简单的方法/mac-0002.png "Optional Title")

**此文介绍Mac用Anaconda配置Python3**
<!-- more -->
# 达成效果

能让你目前只装有Python2的Mac装上Python3，同时拥有很多科学计算库

# anaconda介绍
anaconda 是一个python的发行版，包括了python和很多常见的软件库, 和一个包管理器conda。常见的科学计算类的库都包含在里面了，使得安装比常规python安装要容易。
装了anaconda就不需要装python了。

# 安装步骤
1.下载

首先去[清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)找到你Mac的版本进行下载，根据你的喜好安装有界面的版本或者命令行版本，然后直接安装即可

2.确认安装结果

安装完成后，在终端测试一下安装结果

输入python或ipython等命令，如果看到相应的结果，说明安装成功

3.修改包管理镜像源

安装成功之后，修改其包管理镜像为国内源

在终端中分别运行下面的2个命令：
```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes
```

设置镜像的目的，是因为原生的镜像在国外，在配置下载的时候可能会很慢，国内的镜像速度就很快

基本上到这一步，你的Mac就已经配置好了基本的Python3环境

然后你还想折腾着换着用Python2什么的话就看第4步

4.添加Python2

在终端输入以下命令：
```
conda create -n py27 python=2.7
```
其中py27是新添加环境的名字，可以自定义修改。

之后通过activate py27和deactivate py27命令激活、退出该环境。（Linux和OS系统的命令似乎是source activate和source deactivate）
```
activate py27
```

---



