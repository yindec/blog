---
title: "git command"
date: 2023-05-19T23:43:57+08:00
author: "yindec"
description: "常用git命令"
tags: ["git","blog"]
---
### 推送
`git push (-u) origin <local_branch> : <remote_branch>` 推送 <local_branch>给 <remote_branch>，追踪取决于`-u`。

`<local_branch> `可省略，代表删除origin主机上的:<remote_branch>分支

`: <remote_branch>`可省略，代表<local_branch>推送到origin上面同名的远程分支，如果没有，则创建该远程分支，***推荐使用这个形式***。

`git push --set-upstream-to=origin/<remote_branch> <local_branch>` 推送<local_branch>,并追踪<remote_branch>

### ssh秘钥

`ssh-keygen`

## 远程仓库

### 查看远程仓库连接情况

```
$ git remote -v
origin  https://github.com/yindec/yindec.github.io.git (fetch)
origin  https://github.com/yindec/yindec.github.io.git (push)
```

### LF和CTLF换行符设置

```
git config --global core.autocrlf false     # 适用于确定只在win上面使用该项目
git config --global core.autocrlf true      # win默认设置，所以老师弹出警告
git config --global core.autocrlf input 
git config --get core.autocrlf              # 查看
```
进阶设置：比较推荐的做法是使用 `.gitattributes` 指定项目中各类文件适用的换行符



### .gitignore的添加规则

```
node_modules/       # 过滤整个文件夹
*.zip               # 过滤后缀zip文件
demo.html           # 过滤该文件
```

```
!src/              不过滤该文件夹 
!*.js              不过滤后缀.js文件
!index.html        不过滤该文件
```

### 查看/更改用户名和邮箱

```
git config user.name   //获取当前登录的用户
git config user.email  //获取当前登录用户的邮箱

git config --global user.name "userName"        // 修改登陆账号，userName为你的git账号
git config --global user.email "email"          // 修改登陆邮箱，email为你的git邮箱
git config --global user.password "password"    // 修改登陆密码，password为你的git密码，不确定不确定不确定
```
