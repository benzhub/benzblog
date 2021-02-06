---
title: "Docker 教學系列05 docker container 網路模式介紹"
date: 2021-02-05T14:46:10+08:00
description: "docker container 網路模式介紹"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
  - "Docker 教學系列"
---

#### docker container 網路模式介紹.

None模式:container 不能向外連線網路,外面也不能連線進去

Bridge模式:container 啟動的時候,我們會把container 放到設定的bridge network中

Container模式:啟動的container會複製已有的container的網路模式

Host模式:啟動的container我們會它放到設定的Linux VM network 中

###### 列出我們所擁有的network 
```bash
sudo docker network ls 
```

###### none 模式
```bash
sudo docker run -d --network null --name none-model alpine tail -f /dev/null
```

###### 查看網路界面
```bash
#查看none模式的網路界面
sudo docker network inspect none
```

###### bridge & container 模式
```bash
#創建屬於自己的bridge網路
sudo docker network create --dirver bridge my-bridge
#查看my-bridge模式的網路界面,並記下Subnet的ip
sudo docker network inspect my-bridge
#建立屬於my-bridge網路的container
sudo docker run -d --network my-bridge --name my-bridge-test01 alpine tail -f /dev/null
#再次檢查,會發現my-bridge-test在my-bridge網路中
sudo docker network inspect my-bridge
#不同的netword bridge 連線, 會將container 在不同的bridge 網路中各自分配給它ip
sudo docker network connect my-bridge my-bridge-test02
#container模式,會去複製現有的container的網路設定
sudo docker run -d --name container-mode-test01 --network container:my-bridge-test01 alpine tail -f /dev/null
#host模式,會將啟動的container 跟Linux VM 分配一個 ip給它
sudo docker run -d --name host-alpine --network host alpine tail -f /dev/null
```

----------------------------------
##### 下一篇我們將會開始進入docker volume的介紹
###### [進入下一篇](/docker-06)