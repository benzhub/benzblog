---
title: "MarkDown教學系列01 基礎 MarkDown語法教學 超入門"
date: 2021-02-01T14:46:10+08:00
description: "基礎 MarkDown語法教學 超入門"
type: "post"
image: "images/masonary-post/markdown-logo.png"
categories: 
  - "MarkDown"
tags:
  - "MarkDown"
  - "GitHub"
---

#### 什麼是MarkDown語法??

相信在github打滾過朋友們,一定都會常常看到README.md的說明文件

當你在根目錄中加上README.md並且用git推送到github時

即使你不打開README.md文件,它也會自動默認跑出README.md內容的畫面,.md格式的檔案,其實就是使用MarkDown語法。

國外也有許多人在做筆記時,也是用MarkDown作為主要的筆記工具

順帶一提,本站https://benzhub.github.io也是使用MarkDown語法做出來的喔!!

下面為大家介紹 markdown的入門,即使沒有要寫成像本站部落格,下次在寫github的README.md說明文件時,也能更圖文並茂,得心應手


#### 1.內文  

###### 語法

```markdown
如果什麼都不做,直接打文字進去就是內文

但是內文想要換行的話就必須要空一行,這樣markdown才會換行
```

###### 效果

如果什麼都不做,直接打文字進去就是內文

但是內文想要換行的話就必須要空一行,這樣markdown才會換行

------------------------------

#### 2.標題

###### 語法

```markdown
# 一級標題
## 二級標題
### 三級標題
#### 四級標題
##### 五級標題
###### 六級標題
```

###### 效果

# 一級標題
## 二級標題
### 三級標題
#### 四級標題
##### 五級標題
###### 六級標題

------------------------------

#### 3.粗體 斜體

###### 語法

```markdown
我是**Benz**,我喜歡寫*程式*
```


###### 效果

我是**Benz**,我喜歡寫*程式*

在markdown裡面 粗體無法與斜體同時使用

------------------------------

#### 4.有序序列

###### 語法

```markdown
1. Benz
    1. Hub
1. Coding
1. Python
```

###### 效果

1. Benz
    1. Hub
1. Coding
1. Python

------------------------------

#### 5.無序序列 內縮

###### 語法

```markdown
* Benz
* Coding
* Python
    * Scrapy
    * Django
    * Flask
```

###### 效果

* Benz
* Coding
* Python
    * Scrapy
    * Django
    * Flask

------------------------------

#### 6.引用

###### 語法

```markdown
> Benz say
```

###### 效果

> Benz say

------------------------------

#### 7.超鍊結

###### 語法
```markdown
[超鍊結的文字](https://benzhub.github.io) 
```
###### 效果

[超鍊結的文字](https://benzhub.github.io) 

###### 使用內部鍊結

###### 語法
```markdown
[內部鍊結](/markdown-01)
```

###### 效果

[內部鍊結](/markdown-01)

------------------------------

#### 8.圖片

###### 語法
```markdown
![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/263px-Markdown-mark.svg.png)
```

###### 效果

![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/263px-Markdown-mark.svg.png)

##### 內部圖片--用logo做範例

###### 語法

```markdown
![](/images/logo.jpg)
```
###### 效果

![](/images/logo.jpg)

------------------------------

#### 9.程式碼
###### 單行程式碼 語法

```markdown
`print("hello world XD")`
```

###### 效果

`print("hello world XD")`

###### 多行程式碼 語法 因為範例語法無法用markdown 打出來 這邊用圖片代替

![](/images/masonary-post/markdown-python.png)

###### 效果

```python
print("hello world XD")
print("hello world XD")
print("hello world XD")
```

------------------------------

#### 10.表格

##### 語法
```markdown
|number | name | age |
|:----- |----: |:---:|
|  001  | Benz |  18 |
|  002  | Hub  |  19 |

```

-: 設置内容和標題欄向右對齊

:- 設置内容和標題欄向左對齊

:-: 設置内容和標題欄向中間對齊

###### 效果

|number | name | age |
| :-----| ----: | :----: |
| 001 | Benz | 18 |
| 002 | Hub | 19 |

------------------------------

#### 以上就是最基礎的MarkDown 入門必備語法

#### 各位趕快去練習吧

