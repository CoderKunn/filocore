---
title: Django 开发学习
date: 2019-03-27 20:19:50
categories:
- Django
tags:
---

## 一、Django 框架详解
### 目录结构及各个文件的作用
#### Django 工程初始结构
* **manage.py**：一个让你用各种方式管理 Django 项目的命令行工具。你可以阅读 django-admin and manage.py 获取所有 manage.py 的细节。
* 里面一层的 HiDjango/ 目录包含你的项目，它是一个纯 Python 包。它的名字就是当你引用它内部任何东西时需要用到的 Python 包名。 (比如 mysite.urls).
* **HiDjango/__init__.py**：一个空文件，告诉 Python 这个目录应该被认为是一个 Python 包。如果你是 Python 初学者，阅读官方文档中的 [更多关于包的知识](https://docs.python.org/3/tutorial/modules.html#tut-packages)
* **HiDjango/settings.py**：Django 项目的配置文件。如果你想知道这个文件是如何工作的，请查看 [Django settings](https://docs.djangoproject.com/zh-hans/2.1/topics/settings/) 了解细节
* **HiDjango/urls.py**：jango 项目的 URL 声明，就像你网站的“目录”。阅读 [URL调度器](https://docs.djangoproject.com/zh-hans/2.1/topics/http/urls/) 文档来获取更多关于 URL 的内容。
* **HiDjango/wsgi.py**：作为你的项目的运行在 WSGI 兼容的Web服务器上的入口。阅读 如何[使用 WSGI 进行部署](https://docs.djangoproject.com/zh-hans/2.1/howto/deployment/wsgi/) 了解更多细节。

```
HiDjango/
├── HiDjango
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```

#### Django App 目录结构

执行命令创建一个 app

`python manage.py startapp djangoApp`

创建好 app 的 django 目录结构如下：
我们可以通过目录结构，看到 django 框架 的 MTV 模式

**models**：一个抽象层，用来构建和操作web应用的数据，模型是数据唯一的、权威的信息源。它包含了你所存储的数据的必要字段和行为。通常，每个模型对应数据库中唯一的一张表。

**templates**：模板层提供了设计友好的语法来展示信息给用户。使用模板方法可以动态地生成HTML。模板包含所需HTML 输出的静态部分，以及一些特殊的语法，描述如何将动态内容插入。

**views**：用于封装负责处理用户请求及返回响应的逻辑。视图可以看作是前端与数据库的中间人，他会将前端想要的数据从数据库中读出来给前端。他也会将用户要想保存的数据写到数据库。

```
HiDjango/
├── djangoApp
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   │   └── __init__.py
│   ├── models.py
│   ├── tests.py
│   └── views.py
├── HiDjango
│   ├── __init__.py
│   ├── __pycache__
│   │   ├── __init__.cpython-37.pyc
│   │   └── settings.cpython-37.pyc
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── manage.py
```

### 请求与响应

#### views 与 urls
我们开发过程中经常需要做一个服务端的 API，通常是作为一个 url 来访问。url 的规划就放在 urls 中，基础用法在上一章已经讲过，不再做过多的赘述。在 url 配置时所映射的方法，就会写在 views 中，我喜欢把他理解为 Spring 中的 controller 与 service，当然区别很大，但有相似之处，可以帮助理解。（虽然我觉得相比起来 Spring 的注解优秀的一匹）






















