---
title: hexo主题
date: 2017-10-02 22:55:50
categories: hexo笔记
tags: [hexo笔记,hexo主题,博客笔记]
comments: true
---

## 换主题

1.  [https://github.com/hexojs/hexo/wiki/Themes](https://github.com/hexojs/hexo/wiki/Themes) 上面有主题合集
2.  随便找一个主题，进入主题的 GitHub 首页，比如我找的是 [https://github.com/iissnan/hexo-theme-next](https://github.com/iissnan/hexo-theme-next)
3.  复制它的 SSH 地址或 HTTPS 地址，假设地址为 git@github.com:iissnan/hexo-theme-next.git
4.  `cd themes`
5.  `git clone git@github.com:iissnan/hexo-theme-next.git`
6.  `cd ..`
7.  将 _config.yml 的第 75 行改为 `theme: hexo-theme-next`，保存
8.  `hexo generate`
9.  `hexo deploy`
10.  等一分钟，然后刷新你的博客页面，你会看到一个新的外观。如果不喜欢这个主题，就回到第 1 步，重选一个主题。


## 美化主题

#### 主题设定
Scheme 是 NexT 提供的一种特性，借助于 Scheme，NexT 为你提供多种不同的外观。同时，几乎所有的配置都可以 在 Scheme 之间共用。
在主题配置文件（next/_config.yml）中可以修改scheme字段
```yml
# Schemes
#scheme: Muse
scheme: Mist
#scheme: Pisces
#scheme: Gemini
```

#### 设置语言
在站点配置文件（_config.yml）中修改 `language` 字段:
- 英文: en
- 中文简体: zh-Hans
- 中文繁体: zh-hk或zh-tw

#### 设置头像
1. 在  `next/source` 目录中新建`upload_image`子目录，用于上传自己需要用到的各种图片,设置头像时将头像图片放在这里即可；
2. 修改主题配置文件（next/_config.yml）中的 `avatar` 字段，将它的值设置为你想要替换的头像的链接；
```yml
  avatar: /upload_image/avatar.jpg
```

#### 网站logo设置
1. 通过网站[favicon在线制作](http://tool.lu/favicon/)favicon图片；
2. next主题：将图片放在next主题source/images目录下，替换其中默认的16x16和32x32 favicon图片。


#### 菜单中添加分类和标签
1. 在终端窗口下，定位到 Hexo 站点目录下。使用 `hexo new page` 新建一个页面，命名为 `categories` ：
```
$ cd your-hexo-site
$ hexo new page categories
```
2. 编辑刚新建的页面，将页面的 `type` 设置为 `categories` ，主题将自动为这个页面显示分类。页面内容如下：
```yml
title: 分类
date: 2014-12-22 12:39:04
type: "categories"
```
3. 在菜单中添加链接。编辑主题配置文件(next/_config.yml)， 在`menu` 中找到`categories`,去掉前面的`#`:
```yml
   menu:
     home: / || home
     archives: /archives/ || archive
     #categories: /categories/ || th
     tags: /tags/ || tags
```
4. 配置好后就可以在博客添加分类：
```yml
    ---
    title: 开博大吉
    date: 2017-10-01 14:45:50
    categories: bullshit
    ---
```
***note：添加标签的步骤和添加分类一样，只需要将 `categories` 换成 `tags` 即可***

#### 设置代码高亮主题
1. NexT 使用 [Tomorrow Theme](https://github.com/chriskempson/tomorrow-theme) 作为代码高亮，共有5款主题供你选择。 NexT 默认使用的是 白色的 `normal` 主题，可选的值有 `normal`，`night`， `night blue`， `night bright`， `night eighties`
2. 在主题配置文件中更改 `highlight_theme` 字段，将其值设定成你所喜爱的高亮主题

#### 设置侧边栏社交链接
侧栏社交链接的修改包含两个部分，第一是链接，第二是链接图标。 两者配置均在主题配置文件中。
1. 链接放置在 `social` 字段下，一行一个链接。其键值格式是 `显示文本: 链接地址`。
```yml
    social:
      GitHub: https://github.com/daxueshi || github
      #E-Mail: mailto:yourname@gmail.com || envelope
      #Google: https://plus.google.com/yourname || google
      #Twitter: https://twitter.com/yourname || twittersocial:
```
2. 设定链接的图标，对应的字段是 `social_icons`。其键值格式是 `匹配键: Font Awesome 图标名称`， `匹配键` 与上一步所配置的链接的 `显示文本` 相同（大小写严格匹配），`图标名称` 是 Font Awesome 图标的名字（不必带 `fa-` 前缀）。`enable` 选项用于控制是否显示图标，你可以设置成 `false` 来去掉图标。
```yml
social_icons:
  enable: true
  # Icon Mappings
  GitHub: github
  Twitter: twitter
  微博: weibo
```

#### 鼠标点击小红心的设置

将 [love.js](https://github.com/Neveryu/Neveryu.github.io/blob/master/js/src/love.js) 文件添加到 \themes\next\source\js\src 文件目录下。
找到 \themes\next\layout_layout.swing 文件， 在文件的后面， 标签之前 添加以下代码：
```js
<!-- 页面点击小红心 -->
<script type="text/javascript" src="/js/src/love.js"></script>
```

#### 背景的设置
1. 将 [particle.js](https://github.com/Neveryu/Neveryu.github.io/blob/master/js/src/particle.js) 文件添加到 \themes\next\source\js\src 文件目录下。
2. 找到 \themes\next\layout_layout.swing 文件， 在 `head` 标签中添加以下代码：
```js
<!-- 背景动画 -->
<script type="text/javascript" src="/js/src/particle.js"></script>
```
3. 背景动画默认关闭，需要自己打开：在主题配置文件中`canvas_nest`的值设置为`true`