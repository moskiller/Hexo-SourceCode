---
title: git备份hexo源代码的方法
date: 2018-11-09 11:09:23
tags: git hexo
categories: 学习笔记
---
### 前言

我的博客站点是使用 hexo + github 搭建的，在 github 上作为一个单独的 github 仓库存在，搭建完成的当晚，我在家里心血来潮想发一篇博文的时候才发现只能在存放着 Hexo 源代码的那台电脑上更新才行，虽然可以通过 Teamviewer 远程操作更新，但比较麻烦，而且我又担心某天会不小心删除了某个文件，那就杯具了，所以上网找了一个方法进行操作，发现是可行的，特记录下来备用。
<!-- more -->
### 0x00 备份方法
* 首先在你的 Github下 创建一个新的repo，取名为Hexo-SourceCode。这个仓库名你随意起，我的是Hexo-SourceCode)

> **以下是确保下列命令可正常运行的先决条件：**
> 1. 已安装 git
> 2. 已设置好 SSH 


* 打开命令行界面，cd进入本地的Hexo文件夹，执行以下命令创建仓库:
```
 cd xxx.github.io //这里是你的本地博客目录 

 git init         //初始化 git
```
* 继续执行下面命令设置远程仓库地址以及更新:
```
//将下面的xxx替换为你的github用户名，Hexo-SourceCode是你创建的那个源代码备份仓库名

 git remote add origin git@github.com:xxx/Hexo-SourceCode

 git pull origin master //拉取备份仓库上的文件
```

* 最后执行命令以下命令，完成Hexo源代码在本地的提交
```
 git add .  // 将本地文件所有修改添加到暂存区

 git commit -m  "添加HEXO源代码文件作为备份" //将暂存区里的改动提交到本地的版本库
```
*   执行以下命令，将本地的仓库文件推送到Github。
```
git push origin master
```
* 等待命令成功完成后，你的Hexo源代码就会上传到 github 上备份了，收工！  
  
***  
### 0x01 博客更新后同步到远程仓库

* 在本地编写完博客时，顺次执行以下命令，即可完成Hexo博客源文件的更新同步，保持 Github 上的 hexo 源代码为最新版本。
```
 git add . 
 git commit -m "更新 Hexo 源文件"
 git push origin master
```
### 0x02 远程仓库更新后同步到本地仓库

* 当远程仓库有更新时，执行以下命令，即可同步hexo源文件到本地。
```
 git pull origin master
```
### 0x03 在备份时可能会遇到的问题
* 远程仓库上的某个文件确认不再需要时，可使用以下命令进行删除:
```
 git rm -f --cached FileName // 删除远程仓库的某个文件，将 FileName 替换为你想删除的文件名
 git commit -m "删除文件的说明" // 添加操作说明，将暂存区里的改动提交到本地的版本库
 git push -u origin master // 将本次更改更新到远程仓库上。
```
* 在git commit时出现 "Changes not staged for commit: modified:  xxx/yyy (modified content, untracked content) 的错误提示
```
// 原因: xxx/yyy 目录下存在.git目录，将它删除就ok了

// windows系统的，进入提示的 xxx / yyy 目录下: 
 rd /s/q .git
 
// linux 或 macos系统的，进入对应的目录下：
 rm -rf .git

//然后重新git add 和 git commit -m xxx 就可以了
```
* git push 的时候出现以下出错提示：
```
> ![rejected] master -> master (non-fast-forward) error: failed to push some refs to 'git@github.com:xxx/xxxx'
> hint: Updates were rejected because a pushed branch tip is behind its remote 
> hint: counterpart. Check out this branch and integrate the remote changes 
> hint: (e.g. 'git pull ...') before pushing again.  
> hint: See the 'Note about fast-forwards' in 'git push --help' for details.


// 原因可能是远程仓库和本地仓库版本冲突导致的。
// 解决方法是在push前一定要将远程仓库pull下来先，再push上去。
 
 git pull origin master // pull下来
 git push -u origin master // push 上去
```

* 不想 merge 远程和本地修改的话，可以创建一个新的分支后，再 push到新的分支上。
```
 git branch test  // 创建本地分支，test是新的分支名
 git checkout test // 切换到新的 test 分支上
 git push origin test:test // 提交本地 test 分支作为远程的t est 分支
```

* 完全清除 git仓库所有提交历史记录的方法
```
1.Checkout

   git checkout --orphan latest_branch

2. Add all the files

   git add -A

3. Commit the changes

   git commit -am "commit message"


4. Delete the branch

   git branch -D master

5.Rename the current branch to master

   git branch -m master

6.Finally, force update your repository

   git push -f origin master
```
