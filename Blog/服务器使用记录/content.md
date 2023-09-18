# 服务器使用记录
>只是随笔
[TOC] 
## 查看当前linux系统下所使用的系统
```dotnetcli
uname -a
```
我这个服务器目前显示它的版本是

>Linux hecs-407047 3.10.0-1160.53.1.el7.x86_64 #1 SMP Fri Jan 14 13:59:45 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux  

是华为的一个小套皮，就当**centos**应该就行，我看官网上是这么说的
## 更新版本等
更新yum版本 建议拿到之后就更新一下 中间一路y就可以了
```dotnetcli
yum update
```

## git版本更新(IUS方式)
>该方法虽然方便(也是git官方推荐的方法) 但成功率收到**网络**影响 多试几次

在执行yum update的时候，但是git版本依然是很老的1.8版本，首先尝试在yum中搜索环境中有的git版本，所用命令为
```dotnetcli
yum provides git
```
结果弹出来的四个版本里面都是1.8的很奇怪。在网上找了一个[教程](https://blog.csdn.net/hxj0323/article/details/119751427)是教用IUS的方式来进行git更新的。具体复刻过程步骤如下。
### ①卸载旧版本git
```dotnetcli
yum remove git
```
### ②安装IUS
```dotnetcli
yum install \
https://repo.ius.io/ius-release-el7.rpm \
https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
```
第一次好像因为网络原因失败了，但是两分钟后又好了，看来命令是没有问题的，只和网络有问题
### ③安装对应git版本
这里和教程中就不太一样了，因为版本略微有些变动,具体实现的时候最好到仓库那里，ctrlF搜索一下git，看可以下载什么版本。
```dotnetcli
yum install git236
```
反正我成功了，有的时候卡失败了多尝试几次，或者过段时间再来试试。

## 服务器端口相关
### 查看监听窗口
下面这个只能看监听的 不能准确的看开放的
```dotnetcli
netstat -lnpt
```
### 查看某个特定窗口有没有开放
```dotnetcli
firewall-cmd --query-port=23333/tcp
```
### 开放某个端口
阿里云那边需要打开 系统命令行里面也要设置
```dotnetcli
firewall-cmd --add-port=3000/tcp --permanent
```
### 开放完一定要重新载入一下防火墙
```dotnetcli
firewall-cmd --reload
```

## 快速查看当前主机ip
包括运营商信息 服务器所属城市 服务器所属公司等信息
```dotnetcli
curl cip.cc
```
