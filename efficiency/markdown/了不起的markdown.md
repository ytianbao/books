# 了不起的Markdown

## 第八章 自由地写作--GitBook

在如今这样开放的互联网时代，每个人都可以是一个独立的品牌，
可以表达自己的观点，也可以写一本自己的书。豆瓣阅读、百度阅读、
网易云阅读、简书、知乎等平台都提供了很好的创作环境，可是它们也
都有一定的门槛，那如何才能自由地、无门槛地进行写作呢?GitBook为
我们提供了这种可能。

小提示：本书所提及的GitBook在没有特殊说明的情况下，均是指
GitBook 命令行工具。由于www.gitbook.com在国内访问体验较差，因此
不多作介绍。

本章将向大家介绍如何使用GitBook这个现代写书工具进行写作

### 8.1 你好，GitBook

GitBook命令行工具是基于Node.js开发的，通过命令行可以创建、
编辑和管理电子书。GitBook是目前最流行的开源书籍写作工具，其在
写作方面主要有以下几点优势。

1）支持Markdown和AsciiDoc语法。
2）支持多语言，支持变量、模板和模板继承。
3）可以导出静态站点或电子书（支持PDF、ePub、mobi等格
式）。
4）有丰富的插件。
5）可以使用Git管理写作内容，方便多人协作和版本管理。
6）可以将内容托管在GitHub或Gitlab中。

使用GitBook可以搭建公司内部文档，用于内部的资料共享；也可
以发布开源电子书，用于在互联网上分享知识。

#### 8.1.1 环境配置

安装GitBook前需要先安装Node.js（具体请参考附录），然后再通
过命令来安装GitBook，GitBook的安装命令如下所示。

```sh
npm install gitbook-cli -g
```
#### 8.1.2 快速开始

1. 创建静态站点

先通过一个例子来快速了解GitBook的工作流程。

第1步，初始化工作目录。

```sh
# 首先，创建mygitbook文件夹，并切换到这个文件夹下面，命令如下
~$ mkdir mygitbook && cd mygitbook

# 然后，初始化GitBook工作目录，创建必要的文件
~$ gitbook init
warn: no summary file in this book
info: create README.md
info: create SUMMARY.md
info: initialization is finished
```

根据上述代码，初始化完成后会创建两个md格式的文件。
1）README.md：用于编写书籍的前言或介绍。
2）SUMMARY.md：用于配置书籍的目录结构。

第2步：定义目录结构。
在SUMMARY.md文件中定义书籍的目录结构，主要有两种方法。
方法➊：先定义好目录结构，再通过gitbook init命令自动生成目录
结构对应的文件夹和Markdown文件。
方法➋：先创建好文件夹和Markdown文件再来编辑目录结构
这里我们使用方法➊，在SUMMARY.md中定义书籍的目录结构，
示例如下。

```sh
# SUMMARY

* [项目简介](README.md)
* [快速开始](docs/快速开始.md)
* [环境搭建](docs/环境搭建.md)
* [简单使用](docs/简单使用.md)
* [深入学习](docs/深入学习.md)
```

然后在项目根目录下执行如下命令。

```sh
gitbook init
```

所有不存在的文件夹和文件都会被新建出来。

注意：gitbook init只支持生成两级目录。

第3步：启动服务，在项目根目录下执行如下命令。

```sh
gitbook serve
```

输出结果如下所示。

```sh
Live reload server started on port: 35729
Press CTRL+C to quit...

info: 7 plugins are installed
info: loading plugin "livereload"... OK
```

```sh
info: loading plugin "highlight"... OK
info: loading plugin "search"... OK
info: loading plugin "lunr"... OK
info: loading plugin "sharing"... OK
info: loading plugin "fontsettings"... OK
info: loading plugin "theme-default"... OK
info: found 5 pages
info: found 0 asset files
info: >> generation finished with success in 1.9s !

Starting server ...
Serving book on http://localhost:4000 # 注意浏览地址
```

执行gitbook serve命令后，会先执行gitbook build编译书籍，如果编
译没有问题，就会打开一个Web服务器，默认监听4000端口。如果编译
有问题，则会抛出错误信息。

