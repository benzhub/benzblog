---
title: "Git 教學系列01 git常用指令整理"
date: 2021-02-05T18:46:10+08:00
description: "git常用指令整理"
type: "post"
image: "images/git-logo.png"
categories: 
  - "Git"
tags:
  - "Git"
  - "Git 教學系列"
---

#### git 四種檔案狀態介紹..

1. untracked (未追蹤的，代表尚未被加入 Git 儲存庫的檔案狀態)
1. unmodified (未修改的，代表檔案第一次被加入，或是檔案內容與 HEAD 內容一致的狀態)
1. modified (已修改的，代表檔案已經被編輯過，或是檔案內容與 HEAD 內容不一致的狀態)
1. staged (等待被 commit 的，代表下次執行 git commit 會將這些檔案全部送入版本庫)

#### git常用指令整理. 
```bash
#當前資料夾建立一個 Git 儲存庫
git init

#編輯中的test.js要回覆上一個commit狀態
git checkout master test.js
#把工作目錄也給還原到目前的最新版(commit)(一次把所有檔案都給還原了)
git reset --hard
#還原指定commit
git reset --hard <commit ID>

#檢查git 狀態
git status -s
#查看修改了哪些地方
git diff

#真正把「刪除」的狀態寫進索引檔
git rm test.txt
#只刪除索引檔中的該檔，又要保留工作目錄下的實體檔案
git rm --cached test.txt 

#檔案更名，同時更新索引與變更工作目錄下的實體檔案
git mv oldname newname

#將untrack 的檔案全部加入git 倉庫
git add .
#建立git commit節點
git commit -m "message"

#查看git 所有commit,並且每個單行
git log --oneline
#簡易圖形化 所有commit,並且每個單行
git log --graph --oneline

#查看所有分支，查看目前所在分支
git branch
#建立新分支
git branch newbranch1
#建立分支，並將目前工作目錄切換到新的分支
git checkout -b <branch_name>
#刪除分支
git branch -d <branch_name>
#切換分支
git checkout <branch_name>

#從遠端git倉庫的master分支拉下最新git commit
git pull origin master
#推送本地git的master分支到遠端的git倉庫的master分支上
git push origin master
#如果本地的git分支名字跟遠端git倉庫的master分支名字不同,使用強制HEAD
git push origin HEAD:master
#推送時將本地git commits強制覆蓋遠端git倉庫commits
git push origin master -f
#查看所有遠端倉庫名稱和對應地址
git remote -v
#添加遠端倉庫名稱和對應地址
git remote add <short_name> <repo_url>
```

----------------------------------
##### 下一篇我們將會介紹大家使用ssh榜定最常用遠端Git倉庫(github/gitlab)
###### [進入下一篇](/git-02)