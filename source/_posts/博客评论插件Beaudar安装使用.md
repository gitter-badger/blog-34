---
title: 博客评论插件Beaudar安装使用
date: 2022-09-05 15:52:21
tags:
  - Hexo
categories:
  - 前端
description: Beaudar 是基于 GitHub issue 的轻量评论插件，Utterances 的中文版本，本篇记录怎么集成到博客里面使用
---

## Beaudar

基于 GitHub issue 的轻量评论插件，Utterances 的中文版本，官网在[这里](https://beaudar.lipk.org/)

## Beaudar 是如何工作的？
Beaudar 加载时，将使用 GitHub issue 搜索 API 根据 url，“路径名”或“标题”查找与页面相关的 issue。如果找不到与页面匹配的 issue，即没有评论，当有人首次发表评论时，Beaudar-bot 会自动创建一个 issue。

## 配置使用

1. 准备

Beaudar 的配置方法很简单，创建一个仓库[`blog-comments`](https://github.com/all-smile/blog-comments)，在仓库中创建一个域名白名单文件`beaudar.json`，然后在[此处](https://github.com/apps/beaudar)授权安装即可。

`beaudar.json`文件
```json
{
  "origins": [
    "https://...",
    "http://localhost:4000"
  ]
}
```

2. `Hexo`配置

在主题配置文件里`_config_[theme].yml`里面增加如下配置

```yml
# 评论 [beaudar](https://beaudar.lipk.org/) 插件
comments:
  service: beaudar
  beaudar:
    repo: all-smile/blog-comments # 指向你自己的repo
```

## 效果展示

使用`GitHub`登录后评论

![](https://pic.imgdb.cn/item/6315b40c16f2c2beb16136d9.jpg)

## 问题处理

1. `blog-comments` 仓库默认分支为`main`

![](https://pic.imgdb.cn/item/6315b22716f2c2beb15ee173.jpg)

**解决：**

进入`blog-comments` 仓库，在 settings -> branches 里面，修改 `Default branch` 为 `main`

2. `Hexo` 本地服务测试`Beaudar`，添加白名单配置

![](https://pic.imgdb.cn/item/6315b2a816f2c2beb15f64b2.jpg)

**解决：**

修改`beaudar.json`文件
```json
{
  "origins": [
    "https://...",
    "http://localhost:4000"
  ]
}
```

---


![](https://cdn.jsdelivr.net/gh/all-smile/nav@1.0.7/static/images/wind_girl.webp)


我是 [**甜点cc**](https://home.i-xiao.space/)

热爱前端，也喜欢专研各种跟本职工作关系不大的技术，技术、产品兴趣广泛且浓厚，等待着一个创业机会。主要致力于分享实用技术干货，希望可以给一小部分人一些微小帮助。

我排斥“新人迷茫，老人看戏”的现象，希望能和大家一起努力破局。营造一个良好的技术氛围，为了个人、为了我国的数字化转型、互联网物联网技术、数字经济发展做一点点贡献。**数风流人物还看中国、看今朝、看你我。**