第4步：查看效果，用浏览器打开http://localhost:4000/查看书籍站点
的显示效果。

2.开始写作
笔者推荐的写作工具组合是：GitBook（书籍管理）+Typora（编辑
器）+SourceTree（版本控制），对于编写和管理电子书来说，这是一种
非常高效的组合。当然，使用VS Code也是一个不错的选择。

本书的第3章和第4章已经介绍过Typora和VS Code。而SourceTree是
一款Git可视化管理工具，如果你熟悉Git，那么SourceTree是很容易快速
上手的，关于SourceTree的更多内容可以参考https://www.sourcetreeapp.com/。

3.发布电子书

GitBook不仅可以生成静态网站，也可以生成3种格式（即ePub、
mobi、PDF）的电子书。

例如生成PDF格式的电子书，命令如下所示。

```sh
gitbook pdf ./ ./mygitbook.pdf
```

4.发布上线

如果想要开源，可以把书籍托管到GitHub上，然后绑定自己的域
名。一个比较好的例子是https://github.com/rootsongjc/kuberneteshandbook。

### 配置GitBook

#### 8.2.1 GitBook的项目结构

在开始之前，先了解一下GitBook的项目结构，基本的结构示例如
下。

```sh
|-book.json # 配置书籍（可选）
|-README.md # 书籍的前言/介绍（必填）
|-SUMMARY.md # 配置书籍的目录（可选）
|-GLOSSARY.md # 配置书籍的词汇/注释术语列表（可选）
|-.gitignore # 配置要忽略的文件
|-cover_small.jpg # 封面图片（小）
|-cover.jpg # 封面图片
|-第一章/ #书籍内容目录
```

多语言的GitBook项目结构如下。
```sh
|-book.json # 配置书籍（可选）
|-LANGS.md # 配置多语言（必填）
|-.gitignore # 配置要忽略的文件
|-en/
  |-Readme.md
  |-SUMMARY.md
  |-GLOSSARY.md
  |-book.json
  |-something.md
  |_第一章/
|-zh/
  |-Readme.md
  ...
```

1.配置项目结构
book.json是全局配置文件，可以自定义项目的根目录、自述文件、
摘要、词汇表、多语言等文件的文件名。

在book.json中可配置的变量如下

----------------
| 变量 | 描述 |
| root | 配置书籍的根目录，默认是当前目录 | 
| structure | 配置自述文件、摘要、词汇表的文件名 |
| title | 配置书名，如果不设置，则默认从自述文件README第一段中提取
| description | 配置书籍的描述，如果不配置，则默认从自述文件中提取
| author | 配置作者姓名 |
| isbn | 配置本书的国际码ISBN
| language | 配置书本语言的ISO代码，默认值尾en。这个值是用来做国际化和本地化的 |
| direction | 配置文本的方向。可以是rtl或ltr，默认值取决于language的值 |
| gitbook | 指定GitBook版本。使用SemVer规范，接受“>=3.00”这样的格式
-------------------------

配置 book.json 的一个示例如下。

配置 book.json 的一个示例如下。

```json
{
    "title": "GitBook实用指南",
    "description": "写给大家看的入门指南",
    "author": "帅填报",
    "output.name": "site", //构建输出文件名，使用默认的就好
    "language": "zh-hans",
    "gitbook": "3.2.2",
    "root": ".", //根目录为当前目录就好，仅做展示
}
```

小提示：为了避免出现更多错误，建议使用默认配置。

b）配置链接

如果搭建的是内部文档，右上角的分享链接（如下图所示）就没必
要出现了，那该怎么关闭呢?

关闭分享链接的示例代码如下。

```json
{
    "links": {
        "sharing": {
            "google": false,
            "facebook": false,
            "twitter": false,
            "weibo": false,
            "all": false
        }
    }
}
```

如果要在导航栏配置一些链接，其示例代码如下。

```json
{
    "links": {
        "sidebar": {
            "我的博客": "http://blog.csdn.net/wirelessqa",
            "我的微博": "http://www.weibo.com/wirelessqa"
        }
    }
}
```
