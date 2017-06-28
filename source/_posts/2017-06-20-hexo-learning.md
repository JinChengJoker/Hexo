---
title: GitHub Pages + Hexo 搭建博客
date: 2017-06-20 16:23:01
---
很久之前就准备自己搞一个博客，当时准备直接在博客网站上注册一个，但是总觉得不酷。后来发现了GitHub Pages，可以用Hexo在上面部署一个博客，于是几经折腾，终于搞出来了。

## 1、Hexo 介绍

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

- 速度超快
- 支持 Markdown
- 一键部署
- 丰富的插件

## 2、安装必要程序

[Node.js](https://nodejs.org) - 在官网下载安装包安装
验证安装成功：

```
$ node -v
```

## 3、创建 Github 仓库

由于需要部署到 Github，所以先在 Github 创建一个仓库，这个仓库用来存放 hexo 为我们生成的静态文件。
注意：这个仓库名需要与你的 Github 账户名一致，比如我的账户名是 JinChengJoker，那么则需要创建一个名为 JinChengJoker.github.io 的仓库。

## 4、克隆 Github 仓库

以我的仓库名为例：

```
$ git clone git@github.com:JinChengJoker/JinChengJoker.github.io.git
```

考虑到后面时间长了，会存在不在同一台电脑或者更换电脑的情况，所以这里先克隆到本地。
这里的思路是 master 分支用来存放 hexo 生成的静态文件，再创建一个 hexo 分支且设置为默认分支，用于存放 hexo 的原始文件。
这样做的好处是，以后遇到更换电脑的情况，只要在新电脑上 clone hexo 分支，就可以基本无缝迁移了。

## 5、安装 Hexo

安装完必要程序后，用npm（随同Node.js一起安装的包管理工具）安装 Hexo。

```
$ npm install -g hexo-cli
```

未完，待续。
