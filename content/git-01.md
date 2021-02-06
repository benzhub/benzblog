---
title: "Git 教學系列01 git常用指令整理"
date: 2021-02-05T14:46:10+08:00
description: "git常用指令整理"
type: "post"
image: "images/git-logo.png"
categories: 
  - "Git"
tags:
  - "Git"
  - "Git 教學系列"
---
#### git常用指令整理. 
```bash
#編輯中的test.js要回覆上一個commit狀態
sudo git checkout master test.js
#檢查git 狀態
sudo git status -s
#將untrack 的檔案全部加入git 倉庫
sudo git add .
#建立git commit節點
sudo git commit -m "message"
#查看git 所有commit,並且每個單行
sudo git log --oneline
#簡易圖形化 所有commit,並且每個單行
sudo git log --graph --oneline
#查看所有分支
sudo git branch
#從遠端git倉庫的master分支拉下最新git commit
sudo git pull origin master
#推送本地git的master分支到遠端的git倉庫的master分支上
sudo git push origin master
#如果本地的git分支名字跟遠端git倉庫的master分支名字不同,使用強制HEAD
sudo git push origin HEAD:master
#推送時強制覆蓋所有commit
sudo git push origin master -f
```

----------------------------------
##### 下一篇我們將會介紹大家使用ssh榜定最常用遠端Git倉庫(github/gitlab)
###### [進入下一篇](/git-02)