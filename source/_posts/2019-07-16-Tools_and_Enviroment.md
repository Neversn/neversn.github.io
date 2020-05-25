---
title: Tools_and_Enviroment
tags:
- env
- tools
- 汇总
categories:
- Env
---

# 

君子生非异也，善假于物也~



---

# Linux
## 终端工具

 - terminator ：**分屏**工具
 - powerline ：vim 和 bash **状态栏**插件
 - tmux : 终端**复用**工具

## shell样式

- oh-my-zsh + autojump

vim ~/.bashrc
```shell
source ~/.git-completion.sh
source ~/.git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=1
export GIT_PS1_SHOWSTASHSTATE=1
export GIT_PS1_SHOWUNTRACKEDFILES=1
export GIT_PS1_SHOWUPSTREAM="verbose git svn"
PS1='\[\033[1;35m\]\u@\h \[\033[1;32m\]\w\[\033[1;31m\]$(__git_ps1 " (%s)")\[\033[1;36m\] \n-> \[\033[0m\]'
```
# Window

## Clover

win7系统，多标签资源管理器。

## virgo

[Git地址](https://github.com/papplampe/virgo) 

多桌面工具


## 任务栏监视工具

1. [TrafficMonitor](https://github.com/zhongyang219/TrafficMonitor/releases)
2. XMeters

## cmder

linux 仿生终端

# Android

## Termux
[安卓linux仿真Terminal--Termux](https://www.jianshu.com/p/5c8678cef499)
[Termux官网](https://f-droid.org/packages/com.termux/)
[新手教程](https://www.jianshu.com/p/74fc2e8db834)
[优化配置](https://www.sqlsec.com/2018/05/termux.html#lg=1&slide=6)

## spacedesk

将电脑屏幕投影到平板手机

[spacedesk](https://spacedesk.net/)

# Dev
## idea intellij
[我的配置策略即备份文件](https://github.com/Neversn/OneConfig/tree/master/Intellij)

## anaconda
### 常识
1. anaconda And conda
[常见误区(英文)](https://jakevdp.github.io/blog/2016/08/25/conda-myths-and-misconceptions/)
[中文翻译](https://blog.csdn.net/qsir/article/details/79354734)
- anaconda: python的一个发行版本（即各种软件包的集合）
- conda : 包管理软件和环境管理器
  [conda 的详细介绍](https://www.jianshu.com/p/17288627b994)
2. conda and pip
> pip可以允许你在任何环境中安装python包，而conda允许你在conda环境中安装任何语言包（包括c语言或者python）

3. jupyter **notebook** 中添加conda新环境
>python -m ipykernel install --user --name your_env_name --display-name your_env_name
[jupyter notebook 添加 conda 环境](https://www.jianshu.com/p/08c20cd3a3ec)

window 下安装

[windows下Anaconda的安装与配置正解(Anaconda入门教程) ](https://www.jb51.net/article/137772.htm)

## notebook
docker 启动的notebook 更改密码后需要重启容器
### 插件安装
   >安装  
   pip install jupyter_nbextensions_configurator
    pip install jupyter_contrib_nbextensions
    启动：  
    jupyter nbextensions_configurator enable --user
    jupyter contrib nbextension install --user    
如果安装后找不到nbextensions这个标签，直接在端口后加/nbextensions访问


##  jdk 
>  1.官网下载JDK
   2.解压缩,放到指定目录
   3.配置环境变量
   4.设置系统默认JDK
 - 测试jdk

 sudo vim ~/.bashrc,文件的末尾追加下面内容:

```shell
#set oracle jdk environment
export JAVA_HOME=/usr/lib/jvm/jdk1.7.0_60  ## 这里要注意目录要换成自己解压的jdk 目录
export JRE_HOME=${JAVA_HOME}/jre  
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib  
export PATH=${JAVA_HOME}/bin:$PATH  
```
##  git
### 配置
配置用户信息：
[参考](https://git-scm.com/book/zh/v1/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-%E9%85%8D%E7%BD%AE-Git)
[别名参考](https://www.cnblogs.com/wntd/p/5888796.html)
>  git config --global user.name "John Doe"
 git config --global user.email johndoe@example.com

> git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"


生成ssh key
>ssh-keygen -t rsa -C "your_email@youremail.com"

## mvn

```shell
M2_HOME=/opt/maven/apache-maven-3.3.9
CLASSPATH=$CLASSPATH:$M2_HOME/lib
PATH=$PATH:$M2_HOME/bin
export   PATH    CLASSPATH   M2_HOME
```
## DBeaver
数据库连接工具

# Browser
## SwitchyOmega 代理插件

[规则列表网址](https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt)

## LastPass

密码保存工具

## Stylish  

去掉chrome新标签页上的推荐框
1.使用插件Stylish  (不知道是不是打开方式不对，没成功)

```
插件Stylish

[id="most-visited"]{display:none}

.*\/chrome\/newtab.*
```

#  Edit
## Typora

超级好用的markdown编辑器

