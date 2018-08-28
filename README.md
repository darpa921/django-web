# django-web

## 簡介

## 安裝套件

### 安裝 [Python](https://www.python.org/) 或是 [Anaconda](https://anaconda.org/)
安裝時我是把 "Add Pytho 3.6 to path" 項目打開， 讓 windows command prompt 可以直接使用 python
你可以使用 --version 的參數來知道 python 的版本
>python --version

![alt tag](https://i.imgur.com/vCfkfLT.jpg)

### 安裝 [Django](https://github.com/django/django)
安裝完 Python 後你就可以使用 pip 這個指令來安裝套件，
這個專案是使用最新的 django 版本， 為了防止以後造成不同版本的相容性問題,
我們需要做指定版本的安裝
>pip install django==2.1

![alt tag](https://i.imgur.com/6nQJsdF.jpg)

### 建立 Django 專案
開啟 "命令提示字元" 視窗, 在 D: 根目錄新增 PythonProject 目錄, 到 PythonProject 這個目錄,
利用 django-admin 建立新專案.
>django-admin startproject django_web

在建立完 django-web 專案你可以用檔案管理員看到在 D:\PythonProject 目錄下新增了一個 django_web 目錄, 在這個 django_web下會新增一個 django_web 目錄,
為了方便也不要搞混亂, 我們把第一個 django_web 目錄改成 django-web 來跟我們的專案名稱一樣.
在 django-web 目錄下我們可以看到 django_web 目錄和 manage.py 檔案, 進入下一層 django_web, 你可能看到 __init__.py, settings.py, urls.py 和 wsgi.py

![alt tag](https://i.imgur.com/3k4pBhu.jpg)

### 啟動專案 Server
建立完 django-web 專案後, 我們可以到 D:\PythonProject\django-web 用 python runserver 參數來起動 server

>python manage.py runserver

使用瀏覽器輸入 http://127.0.0.1:8000 或是 http://localhost:8000 就可以看到網站執行的狀況

![alt tag](https://i.imgur.com/jIBYxtu.jpg)

## 建立應用程式
我們可以利用 python startup 來建立應用程式 (Application)

>python manage.py startapp firstapp

當我們建立了一個新的 firstapp, 建立完應用程式, 記得要先在 settings.py 裡的 INSTALL_APPS 加 firstapp 應用程式

![alt tag](https://i.imgur.com/eCsnldP.jpg)

django 會新增 firstapp 目錄, 在這 firstapp 目錄則會增加幾個 .py 檔案和 migrations 目錄,


![alt tag](https://i.imgur.com/nr6la6S.jpg)


### 資料庫同步
>python manage.py makemigrations firstapp

>python manage.py migrate firstapp

### 建立 templates 和 static
在 django-web 目錄下建立 templates 跟 static 目錄, 
>templates 目錄是 django 存放 html 檔案的目錄
>static 目錄是 django 存放圖檔, CSS 跟 JavaScript 檔案的子目錄
在 settings.py 裡設定 templates 的路徑, 把  os.path.join(BASE_DIR, 'templates') 加在 TEMPLATES 'DIRS' 裡

![alt tag](https://i.imgur.com/diqFNdD.jpg)

在 settings.py 裡設定 static 的路徑, 把 STATICFILES_DIR = [os.path.join(BASE_DIR, 'STATIC')] 加在 STATIC_URL 的下一行

![alt tag](https://i.imgur.com/nfuz6Gz.jpg)

### 設定中文及時區
django 預設為英文, 要使用中文必須改為繁體中文及台北時區

![alt tag](https://i.imgur.com/oDCzGin.jpg)

