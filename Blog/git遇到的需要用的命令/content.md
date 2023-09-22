# git遇到的需要用到的命令
[TOC]
## 新电脑配置git环境（windows）
全程按照[这个](https://blog.csdn.net/u012124199/article/details/114004087)就行。记得镜像下载，不然会很慢。
## 自己本地已经有仓库和只有git上有仓库不同
在第三方平台登录git时，用户名和昵称不同，注意辨别。
打开gitee新建一个仓库就行 里面写的很详细
## 查看远程仓库信息
有时候配置好了之后  不是很放心有没有配置完成，这个时候就需要一定的**远程仓库查看**
```dotnetcli
git remote -v
git remote show origin
```
上面的是查看远程仓库的**地址**
下面是更多信息，比如说**各个分支**的情况等等。
## 撤销删除本地仓库中已有的git init
进入文件夹之后，输入
```dotnetcli
rmdir /s /q .git 
```
只要删除了这个.git文件夹，就实现了脱离版本控制
## 更改全局的用户名和邮箱
```dotnetcli
git config --global user.name "wca_admin"
git config --global user.email "602514418@qq.com"
```
查看两种信息
```dotnetcli
git config --global user.name
git config --global user.email
```
## 配置ssh免密登录
+ 首先进入目录例如C:\Users\admin\\.ssh
+ 生成密钥对（如果已经有了就不用重新生成了）
```dotnetcli
ssh-keygen -t rsa -C "邮箱"
```
+ 之后用记事本打开这个文件并且复制
+ 右上角点头像然后设置，里面找到ssh什么什么的

## 打tag来进行版本标注
### 本地标注标签
```dotnetcli
git tag -a v1.0 -m "v1.0"
```
### 一次性推送所有标签到远程
```dotnetcli
git push origin --tags
```

## 查看所有分支
```dotnetcli
git branch -a
```
## 实现远程仓库覆盖本地
远程仓库名根据实际调整
```dotnetcli
git fetch --all

git reset --hard remotes/origin/master

git pull
```
## gitea推送到github上
>参考[教程](https://docs.gitea.com/zh-cn/1.20/usage/repo-mirror)

我设置的是90天的 如果时间到了就要再重新设置
我的这个token如下（因为再也看不到了 就复制到这里）
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