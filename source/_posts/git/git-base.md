---
title: git - 基础命令清单
abbrlink: e930fae2
date: 2019-08-30
tags: 
  - git
  - 语法
categories: git
---
常用的git基础命令清单总结。
<!-- more -->
[参考：阮一峰网络日志](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

#### 新建代码库
##### 在当前目录新建一个Git代码库
```git init```

##### 新建一个目录，将其初始化为Git代码库
```git init [project-name]```

##### 下载一个项目和它的整个代码历史
```git clone [url]```

#### 提交代码到远程仓库的流程
##### 添加当前目录的所有文件到暂存区
```git add .```

##### 提交暂存区到仓库区
```git commit -m [提交信息]```

##### 拉取远程仓库到本地代码库
```git pull [远程仓库名] [分支名]```

##### 提交暂存区到远程仓库
```git push [远程仓库名] [分支名]```

#### 分支
##### 列出所有本地分支
```git branch```

##### 列出所有远程分支
```git branch -r```

##### 列出所有本地分支和远程分支
```git branch -a```

##### 新建一个分支，但依然停留在当前分支
```git branch [branch-name]```

##### 新建一个分支，并切换到该分支
```git checkout -b [branch]```

##### 切换到指定分支，并更新工作区
```git checkout [branch-name]```

##### 切换到上一个分支
```git checkout -```

##### 新建一个分支，指向指定commit
```git branch [branch] [commit]```

##### 新建一个分支，与指定的远程分支建立追踪关系
```git branch --track [branch] [remote-branch]```

##### 合并指定分支到当前分支
```git merge [branch]```

##### 选择一个commit，合并进当前分支
```git cherry-pick [commit]```

##### 删除分支
```git branch -d [branch-name]```

##### 删除远程分支
```git push origin --delete [branch-name]```
```git branch -dr [remote/branch]```

#### 查看信息
##### 显示有变更的文件
```git status```

##### 显示当前分支的版本历史
```git log```

##### 显示过去5次提交
```git log -5 --pretty --oneline```

##### 显示指定文件是什么人在什么时间修改过
```git blame [file]```

#### 远程仓库
##### 显示所有远程仓库
```git remote -v```

##### 增加一个新的远程仓库，并命名
```git remote add [远程仓库命名] [远程仓库url]```