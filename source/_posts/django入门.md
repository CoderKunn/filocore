---
layout: source/_posts
title: Django 入门
date: 2019-03-25 10:01:16
categories:
- Django
tags:
---

## 零、本文将做什么  
1. 安装/升级 Python3
2. Django 框架
3. 快速开始一个 Django App
4. Django IDE 

## 一、安装/升级 Python3
### 1.1、Python2.x 和 Python3.x
目前最新的 Python 版本已经到了 3.7，从 Python3.x 的升级放弃了向下兼容，所以一些早期基于 Python2.x 开发的项目已经无法在 Python3.x 上执行了。
为了照顾现有程序，Python 2.6 作为一个过渡版本，基本使用了Python 2.x的语法和库，同时考虑了向Python 3.0的迁移，允许使用部分Python 3.0 的语法与函数。
新的Python程式建议使用Python 3.0 版本的语法。

### 1.2、MacOS 系统
MacOS 系统自带 Python2.7，所以我们需要升级至 Python3。
点击[Python-MacOS](https://www.python.org/downloads/mac-osx/), 下载最新或者想要的版本，根据提示安装

### 1.3、Linux/UNIX
点击[Python-Linux](https://www.python.org/downloads/source/)，下载最新或者想要的版本，根据提示安装


### 1.4、Windows
点击[Python-Windows](https://www.python.org/downloads/windows/)，下载最新或想要的版本，根据提示安装，注意32位或64位的系统版本

### 1.5、安装验证
执行命令：`python3 -V`, 获取到下载的版本，即为安装成功


## 二、Django 框架

> Django(发音：/ˈdʒæŋɡoʊ/ JANG-goh) 是用python语言写的开源web开发框架(open source web framework)，它鼓励快速开发,并遵循MVC设计。Django遵守 BSD版权，初次发布于2005年7月, 并于2008年9月发布了第一个正式版本1.0 。最新发行版本是Django 1.3.1，于2011年09月10日发布.

> Django 是一个开放源代码的Web应用框架，由Python写成,采用了 MTV 的框架模式，即Model，View，Template 组成。许多成功的网站和 APP 都基于 Django。

> 如果学习或使用过 Spring，那很棒，可以将 Django 和 Spring 放到同一个层面进行理解。都是 Web App 框架，区别是 Spring 使用的语言是 Java，Django 使用的是 Python；Spring 更加成功，Django 更加快速。

### 2.1、Django 安装
想安装 Django 首先要安装 Python，按照前文安装好 Python3 后，我们可以利用 Python 的包管理工具安装 Django。

`pip3 install django`

安装完成后，我们通过查看版本，检测是否安装成功

`python3 -m django --version`

我们可以通过命令行来创建一个 Django 工程

`django-admin.py startproject djangoDemo`

我们可以通过 tree 命令，看一下 Django 工程的目录结构

`tree djangoDemo`

```
djangoDemo/
├── djangoDemo
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py

```

mac 上默认没有 tree 命令，执行 `brew install tree` 安装

后续章节详细介绍目录结构以及各个文件的意义，本章节我们先专注快速开始

### 2.2、创建 Django App

#### 2.2.1 创建 App

在 DjangoDemo 工程目录下，执行命令，创建一个 Django App

`python3 manage.py startapp ajangoApp`

我们再来 tree 一下目录，`tree djangoDemo`

```
djangoDemo/
├── ajangoApp
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── djangoDemo
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-37.pyc
│   │   └── settings.cpython-37.pyc
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```

#### 2.2.2 App 目录结构


【admin.py】：对应应用后台管理配置文件

【papps.py]：对应应用的配置文件

【models.py】：数据模块，用于设计数据库等

【tests.py】：编写测试脚本

【views.py】：视图层，直接和浏览器进行交互

每次新建一个App我们需要将其在settings.py文件中的INSTALLED_APPS里进行注册，这样程序才能够找到这个服务

```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'djangoDemo', # 注册新创建的应用app
]

```

#### 2.2.3 Hello World

**coding**

Hello World 是任何一门语言的开始，我们初次体验 Django，也从这里开始，当 Hello World 运行成功时，前面的一切困惑将一扫而光。

打开 `/djangoDemo/ajangoApp/views.py`，开始 coding

```
from django.http import HttpResponse
"""
 django.http模块中定义了HttpResponse 对象的API
 作用：不需要调用模板直接返回数据
 HttpResponse属性：
    content: 返回内容,字符串类型
    charset: 响应的编码字符集
    status_code: HTTP响应的状态码
"""

"""
hello 为一个视图函数，每个视图函数必须第一个参数为request。哪怕用不到request。
request是django.http.HttpRequest的一个实例
"""
def hello(request):
    return HttpResponse('Hello World')
```

视图层写完，最终通过 HttpResponse 将'Hello World' 进行响应。

urls是用来声明请求url的映射关系。也就是程序通过urls里的配置来找到我们写的这个view。
打开 `djangoDemo/djangoDemo/urls.py`

```
# 导入url模块
from django.conf.urls import url

urlpatterns = [
    path('admin/', admin.site.urls),
    url(r'^hello/$', views.hello)
]

```

**run**

通过执行如下命令来启动项目

`python3 manage.py runserver`

默认端口号为：8000，当8000端口被占用时，我们也可以手动去更换端口，如更换成8080

`python3 manage.py runserver 8080`

执行后：

```
weixiaokundeMacBook-Pro:djangoDemo filocore$ python3 manage.py runserver 
Performing system checks...

System check identified no issues (0 silenced).

You have 15 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.

March 25, 2019 - 03:46:12
Django version 2.1.7, using settings 'djangoDemo.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.

```

**测试**

进入浏览器输入 url，`http://127.0.0.1:8000/hello`，即可看到 Hello World 显示在网页上



























