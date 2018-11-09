---
title: Hexo，我来了
date: 2018-11-03 11:58:18
updated: 2018-11-03 12:00:01
tags: Hexo
categories: 建博笔记
---
### 0x00 前言

其实一直以来，我对HEXO的风格都很喜欢,只是在错误的时候选择了错误的东西...最近在网上偶然间看到了一篇关于使用HEXO搭建的博客网页时，我脑海里突然就出现了几个大字：
<!-- more -->
{% cq %} 骚年，趁着年轻,赶快折腾 {% endcq %}

![Hexo](https://d33wubrfki0l68.cloudfront.net/6657ba50e702d84afb32fe846bed54fba1a77add/827ae/logo.svg "Hexo")

#### 0x01 来认识一下Hexo？

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

#### 0x02 如何得到 Hexo?

安装 Hexo 相当简单。在安装前，您必须检查电脑中是否已安装下列应用程序：

* [Node.js](http://nodejs.org/)
* [Git](http://git-scm.com/)

如果您的电脑中已经安装上述必备程序，那么恭喜您！接下来只需要使用 npm 即可完成 Hexo 的安装。

```
 npm install -g hexo-cli
```

安装完成后，需要先初始化Hexo，在命令行（即Git Bash）依次运行以下命令即可：

```
 hexo init 你的博客目录
 cd 你的博客目录
 npm install
```
以上代码完成后，在你的博客目录下，会产生这些文件和文件夹：

```
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

#### 0x03 注册github账号并创建repo
假定你已有账号，那么请在github里面创建一个repo, 名称就是 你的账号.github.io 

#### 0x04 配置和优化 Hexo
修改站点配置文件_config.yml，也可以在 https://hexo.io/themes/ 查看并下载你喜欢的主题。
最后。。。。。。写个hello world呗...... 
```
// 创建一个 hello world.md 文件
// 双引号里面 hello world 就是您的博文标题
hexo new "hello world"  
```
里面的内容随意书面，记得这个是 markdown 语法的。  
内容如何编写？参考[Markdown语法](https://www.appinn.com/markdown/)发挥你的想像力写吧，我想偷个懒，其它详细教程请您自行到谷歌或度娘处查询吧。

#### 0x05 本地测试
保存好你的 hello world.md 后，在命令行输入
```
hexo s   // hexo s是hexo server的缩写，效果一样
```

#### 0x06 打完，收工！
测试通过后，那么您只需要在命令行里依次输入以下命令，就可将你的博客上传到github里了:
```
hexo clean
hexo g   // hexo g 是 hexo generate 的缩写
hexo d   // hexo d 是 hexo deploy 的缩写

// 或者写成一行
hexo clean && hexo g && hexo d
```

如无意外的话，现在请打开你的浏览器，输入 你的账号.github.io 并回车，看到了吗？ Have fun!
