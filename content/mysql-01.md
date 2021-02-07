---
title: "MySQL 教學系列01 MySQL常用指令"
date: 2021-02-06T20:46:10+08:00
description: "MySQL MySQL常用指令"
type: "post"
image: "images/mysql-logo.png"
categories: 
  - "MySQL"
tags:
  - "MySQL"
  - "MySQL 教學系列"
---

#### MySQL MySQL常用指令.

```bash
#使用utf-8建立名為api的資料庫
CREATE SCHEMA `api` DEFAULT CHARACTER SET utf8 ;

#創建資料表(table)和欄位(column)
CREATE TABLE `api`.`users` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `name` VARCHAR(45) NULL,
  `gender` INT NULL,
  `birth` DATE NULL,
  `note` LONGTEXT NULL,
  PRIMARY KEY (`id`));

#insert 新增資料
INSERT INTO `api`.`users` (`name`, `gender`, `birth`, `note`) VALUES ('Jack', '0', '2000-01-01', 'Jack is a good boy.');

#delete 刪除資料
DELETE FROM `api`.`users` WHERE `id`='5';

```


----------------------------------
##### 下一篇我們將會開始進入MySQL安裝教學
###### [進入下一篇](/MySQL-02)