---
title: "Docker 教學系列06 docker volume的介紹"
date: 2021-02-05T14:46:10+08:00
description: "docker volume的介紹"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
  - "Docker 教學系列"
---

#### docker volume的介紹.
```bash
#查看我們有哪些volume
sudo docker volume ls
#建立volume
sudo docker volume create volume-test
#查看volume-test細部資訊
sudo docker volume inspect volume-test
#使用volume mapping Linux VM 和 container的資料夾
sudo docker run -d -p 8080:80 -v volume-test:/var/www/localhost/htdocs alpine tail -f /dev/null
```

----------------------------------
##### 下一篇我們將會開始進入docker compose的使用介紹
###### [進入下一篇](/docker-07)