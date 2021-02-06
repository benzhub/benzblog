---
title: "Docker 教學系列04 Dockerfile基本操作"
date: 2021-02-02T14:46:10+08:00
description: "Docker Dockerfile操作"
type: "post"
image: "images/masonary-post/docker-logo.png"
categories: 
  - "Docker"
tags:
  - "Docker"
---

#### Dockerfile 基本操作.
```bash
#FROM指令
touch Dockerfile
FROM alpine:latest
#RUN 執行指令(build中執行)
#ARG可以賦予變量
ARG whoami=docker
#賦予路徑myworkspace變數,只後使用${}就能帶入變數
env myworkspace /var/www/localhost/htdocs
#工作預設路徑改為${myworkspace}
WORKDIR ${myworkspace}
#COPY複製檔案到image裡面
COPY ./content.txt ./
RUN ls -l ./
RUN cat ./content.txt >> index.html
RUN echo "I impersonated the unicorn." \
    && echo "I love ${whoami}." \
    && ls -l /
RUN echo "I impersonated the unicorn." \
    && echo "I love ${whoami}." \
    && ls -l /
RUN apk --update add apache2
RUN rm -rf /var/cache/apk/*
# httpd -D FOREGROUND
#ENTRYPOINT,image一啟動container默認執行的command(container 啟動後執行)
ENTRYPOINT ["tail", "-f", "/dev/null"]
ENTRYPOINT ["httpd", "-D", "FOREGROUND"]
#建立image
docker build -t lenrich1403/aplinetest .

```

#### Dockerfile build
```bash
sudo docker build --build-arg whoami=Linux -t lenrich1403/argtest .
```
----------------------------------
##### 下一篇我們將會開始進入docker 網路模式的介紹和實做
###### [進入下一篇](/docker-05)