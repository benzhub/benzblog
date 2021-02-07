---
title: "Flask-Restful API 教學系列01 flask入門"
date: 2021-02-06T08:46:10+08:00
description: "Flask-Restful API flask入門"
type: "post"
image: "images/flask-restful-api-logo.png"
categories: 
  - "Flask-Restful API"
tags:
  - "Flask"
  - "Restful API"
---

#### Flask入門&&安裝.

Flask是Python中一款輕量級的web框架,它比起另外一套Django更為自由

非常適合用來開發小專案或是要高度自定義的情況

這次我們會用Python Flask 來打造我們的 Restful API


```bash
#新建一個main.py檔案
sudo touch main.py
#使用pip安裝Flask
python -m pip install Flask
```

##### 我們的第一支Flask程式

```bash
from flask import Flask 

app = Flask(__name__)

@app.route('/')
def index():
    return "hello world XD"

if __name__ == '__main__':
    app.debug = True
    app.run(host = '0.0.0.0', port = 5000)
```

##### 啟動
```bash
python main.py
```

我們到http://localhost:5000/ 上面就可以看到我們的hello world XD

代表你成功完了第一支Python Flask 的程式了

----------------------------------
##### 下一篇我們將會開始進入Flask串接MySQL建立資源
###### [進入下一篇](/flask-api-02)