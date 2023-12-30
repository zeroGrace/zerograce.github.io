---
layout: post
title: Github & jekyll 搭建个人blog纪录
date: 2023-12-30
categories: blog
tag: jekyll
---

* content
{:toc}



以前磕磕绊绊搭过，后来重装系统blog搁置了，重新复健

## Github创建仓库

创建名为`username.github.io`的Github repostitory并clone仓库到本地（前期已完成；参考[官网](https://pages.github.com/)）

## 本地部署jekyll

jekyll是一个静态html网站生成器，使用Ruby写的，安装前需要装Ruby及其包管理系统RubyGems。

1. 安装ruby及RubyGems： 根据[rubyinstaller](https://rubyinstaller.org/downloads/)网站的建议，直接下载并安装Ruby+Devkit 3.2.X (x64)，内含gem

2. 安装Jekyll，参考[官网](https://jekyllrb.com/docs/step-by-step/01-setup/) ，但不装bundle

   1. 开始菜单，打开Ruby下的终端（start command prompt with Ruby）

   2. rubygems官网换源。不换源无法gem安装，科学上网也不行；参考[教程](https://juejin.cn/post/6998395351744921637)

      ```shell
      # 移除原官网https://rubygems.org/
      gem sources -r https://rubygems.org/
      # 添加国内镜像（网址域名可能以后会变）
      gem sources -a http://gems.ruby-china.com/
      ```

   3. gem安装jekyll：

      ```shell
      gem install jekyll
      ```

   4. 切换到blog所在文件夹（index.html所在目录）

      ```shell
      # 中间路径省略
      cd C:\...\zerograce.github.io
      ```

   5. 构建site并运行local web server at `http://localhost:4000`:

      ```shell
      # build site生成静态页面（首次运行）
      jekyll build
      # run site
      jekyll server
      ```

      浏览器地址栏输入`http://localhost:4000`，能成功打开blog即成功

   6. blog内容更新、本地运行预览检查无误后，git提交并push到Github仓库里，即可通过 [https://zerograce.github.io/](https://zerograce.github.io/) 远程访问博客。（网站更新需要稍等一段时间）

## Blog模板使用与页面设置

见Info of my Blog



