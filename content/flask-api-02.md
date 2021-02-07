---
title: "Flask-Restful API 教學系列02 Flask串接MySQL建立資源"
date: 2021-02-06T08:46:10+08:00
description: "Flask-Restful API 串接MySQL建立資源"
type: "post"
image: "images/flask-restful-api-logo.png"
categories: 
  - "Flask-Restful API"
tags:
  - "Flask"
  - "Restful API"
  - "MySQL"
---

#### pip 安裝 必要套件.
```bash
#安裝 flask_restful
python -m pip install flask_restful
#安裝 pymysql
python -m pip install pymysql
```

##### main.py中
```bash
from flask import Flask 
from flask_restful import Api

app = Flask(__name__)
api = Api(app)

api.add_resource(Users, '/users')
api.add_resource(User, '/user/<id>')


@app.route('/')
def index():
    return "hello world XD"

if __name__ == '__main__':
    app.debug = True
    app.run(host = '0.0.0.0', port = 5000)
```

##### 根目錄中創建resources目錄,在resources目錄下再創建user.py
```bash
#根目錄中創建resources目錄
sudo mkdir resources
#進入resources目錄
cd resources
#將resources成為python套件
touch __init__.py
#創建user.py
touch user.py
```

##### user.py中
```bash
from flask_restful import Resource, reqparse
from flask import jsonify
import pymysql
import traceback

parser = reqparse.RequestParser()
parser.add_argument('name')
parser.add_argument('gender')
parser.add_argument('birth')
parser.add_argument('note')

class Users(Resource):
    def db_init(self):
        db = pymysql.connect(
            host = r'127.0.0.1',
            user =  r'root',
            password =  r'mysql',
            database =  r'api',
            )

        cursor = db.cursor(pymysql.cursors.DictCursor)
        return db, cursor

    def get(self):
        db, cursor = self.db_init()
        sql = 'Select * From api.users'
        cursor.execute(sql)
        db.commit()
        users = cursor.fetchall()
        db.close()

        return jsonify({'data': users})

    def post(self):
        db, cursor = self.db_init()
        arg = parser.parse_args()
        user = {
            'name': arg['name'],
            'gender': arg['gender'] or 0,
            'birth': arg['birth'] or '1900-01-01',
            'note': arg['note'] or None,
        }

        sql = """
            INSERT INTO `users` (`name`, `gender`, `birth`, `note`) VALUES ('{}', '{}', '{}', '{}');
        """.format(user['name'], user['gender'], user['birth'], user['note'])

        response = {}
        try:
            cursor.execute(sql)
            response['msg'] = 'success'
        except :
            traceback.print_exc()
            response['msg'] = 'failed'

        db.commit()
        db.close()
        return jsonify(response)

```

----------------------------------
##### 下一篇我們將會開始建立Flask Restful-Api 的CRUD

###### [進入下一篇](/flask-api-03)