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

Flask是python中一款輕量級的web框架,它比起另外一套Django更為自由

非常適合用來開發小專案或是要高度自定義的情況

這次我們會用Python Flask 來打造我們的 Restful API


```bash
#安裝
python -m pip install Flask

from flask import Flask 

app = Flask(__name__)
api = Api(app)

@app.route('/')
def index():
    return "hello world XD"

if __name__ == '__main__':
    app.debug = True
    app.run(host = '0.0.0.0', port = 5000)
```


----------------------------------
##### 下一篇我們將會開始進入Flask
###### [進入下一篇](/flask-api-02)