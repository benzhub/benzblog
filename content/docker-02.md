---
title: "Docker 教學系列02 image基本操作"
date: 2021-02-02T14:46:10+08:00
description: "Docker 基本操作"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
  - "Docker 教學系列"
---

#### image 下載.使用.製作.上傳
```bash
#查看所有本地的image 檔案
sudo docker image ls -a
#拉下想要的image 檔案
sudo docker pull hello-world
#啟動image
sudo docker container run hello-world
```

#### 製作自己的image
```bash
#創建目錄
mkdir dockertest001
#進入目錄
cd dockertest001
#創建 Dockerfile
tocuh Dockerfile
#寫入
vim Dockerfile
#用本地當下目錄的Dockerfile 創建 image 
docker build -t lenrich1403/test-image-build .
#創建時帶參數進去
docker build -t lenrich1403/test-image-build002 --build-arg my_name_is="Dan Hooker"
```

#### 上傳製作的image 到自己的DockerHub帳號
```bash
#登入docker 帳號#輸入你的帳號密碼
docker login
#上傳  一定要帶你自己的帳號
docker push lenrich1403/test-image-build
```

#### 清理不需要的image
```bash
docker rmi lenrich1403/test-image-build002
#如果有你使用此image啟動container 
#需要先把container先刪除
docker rm container-ID
docker image rmi lenrich1403/test-image-build002
#強至刪除image 不管他有沒有container
docker image rmi -f lenrich1403/test-image-build002
```
----------------------------------
##### 下一篇我們將會開始進入docker container  的操作
###### [進入下一篇](/docker-03)