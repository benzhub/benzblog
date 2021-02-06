---
title: "Docker 教學系列03 container基本操作"
date: 2021-02-03T14:46:10+08:00
description: "Docker container基本操作"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
  - "Docker 教學系列"
---

#### container 基本操作.
```bash
#先下載我們需要的映像檔
sudo docker pull alpine
#啟動alpine 的container 並命名為c001並且查看啟動的container的根目錄
sudo docker run --name c001 alpine:latest ls /
#-it互動模式 可以進去container 打shell的指令
sudo docker run -it --name c003 alpine:latest /bin/sh
#讓container 可以在背景不斷執行的指令
sudo docker run -d --name c004 alpine:latest tail -f /dev/null
#exec進入container 可以進去做sh指令
sudo docker exec -it c004 /bin/sh
#離開container 
exit
#container 端口映射
#拉下最新版本的nginx image
sudo docker pull nginx:latest
#啟動nginx的container 並且映射對應的端口
sudo docker run -d --name c006 -p 8088:80 nginx:latest 
#停止container 
sudo docker stop c006
#刪除container 
sudo docker rm c006
#container啟動中強制刪除
sudo docker rm -f c006
```

----------------------------------
##### 下一篇我們將會開始進入Dockerfile的實做
###### [進入下一篇](/docker-04)