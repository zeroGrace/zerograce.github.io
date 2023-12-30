---
layout: post
title: Info of my Blog 
date: 2023-12-30
categories: blog
tag: jekyll
---

* content
{:toc}


## Grace's blog     {#myblog}

该blog基于github pages和jekyll构建，模板基于[less官网](https://lesscss.cn/)，向所有相关开发者致谢。

### 更改博客布局

修改页面基本信息：`_config.yml`文档；主要配置含义如下：

> 特别注意`baseurl`的配置。如果是`***.github.io`项目，不修改为空''的话，会导致JS,CSS等静态资源无法找到的错误

```bash
name: 博客名称
email: 邮箱地址
author: 作者名
url: 个人网站
# baseurl修改为项目名，如果项目是'***.github.io'，则设置为空''
baseurl: ''   
resume_site: 个人简历网站
github: github地址
github_username: github用户名称
```

修改页面字体大小间距、图片位置等style信息（blog所在本地路径的前半部分省略，下同）: `/zerograce.github.io/styles/css/index.css`文件，改CSS。

### 发布博客

每篇文章为一个markdown文件，直接放在`_posts`文件夹下面。每篇文章的开始处需要使用yml格式来写明这篇文章的简单介绍。格式如下(去掉注释)：

```yml
---
layout: post
title:  标题
date:   2023-12-30
categories: code
tag: python
---

* content
{:toc}


我是正文。
```

添加`* content {:toc}`为目录，会在博客侧边栏显示目录导航。目录和正文之间至少需要2行空行。而后按正常的Markdown语法书写正文。

文档中插入图片：

- 图片需要保存在：`/zerograce.github.io/styles/pics/`文件夹下
- markdown文件中的图片链接书写格式：`/styles/images/pics/pic_name.png`
- 不在blog的markdown文件里设置图片缩放，否则blog网页显示图片时无法居中。

正文部分从2级标题开始，不加1级标题（title），这样网页布局看起来舒服一些。

个人习惯：Typora写笔记，vscode处理笔记发布格式及上传Github。

### 本地运行预览

Ruby终端运行：

``` bash
# 切换到blog所在目录
cd /zerograce.github.io
# run site
jekyll server
```

打开浏览器并输入URL`http://localhost:4000/`即可查看。


