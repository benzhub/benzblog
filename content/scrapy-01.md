---
title: "如何在ubuntu18.04上正確安裝 python scrapy 框架"
date: 2021-02-01T14:46:10+08:00
description: "如何正確安裝 python scrapy 框架"
type: "post"
image: "images/masonary-post/scrapy.png"
categories: 
  - "Scrapy"
tags:
  - "Python"
  - "Scrapy"
  - "Env Setup"
---

#### 學習Scrapy最大困擾
站長我在學習python的爬蟲框架scrapy時,最大的困擾居然是我根本不知道要怎麼安裝

因為原本的scrapy是在python2上開發的,所以google到的教學都只會教你如何用python2安裝和開發
但眾所周知,python2現在已經停止繼續維護了，親爸都要放棄他了,你怎麼還抱著python2不放,這可是不會生利息給你的

因此當我開始學習scrapy時，就下定決心一定要用python3來開發
又加上站長我是Linux信徒,相信沒有什麼事情是Linux做不到的
我在Ubuntu18.04上使用python pip 安裝時踩了太多的坑
經歷無數的失敗,終於給站長我研究出一個python3 scrapy 100%安裝成功率的方法

話不多說,我們直接上code:

首先檢查你的各python 版本

許多人都會在這邊搞混,分不清

```bash
python -m pip --version
python2 -m pip --version
python3 -m pip --version
```

通常在linux 可以有3個默認的python版本,一般來說ubuntu18.04的python3是默認的python3.6

許多ubuntu18.04會用到python3裡面的東西,所以不建議對它改動

因此我們安裝python3.8,並且安裝上對應的pip,再把python3.8 把它放到python裡面
把原本的python3.6放回去python3

```bash
#安裝python3.8
sudo apt -y install python3.8
#強至將python3.8鍊結到python3
sudo ln -f /usr/bin/python3.8 /usr/bin/python3
#安裝對應到python3(python3.8)的pip
sudo apt -y install python3-pip
#將原本的python3.6鍊結回去python3
sudo ln -f /usr/bin/python3.6 /usr/bin/ptyhon3
#將python3.8鍊結到python上面
sduo ln -s /usr/bin/ptyhon3.8 /usr/bin/pythonn
#更新python(python3.8)上面的pip到最新版本
python -m pip install --upgrade pip
```

接下來我們再次檢查你的各python和pip對應的版本

```bash
python -m pip --version
python2 -m pip --version
python3 -m pip --version
```

這樣你的python -m pip就會對應到你想要python3.8
也不會影響到原本ubuntu系統的python3裡面的python3.6了

接下來我們安裝虛擬環境

```bash
python -m pip install virtualenvwrapper
sudo mkdir $HOME/.virtualenvs
sudo chmod 777 -R .virtualenvs
```

```bash
sudo vim ~/.bashrc
```

在~/.bashrc中加入以下
```bash
# virtualenv-wrapper path
export WORKON_HOME=$HOME/.virtualenvs
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python
export VIRTUALENVWRAPPER_VIRTUALENV=/usr/local/bin/virtualenv
source /usr/local/bin/virtualenvwrapper.sh
```

#### 注意:這邊的 /usr/local/bin/virtualenv 和 /usr/local/bin/virtualenvwrapper.sh 不一定是你的實際路徑

#### 建議你先搜尋過後,放入你的路徑再寫入~/.bashrc

```bash
sudo find / -name virtualenv
sudo find / -name virtualenvwrapper.sh
```

重新加載環境變量

```bash
source ~/.bashrc
```

創建scrapy的虛擬環境

```bash
mkvirtualenv -p python scrapy-env
```

進入虛擬環境
```bash
workon scrapy-env
```

安裝 scrapy

```bash
sudo apt-get install python3.8-dev
sudo apt-get install libssl-dev
python -m pip install lxml
python -m pip install pyOpenSSL
python -m pip install Twisted
python -m pip install scrapy

```

檢查 打完收工 恭喜你千辛萬苦終於安裝成功 python3.8的 scrapy
```bash
scrapy --version
```


