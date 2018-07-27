---
title: serverpath：切换 xampp 本地服务器目录
date: 2016-05-17 15:51
tags: [工具, Python]
---
## 前言
xampp 是一个十分易用的集成开发环境，包含了 apache、php 以及 mySQL 等建站环境。在现实的工作当中，进行本地化调试以及开发相当方便。但是随着本地开发项目的增加，切换服务器的目录就会十分繁琐。


<!--more-->


xampp 默认的服务器目录是在安装目录下的 htdocs 目录中。例如我的安装目录在 D 盘，那么我的默认服务器目录就是 `D:/xampp/htdocs/`。当我将项目放在 htdoc 目录下，开启 xampp 的 apache 模块时。我就可以通过 `http://localhost/` 访问到工作项目。这是一般的流程。

为了更好地管理每个项目，不能把每个项目都放在 htdocs 目录下，这时候就需要更改服务器路径。具体来说，修改打开安装目录下的 `apache/conf/httpd.conf` 文件。

httpd.conf 文件中默认路径是这样的：
```
DocumentRoot "D:/xampp/htdocs"
<Directory"D:/xampp/htdocs">
```

可以选择替换或者用 `#` 符号注释原有的路径并添加当前的工作路径，这里我选择了替换：
```
DocumentRoot "F:/workspace/myProject"
<Directory"F:/workspace/myProject">
```

但是，如果有多个工作目录需要同时开发，以上操作就变得十分繁琐。需要不停修改 httpd.conf 文件，然后保存，并重启 xampp 的 apache 服务。为了加快开发效率，我编写了 serverpath 工具来帮助自己。

## 技术
serverpath 工具由 python 开发，主要使用了 python 的文件模块以及正则模块。然后使用 python 内置的 Tkinter 开发了工具界面。在当今 WebApp 如日中天的时候，桌面 GUI 开发并不是那么重要。自己使用的工具而已，并不要求要多么美观，实现其功能就行。如果要界面十分漂亮，想必得学习 pyQt 等 GUI 开发框架，那就太重了。

实现原理就是简单的文件替换，主要的知识点是文件读写时用 `with` 语句得到文件对象的操作权，然后在读取写入的时候，使用 `seek()` 方法合理设定文件指针的位置。

## 如何使用

修改工具下的 `path.ini` 文件，将第一行路径修改为 xampp 的安装路径。并在下面添加工作项目的路径，多个项目路径换行添加。
```
D:/xampp/
F:/workspace/project1
F:/workspace/project2
F:/workspace/project3
```

安装 python 的环境，工具开发环境是 python 2.7.9。双击运行本程序，或者通过命令来运行：`python serverpath.py`。

![serverpath.png][1]
在界面列表选择要切换到的路径，点击 “修改” 按钮，然后重新启动 xampp 的 apache 服务。

![xampp.png][2]
用浏览器访问 `http://localhost/` 访问工作目录。

## 源码
[GitHub][3]
## 后记
使用 python 越久，越来越喜欢这个语言，真是有种想见恨晚的感觉。语法简单易学，而且能快速验证自己的想法，不愧为编程语言中的“瑞士军刀”。虽然也有一些缺点（如运行效率慢等），但用来解决一些生活和工作中的疑难杂症，当真是得心应手，再好不过了。


  [1]: /img/425988509.png
  [2]: /img/3909286478.png
  [3]: https://github.com/chunqiuyiyu/python-tools/tree/master/serverpath
