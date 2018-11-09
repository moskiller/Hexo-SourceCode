---
title: HexoEditor
date: 2018-11-08 09:54:56
tags: HexoEditor
categories: 建博笔记
---

> 昨天是立冬，昨晚好像吹了一晚上的冷风，今天好像变冷了点，注意保暖哦，亲！ 

## 前言
HexoEditor，项目地址：[Github](https://github.com/zhuzhuyule/HexoEditor)。这是一款为 Hexo 做了优化的 Markdown 编辑器，它使用 Electron 做框架，修改自 [Moeditor](https://github.com/Moeditor/Moeditor)。
<!-- more -->
### 0x00 它的样子？

* 先来个静图：
![HexoEditor](https://raw.githubusercontent.com/zhuzhuyule/HexoEditor/master/screenshots/main.png "这就是HexoEditor")

* 不过瘾？来，看一下动图：
![HexoEditor](https://raw.githubusercontent.com/zhuzhuyule/HexoEditor/master/screenshots/gif-tag.gif "还可以吧？")

### 0x01 它有什么功能?
*   HexoEditor
    *   预览内容与 Hexo 生成页面内容高度相似
    *   支持 Hexo 原生 Tag/Filter/Renderer
    *   支持使用 Hexo 配置文件 `_config.yml`
    *   快速生成 **新Post** 到项目资源路径下
    *   快速修改文件名(在Hexo编辑模式中)
    *   快速部署
    *   快速执行Hexo命令 `hexo d`,`hexo g`,`hexo s`,`hexo clean`
    *   图片自动转换为Markdown格式
        *   支持拖拽图片
        *   支持剪贴板粘贴
    *   图床支持(一键上传)
        *   支持 [SM.MS](https://sm.ms/)
        *   支持 [QiNiu](https://portal.qiniu.com/)
        *   支持 [Tencent](https://console.cloud.tencent.com/)
    *   快速启动（常用目录，常用地址）
    *   滚动条启用/取消同步滚动
*   HexoEditor (继承 [Moeditor](https://github.com/Moeditor/Moeditor) 原有功能)
    *   GitHub 风格 Markdown 显示
    *   TeX math 表达式
    *   UML 设计图
    *   编辑框代码高亮显示
    *   只读/只写/预览多模式切换
    *   用户自定义 字体，行高，字体大小
    *   用户自定义主题（文件名：main.csss）
    *   高亮代码块皮肤切换(由 [highlight.js](https://highlightjs.org/) 提供支持)
    *   自动重载文件
    *   本地化
    *   专注模式

### 0x02 怎么得到它？
```
//如果使用 Windows:
npm config set prefix "C:/Program Files/nodejs/npm_global"
npm config set cache "C:/Program Files/nodejs/npm_cache" 

//如果使用 Linux\Mac:
npm config set prefix "~/nodejs/npm_global"
npm config set cache "~/nodejs/npm_cache" 

//在中国，中国，中国，你应该设置淘宝镜像来加速下载。
npm config set registry "https://registry.npm.taobao.org/"
npm config set electron_mirror "https://npm.taobao.org/mirrors/electron/"

git clone https://github.com/zhuzhuyule/HexoEditor.git
cd HexoEditor
npm install
npm start
```

### 0x03 它有快捷键么？
| 按键 | 方法 | 说明 |
| :-: | :-- | :-- |
| `Tab` | tabAdd | 添加缩进 |
| `Shift` - `Tab` | tabSubtract | 减少缩进 |
| `Ctrl` - `B` | toggleBlod | 切换粗体 |
| `Ctrl` - `I` | toggleItalic | 切换斜体 |
| `Ctrl` - `D` | toggleDelete | 删除当前行 |
| `Ctrl` - `   | toggleComment | 切换注解 |
| `Ctrl` - `L` | toggleUnOrderedList | 切换无序列表 |
| `Ctrl` - `Alt` - `L` | toggleOrderedList | 切换有序列表 |
| `Ctrl` - `]` | toggleHeader | 降级标题 |
| `Ctrl` - `[` | toggleUnHeader | 升级标题 |
| `Ctrl` - `=` | toggleBlockquote | 增加引用 |
| `Ctrl` - `-` | toggleUnBlockquote | 减少引用 |
| `Ctrl` - `U` | drawLink | 添加超级链接 |
| `Ctrl` - `Alt` - `U` | drawImageLink | 添加图片 |
| `Ctrl` - `T` | drawTable(row col) | 添加表格(行 列) |
| `Ctrl` - `V` | pasteOriginContent | 源内容粘贴 |
| `Shift` - `Ctrl` - `V` | pasteContent | 智能粘贴 |
| `Alt` - `F` | formatTables | 格式化表格 |
| `Ctrl` - `N` |  | 新建md文档 |
| `Ctrl` - `H` |  | 新建Hexo文档 |
| `Ctrl` - `O` |  | 打开md文件 |
| `Ctrl` - `S` |  | 保存文档 |
| `Shift` - `Ctrl` - `S` |  | 另存为 |
| `Alt` - `Ctrl` - `S` |  | 打开设置 |
| `Ctrl` - `W` |  | 切换写作模式 |
| `Ctrl` - `P` |  | 切换预览模式 |
| `Ctrl` - `R` |  | 切换阅读模式 |

* **提示**: 在 Mac OS下, 请使用 `Cmd` 来代替 `Ctrl`  


### 0x04 如何使用？

在HexoEditor的根目录下，打开命令行执行命令：

```
npm start
```

等一会儿，HexoEditor就会跳出来了，然后点击左下角会出现菜单栏
![HexoEditor](http://pai5cscef.bkt.clouddn.com/如何写好Markdown文章？HexoEditor助你写出一篇好Hexo文章/20180618052712819.png "HexoEditor的菜单栏")
如果你想要写一篇博文，就点 新建Post。

`注意：
新建的文章会根据/yoursite/scaffolds/post.md模板自动生成一些内容，其实也就是这个文件的内容，如果想修改模板，就直接修改这个就行了。
`
