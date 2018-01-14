---
title: downfaster：快速下载html5游戏资源
date: 2016-01-08 18:54
tags: [游戏, HTML5, 工具, Python]
---
## 简介downfaster，一个快速下载html5游戏资源的小工具。<!--more-->## 相关技术* python（开发语言）* Tkinter（python自带的界面模块，开发程序的图形界面）* pyinstaller（将python脚本打包成为exe执行程序）* 正则表达式（提取资源的下载地址）* urllib（python提供的http模块，主要用到了`urllib.urlretrieve(url, path)`方法）## 如何使用1. 用chrome打开你要下载的游戏链接，打开开发者工具，选择网络选项卡，在任一资源上右键菜单选择下载游戏的har文件（har文件就是当前链接所有网络请求的归档文档，工具需要这个文件来解析出资源的路径，所以，downfaster需要和chrome来配合使用）。![3005357825.png][1]2. 运行程序，首先填写小游戏的名称（一般来说会是游戏中文名称的拼音缩写或者英文名称），然后选择上一步har文件的路径（不要有中文路径）。![2552164374.png][2]3. 点击下载按钮，等候下载完成，所有资源文件会保存在程序目录的res文件夹下。![3137387352.png][3]## 一些说明* 在英文目录下执行程序，如果有中文目录，可能会出现未知错误。* 最好将游戏的流程进行一遍后再下载har文件，因为有些游戏会在中途加载资源。* 如果游戏网站使用云加速等措施，可能下载下来的图片是错误的。* 如果游戏网站的页面比较复杂，下载也可能出错。* 如果程序有什么问题，欢迎向我反馈（[反馈地址][4]）## 链接* [源码][5]* [执行程序][6]  [1]: /img/1010043363.png  [2]: /img/2654014268.png  [3]: /img/3042905707.png  [4]: http://www.chunqiuyiyu.com/2016/01/download-html5-game-resources.html  [5]: https://github.com/chunqiuyiyu/python-tools/tree/master/downfaster  [6]: http://pan.baidu.com/s/1gdQKizD
