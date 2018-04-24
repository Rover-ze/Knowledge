
## 什么是Djiango
Django是一个开放源代码的Web应用框架，由Python写成。采用了MTV的框架模式，即模型M，模板T和视图V。它最初是被开发来用于管理劳伦斯出版集团旗下的一些以新闻内容为主的网站的，即是CMS（内容管理系统）软件。并于2005年7月在BSD许可证下发布。这套框架是以比利时的吉普赛爵士吉他手Django Reinhardt来命名的。
1.基于Python的高级web高级框架<br>
2.能够让开发人员进行高效且快速的开发<br>
3.高度集成，免费且开源<br>


## 浏览器 / 网页

1.正常上网的流程：<br>
![这里写图片描述](https://img-blog.csdn.net/20180424192454695?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTc4MTk3Mw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)


![这里写图片描述](https://img-blog.csdn.net/20180424192428733?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MTc4MTk3Mw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)


2.浏览网页的基本原理：<br>
本质是网络通信,即通过网络进行数据传递<br>
浏览器是经过通信后获取到该页面的源代码文档（HTML等）<br>
浏览器解析文档后以适当的形式展现给用户<br>


## 搭建环境
1. 安装虚拟环境
```
pip3 install virtualenv
```

2. 安装env环境
```
virtualenv --no-site-packages -p xxxx env

virtualenv --no-site-packages env
```

3. 进入/退出虚拟环境
```
source bin/activate   # 进入虚拟环境

deactivate   # 退出虚拟环境
```

4. 安装django
```
pip install django==1.11
```

5. 创建项目
```
django-admin startproject helloworld
```
6. 启动django项目
```
python manage.py runserver ip:端口
```
 

 #### wsigi. py
 WSGI(Python Web Sever Gateway Interface -- Python服务器网关接口)

 Python应用于Web服务器之间的接口

 一般不动

 #### settings. py
 BASE_DIR -- 项目的根目录

 SECRET_KEY -- 项目的安全码（自动生成，不管）

 INSTALLED_APPS -- 已安装的应用，自己创建的应用需要加入进去

 MIDDLEWARE -- 中间键（不同过多关注）

 TEMPLATES -- 模板

 DATABASES -- 数据库配置

