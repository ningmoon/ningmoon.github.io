---
title: 用Hexo + Github Pages搭建你的个人博客
catalog: true
comments: true
date: 2018-04-18 22:00:00
subtitle: Build Your Personal Blog with Hexo + Github Pages
header-img: hexo-bg.jpg
tags:
- Hexo
- Git
- Blog
categories:
- Hexo

---
![The First Title Picture](Hexo180418 用Hexo + Github Pages搭建你的个人博客/hexo-0002.png "Optional Title")

<!-- more -->

**本文介绍使用Hexo + Github Pages搭建个人独立博客**

# 1 写在最前面

Blog可能已经过了最火热的时代，特别是现在又要自己折腾一个个人的独立博客，反反复复，停停走走，最后还是下了决心决定自己搭建一个博客。

之所以想要建立一个自己的个人博客，想让自己在写博客的过程又有新的收获。

[出处](https://zhuanlan.zhihu.com/p/19743861?columnSlug=cnfeat)

**“提高将事情讲清楚的能力” **

> <p align="left">在写博客之前你需要花更多的时间来表达出你的想法，表达你想法之前你得先对你要表达的东西充分理解并理清思路和逻辑。很多东西你以为懂了，但当你在写下来的时候，你就觉得无从下手了。</p>

**分享带来的连锁反应**

> <p align="left">“通过分享，你获得了直接而快速的回报，你最终或许会发现你已将版权和“保留所有权利”抛诸脑后。新的经济学准则是：参与你作品的人越多，回报越高。在分享主义里，如果你愿意你可以保留所有权，但是我乐于分享。” by 毛向辉 《分享主义：一场思维革命》</p>

**记录成长**
> <p align="left">我们每个人都应该有这样的经历:隔了很久我们回头看看以前的自己会发现特别傻x,但正是因为这些傻x的岁月让我们不断成长,你在成长的过程中不断的修正自己的错误。</p>

**探索未知的世界**
> <p align="left">世界不止是你的家，你的公司，你的朋友圈，你应该去发现一个更大的世界，通过写博客，你会知道世界上还有很多人像你一样在写博客，这些人和知识正在世界的某个角落在等着你。</p>

**帮助更多想要获取帮助的人**
> <p align="left">这点我相信大家由为感触,在你探索一个未知的知识领域的时候,往往被撞的一鼻子灰.幸运的人很快就能找到一个“师傅”或一篇很好的文章,但大多数往往在找“教程”的过程中就已经放弃了.因为他们没能够找到刚好理解的文章.</p>

# 2 系统环境配置
要使用Hexo，就需要在系统中安装Nodejs以及Git。
**[安装Nodejs](https://nodejs.org/en/download/)**
**[安装Git](https://git-scm.com/download/)**
**安装Hexo
```python
$ cd ~/hexo
$ npm install hexo-cli -g
$ hexo init blog
$ cd blog
$ npm install
$ hexo g # 或者hexo generate
$ hexo s # 或者hexo server，可以在http://localhost:4000/ 查看
```
这里有必要提下Hexo常用的几个命令：
```python
hexo generate (hexo g)#生成静态文件，会在当前目录下生成一个新的叫做public的文件夹
hexo server (hexo s) #启动本地web服务，用于博客的预览
hexo deploy (hexo d) #部署播客到远端（比如github, heroku等平台）
```
另外还有其他几个常用命令：
```python
$ hexo new "postName" #新建文章
$ hexo new page "pageName" #新建页面
```
常用简写
```python
$ hexo n == hexo new
$ hexo g == hexo generate
$ hexo s == hexo server
$ hexo d == hexo deploy
```
常用组合
```python
$ hexo d -g #生成部署
$ hexo s -g #生成预览
```
现在我们打开http://localhost:4000/ 已经可以看到一篇内置的blog了。

目前我安装所用的本地环境如下：(通过hexo -v查看)
```
hexo: 3.5.0
hexo-cli: 1.0.4
os: Darwin 17.3.0 darwin x64
http_parser: 2.7.0
node: 8.9.4
v8: 6.1.534.50
uv: 1.15.0
zlib: 1.2.11
ares: 1.10.1-DEV
modules: 57
nghttp2: 1.25.0
openssl: 1.0.2n
icu: 59.1
unicode: 9.0
cldr: 31.0.1
tz: 2017b
```
# 3 Hexo主题设置
这里以主题light为例进行说明。

安装主题
```python
$ hexo clean
$ git clone git clone git://github.com/tommy351/hexo-theme-light.git themes/light
```
启用主题
修改Hexo目录下的_config.yml配置文件中的theme属性，将其设置为light。

更新主题
```python
$ cd themes/light
$ git pull
$ hexo g # 生成
$ hexo s # 启动本地web服务器
```
现在打开http://localhost:4000/ ，会看到我们已经应用了一个新的主题。

# 4 Github Pages设置
GitHub Pages 本用于介绍托管在GitHub的项目，不过，由于他的空间免费稳定，用来做搭建一个博客再好不过了。

每个帐号只能有一个仓库来存放个人主页，而且仓库的名字必须是username/username.github.io，这是特殊的命名约定。你可以通过http://username.github.io 来访问你的个人主页。(这里特别提醒一下，需要注意的个人主页的网站内容是在master分支下的。)

创建自己的Github Pages
注册GitHub及使用Github Pages的过程不做赘述，创建之后创建一个github repo叫做 xxx(your username).github.io. 创建完成之后，需要有一次提交(git commit)操作，然后就可以通过链接http://xxx(your username).github.io/ 访问了。



# 5 部署Hexo到Github Pages
有了上一步的基础，这一步是将我们本地的web部署到github上，然后就可以通过http://xxx(your username).github.io/ 直接访问了。

首先需要明白所谓部署到github的原理。

之前步骤中在Github上创建的那个特别的repo（xxx(your username).github.io）一个最大的特点就是其master中的html静态文件，可以通过链接http://xxx(your username).github.io来直接访问。

Hexo -g 会生成一个静态网站（第一次会生成一个public目录），这个静态文件可以直接访问。

需要将hexo生成的静态网站，提交(git commit)到github上。

明白了原理，怎么做自然就清晰了。

可以参考下面的图片：
![](Hexo180418 用Hexo + Github Pages搭建你的个人博客/hexo-0003.png "Optional Title")

如果还不明白，可以自己做做功课补习一下。

使用hexo deploy部署
hexo deploy可以部署到很多平台，具体可以参考这个[链接](https://hexo.io/docs/deployment.html). 如果部署到github，需要在配置文件_config.xml中作如下修改：
```python
deploy:
  type: git
  repo: git@github.com:xxx(your username).github.io.git
  branch: master
```
然后在命令行中执行
```
hexo d
```
即可完成部署。

要能成功部署，需要提前安装一个扩展：
```
$ npm install hexo-deployer-git --save
```

使用git命令行部署
使用hexo depoly确实很方便，但是有的时候会出现一些bug，所以个人还是更喜欢直接用Git命令来完成部署。

clone github repo 进入你的blog文件夹，然后clone你的GitHub repo
```
$ git clone https://github.com/xxx/xxx(your username).github.io.git .deploy/xxx(your username).github.io
```
上一行代码的意思是将我们之前创建的repo克隆到本地的一个叫做.deploy的新建的文件夹用于存放克隆的代码。


将下面的代码直接封装成sh，每次需要部署的时候直接bash执行就行。

具体每行代码的意思见注释。
```python
cp -R public/* .deploy/xxx(your username).github.io
#这一行是复制blog下面的public中的网页代码到我们Git的本地文件夹
cd .deploy/xxx(your username).github.io
#进入这个本地的Git文件夹
git add .
#加载此文件夹下面所有的文件
git commit -m “update”
#提交代码
git push 
#push到GitHub上
```

到这里你的个人博客基本框架搭建起来了，这里根据你自己所选的主题配置的不同，你的个性化设置也可以不一样，有很多的配置，现在不熟悉也没有关系，可以慢慢的摸索，后面我还会分享一些个人搭建过程中的小小心得经验。

