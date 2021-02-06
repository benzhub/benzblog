---
title: "Docker 教學系列07 docker compose的使用介紹"
date: 2021-02-05T14:46:10+08:00
description: "docker compose的使用介紹"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
  - "Docker 教學系列"
---

#### docker compose的Services使用介紹.
```bash
#創建docker-compose 的設定檔案
touch docker-compose.yml

version:"3.7"
services:
  myweb:
    build:
      context: .
      args:
        whoami:"Git"
    image:lenrich1403/nginx:latest
    ports:
      - "8080:80"
    networks:
      - mybridge001
  myweb2:
    build:
      context: .
      args:
        whoami:"Nginx"
    image:lenrich1403/nginx2:latest
    ports:
      - "8081:80"
    networks:
      - mybridge001
  myweb3:
    build:
      context: .
      args:
        whoami:"Laravel"
    image:lenrich1403/nginx3:latest
    ports:
      - "8082:80"
    networks:
      - mybridge001
  myweb4:
    image:lenrich1403/nginx3:latest
    ports:
      - "8083:80"
    networks:
      - mybridge002
  myweb5:
    image:lenrich1403/nginx3:latest
    ports:
      - "8084:80"
    networks:
      - mybridge002
    volumes:
      - main-vol002:/etc/nginx

networks:
  mybridge001:
  mybridge002:

volumes:
  main-vol002:


#docker-compose建立
sudo docker-compose build --no-cache
#用docker-compose 背景執行啟動
sudo docker-compose up -d
#刪除/下架所有用docker-compose啟動的container
sudo docker-compose down

```

----------------------------------
##### 下一篇我們將會開始進入docker實戰應用在專案佈署上
###### [進入下一篇](/docker-08)