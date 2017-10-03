---
title: hexo搭建博客
date: 2017-10-01 15:17:28
categories: hexo笔记
tags: [hexo笔记,博客笔记]
---
1. 在 GitHub 上新建一个空 repo，repo 名称是「你的用户名.github.io」（请将你的用户名替换成真正的用户名）
2.  `npm install -g hexo-cli`，安装 Hexo
3.  `hexo init myBlog`
4.  `cd myBlog`
5.  `npm i`
6.  `hexo new 开博大吉`，你会看到一个 md 文件的路径
7.  `start xxxxxxxxxxxxxxxxxxx.md`，编辑这个 md 文件，内容自己想
8.  `start _config.yml`，编辑网站配置
    1.  把第 6 行的 title 改成你想要的名字
    2.  把第 9 行的 author 改成你的大名
    3.  把最后一行的 type 改成 git
    4.  在最后一行，与 type 平齐，加上一行 `repo: 仓库地址` （请将仓库地址改为「你的用户名.github.io」对应的仓库地址）
9.  `npm install hexo-deployer-git --save`，安装 git 部署插件
10.  `hexo generate`
11.  `hexo deploy`
12.  进入「你的用户名.github.io」对应的 repo，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接
13.  你现在应该看到了你的博客！
