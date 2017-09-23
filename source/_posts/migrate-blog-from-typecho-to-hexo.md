---
title: 博客从 Typecho 迁移到 Hexo
date: 2017-09-12 16:39:49
tags: [Hexo, Typecho]
---

## 回忆
又一次博客搬家，算来已经是第三次了。刚开始接触到博客，使用的是大名鼎鼎的 WordPress，搭建在 SAE （新浪云平台）上。后来，觉得 WordPress 太过臃肿，于是博客程序迁移到了 Typecho，同时由于 SAE 开始收费，自己购买了服务器和域名，博客也算是走上了正规的道路。在此期间，明白了一个道理，免费的就是最贵的。在吸引用户的时候，商家当然会降低姿态，各种优惠，等到商品有了用户量，就是“割韭菜”的时候了。当时就想使用 Hexo 将博客搭建到 GitHub 上面，只不过比较年轻，觉得这样的操作比较高端，就没敢尝试。现在时机到了，作为一名处在“风口浪尖”的前端开发，和 Node.js 打交道这么久，使用 Hexo 当然是小菜一碟。

## 理由
之所以选择 Hexo，除了对 Node.js 的亲近感，还有一个重要原因就是 Hexo 是静态博客生成程序。与 WordPress 和 Typecho 不同，Hexo 直接将 Markdown 文章解析成 HTML 文档。动态博客则需要请求数据库，将数据库中的数据读取出来，并按照一定的格式拼装返回 HTML 文档。静态博客少了数据库这一层，可以想象，网站速度会非常快。在使用 WordPress 与 Typecho 搭建动态博客时，我都会使用伪静态技术。现在，可以把“伪”字扔掉了。使用静态博客的好处还在于，迁移十分方便，最终生成的网站就是一个目录，里面是所有的文章，可以随时保存在其他地方，上传到任意的服务器上，不用任何繁琐的数据库配置与数据导入导出等。

## 缺点
凡事都有两面性，Hexo 同样如此。静态博客无法使用评论等动态功能。原先还可以借助多说等第三方评论，但是今年不久前，多说就停止服务了。至于国内的其他评论系统，当然也是非常不可靠。国外的评论系统，从国内网络访问不稳定，甚至完全无法访问，影响体验。同时 Hexo 的安装与使用对新手来说比较复杂，有些人更是喜欢用网站自带的编辑器创作博客，Hexo 显然不能原生满足这些需求。但是对我来说，Hexo 非常适合。

## 实践
本地安装就不用说了，网上教程一大堆。有了博客当然得有一个适合自己的主题，我自己开发了一款单栏极简主题 [Polk](https://github.com/chunqiuyiyu/hexo-theme-polk)，专注于博客内容的展现，只有首页、归档与关于三个页面，文章页只有日期、内容与标签，去除了其他博客常见的分类、友链、搜索、侧边栏等等，对我来说，现在展示出来的内容已经足够了。至于评论，使用了开源的 PHP 项目 [HashOver](https://github.com/jacobwb/hashover-next)，这样一来，迁移工作算是大体完成。以前的文章会逐渐更新到当前博客系统中。

## 想法
其实，做这么多都是次要的，博客内容永远是最重要的。我希望自己与访客能够快速准确地获取想要得到的内容，所以使用极简模式的主题。也许有人不喜欢，但没有关系。个人博客就是要展现出“个性”，我不靠博客流量吃饭，我只是需要一个写东西、发牢骚的地方（不局限于技术文章），所以不必迎合大众的品味。坚持下去吧，活着是需要坐标的，虽然回不去，可是看得见，博客的意义正在于此。