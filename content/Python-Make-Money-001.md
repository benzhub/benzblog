---
title: "程式煉金術-Python 超入門01"
date: 2021-02-02T14:46:10+08:00
description: "這是一門教你如何用python煉金的入門課程，適合程式新手,中手,老手,高手高手高高手"
type: "post"
image: "images/python-logo2.png"
categories: 
  - "程式煉金術-Python 超入門"
tags:
  - "程式煉金術-Python 超入門"
---
>緣起:
這堂課程的起源是因為站長我初次轉職軟體工程師後,所感受到的[程式語言鄙視鏈](https://vinta.ws/blog/695)的衝擊,
因此下定決心要寫更廢的code,但賺得比那些自視甚高的王八蛋多

>真的由衷感謝:當初嘲笑我的那些王八蛋  
2021.02.02

python現今的應用層面非常廣,在業界被稱為**膠水語言**之一，在許多方面都可以見到他們身影

例如：資安.爬蟲.測試.運維.web.桌面應用程式以及近幾年最火紅的人工智能

python可以說是現今所有軟體工程師都避免不了需要去了解的一門程式語言

本系列課程唯一的目標導向就是要讓你用python賺錢,因為這次的教學是面向所有人,包含**程式麻瓜**(別擔心,我以前也是)

所以一開始避免不了要從最基礎的開始教起,好了,那就讓我們直接走起

#### 安裝
因為站長我個人是Linux信徒,所以之後的所有教學,除非必要,不然一律都是在Linux的作業系統(Ubuntu 18.04)上教學

至於程式麻瓜們心裡os:阿我要怎麼安裝Linux？怎麼用Linux?

之後站長有空的話**可能**會出教學,但現階段就麻煩自己去google(站長os:林北也沒人教我Linux🤬,要賺錢就拿出決心)

好了,我們馬上開始進入正題

```bash
python -m pip --version
python2 -m pip --version
python3 -m pip --version
```

雖然是要安裝，但是我們第一步也是最重要的一步就是檢查你環境**現有的python版本**,這是很多教學都會忽略掉的,只會要你無腦安裝

首先,我來解釋一下每一行的意義

如果你是安裝ubuntu 18.04

通常我們會讓Linux系統變數有3種python,分別是**python**, **python2**, **python3**

每一種Linux系統變數的python都可以讓你指定不同版本的python

pip是用來管理python套件的工具,-m 的意思簡單理解就是這個Linux系統變數的python 對應到的 pip 是什麼版本

每一種Linux系統變數的python,都可以對應到各自的pip,因此如果你沒有加上 -m 指定對應到的python,有可能你的套件會安裝在錯誤的python版本上

但通常我的作法都是以下

python:放置我要用的較新的python版本(通常是python3.8)

python2:放python2.7版本(因為有些github上的專案是用python2開發,所以有時還是避免不了要用python2.7)

python3:ubuntu 18.04 系統會用到python3,因此一般來說我不太會動它,當你ubuntu 18.04 安裝好通常python3會是python3.6

那麼,假設你的ubuntu 18.04是乾淨沒有安裝過任何東西的環境,那我們來開始安裝

```bash
sudo apt -y install python3.8
```

檢查是否安裝成功

```bash
/usr/bin/python3.8 --version
```

接下來我們要把python3.8鍊結上python,但是我們的python3.8這時還沒有安裝對應的pip 因此我們要暫時將python3 原本的 python3.6 改成 python3.8
我們會用到Linux 中的 ln 建立連結檔

```bash
sudo ln -f /usr/bin/python3.8 /usr/bin/python3
```

然後我們安裝python3.8 的 pip 並且將pip 更新到最新版本

```bash
sudo apt -y install python3-pip
python3 -m pip install --upgrade
```

我們將原本的python3.6放回python3 ,將我們想要的python3.8 建立連結檔到 python

```bash
sudo ln -f /usr/bin/python3.6 /usr/bin/python3
sudo ln -s /usr/bin/python3.8 /usr/bin/python
```

最後再檢查一次

```bash
python -m pip --version
python2 -m pip --version
python3 -m pip --version
```

這樣你就會看到你想要的python(python3.8版本)出現在Linux系統變數中
下一篇文章中,我們將會教你開始寫程式的幾個小工具











