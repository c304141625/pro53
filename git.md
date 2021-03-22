# Git

## 一. 了解Git

### 1. 什么是git 

是一种版本控制器 , 在团队开发的时候 , 进行代码管理的工具

流行的版本控制器   Git     SVN 

### 2. 下载安装git

无论看见复选框让你选啥 , 都按下一步就行

安装成功以后 , 在任意目录 , 右键单击 -> git bash here 代表安装成功

### 3. 了解git的分区

* 工作区 : 本地的项目
* 暂存区 : 通过git add 可以把本地的项目上传到暂存区 
* 仓库(版本库) : 存储每一次提交的信息 (日志) 和 项目的版本信息

## 二. 使用Git

### 1. 使用git之前 自报家门

```
git config --global user.name 用户名        告诉git你是谁
git config --global user.email 邮箱    	  告诉git怎么联系你
```

### 2. 初始化git

* 在项目目录中 右键 选择 git bash here
* 输入初始化命令 会生成一个 .git 的隐藏目录 

```
git init
```

### 3. git 命令

* 添加文件 -> 暂存区

```
gid add 文件名   
	例如: git add 1.php
git add .  把项目区的所有文件 提交到 暂存区中 
git status 查看暂存区的状态

把暂存区的内容 提交到 仓库中 
git commit -m "此次提交的说明信息"
```

* 删除文件 

```
git rm 文件名    删除本地文件的同时 把 删除请求 提交到了暂存区  

通过
git commit -m "del说明"
把暂存区的删除请求提交到仓库中 删除了仓库中的文件
```

* 版本退回

```
git log 查看每一次的历史版本  记住 想退回那个版本的commit码的 前8位   9477aa64

git reset --hard 前8位码
	例如 git reset --hare 9477aa64
```

* git 忽略追踪

```
1. 创建出一个 .gitignore 的文件 
2. 把不希望git追踪的文件名字 放进去 如果 多个文件 用换行分割 
```

* 分支管理

```
查看分支
git branch
创建分支
git branch 分支名
切换分支
git checkout 分支名
合并分支   往主分支上合并  
git checkout master  切换到主分支
git merge 分支名     合并分支
删除分支
git branch -d 分支名   一定要合并以后才能删除这个分支
git branch -D 分支名   没有合并的分支 , 一定要用-D 才能删除

快速创建并且切换分支
git checkout -b fanren
```

## 三.利用远程仓库GitHub管理项目

远程项目的托管平台 , 官网: https://github.com/

注册一个github 的帐号 , 右上角 sign up

进入 , 单机左上角+ new re....   创建一个新的仓库

* 通过git远程的项目克隆到本地

```
git clone 远程仓库的网址
```

* 把本地的仓库提交到 github仓库上面去 

```
git remote add origin github网址   链接远程的仓库 (域名看你自己的)
   例如 git remote add origin https://github.com/c304141625/pro53.git   链接远程的仓库 (域名看你自己的)
   
git push origin 本地分支:远程的分支 (默认 main)
	例如 git push origin master
```

