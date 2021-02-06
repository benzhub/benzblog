---
title: "Docker 教學系列01 在不同os上使用安裝"
date: 2021-02-02T14:46:10+08:00
description: "Docker 在不同os上使用安裝"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
  - "Docker 教學系列"
---

#### Linux 上面安裝docker

查看你的linux版本
```bash
cat /etc/os-release
```

#### 安裝docker 套件

##### centos 8 上安裝
```bash
sudo yum -y install docker 
```

##### centos 7 上安裝
```bash
sudo yum remove docker docker-common container-selinux docker-selinux docker-engine docker-engine-selinux
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum-config-manager --enable docker-ce-edge
sudo yum makecache fast
sudo yum install docker-ce
```

##### ubuntu 上安裝
```bash
sudo apt -y install docker.io
sudo apt -y install docker-compose
```

##### 查看是否安裝成功
```bash
docker --version
```

##### docker service 操作
```bash
#啟動
sudo sytemclt start docker 
#系統默認啟動
sudo systemclt enable docker
#關閉
sudo systemclt stop docker
```
----------------------------------
##### 下一篇我們將會開始進入docker 的操作
###### [進入下一篇](/docker-02)
