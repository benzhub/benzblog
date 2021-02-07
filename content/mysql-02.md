---
title: "MySQL 教學系列02 MySQL安裝教學"
date: 2021-02-06T20:46:10+08:00
description: "MySQL MySQL安裝教學"
type: "post"
image: "images/mysql-logo.png"
categories: 
  - "MySQL"
tags:
  - "MySQL"
  - "MySQL 教學系列"
  - "Docker"
---

#### MySQL Docker安裝教學.

```bash
#使用docker 啟動mysql,帳號為root,密碼為mysql,端口為3306
sudo docker run -d --name flask-api-mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=mysql mysql:latest
```

##### 安裝workbench

intrinsic column flags (基本欄位型別標識)

    1. PK: primary key (column is part of a pk) 主鍵
    1. NN: not null (column is nullable) 非空
    1. UQ: unique (column is part of a unique key) 唯一值
    1. AI: auto increment (the column is auto incremented when rows are inserted) 通常是在id或是流水號碼的讓它自動新增


----------------------------------
##### 下一篇我們將會開始進入MySQL
###### [進入下一篇](/MySQL-03)