+++
date = '2026-05-31T17:56:31+08:00'
draft = false
title = '我为什么选 Hugo + GitHub Pages 搭博客'
tags = ['hugo', 'blog']
comments = true
+++

去年想搭博客，看了几个方案：

**WordPress** — 太臃肿，还得租服务器。而且 WordPress 被攻击的新闻看多了，不想给自己找事。

**Hexo** — 朋友在用，说文章多了构建越来越慢。我看他博客有几百篇，每次部署要等十几秒，对我来说能忍，但还是想找个更快的。

**Ghost** — 界面确实漂亮，但还是要服务器，免费版限制太多。

**Hugo** — 同事推荐的。一个 .exe 搞定所有，不用装 Node、Ruby、PHP。我试了一下 `hugo new site` 到 `hugo server` 不到一分钟，当场就定了。

## 搭博客的过程

实际搭起来比想象中简单：

1. 装 Hugo Extended 版（普通版不支持 SCSS，我第一次就装错了，构建报错才发现的）
2. `hugo new site` 创建项目
3. 装 PaperMod 主题（Git submodule 的方式，方便以后升级）
4. 配 GitHub Actions 自动部署到 GitHub Pages
5. 绑域名

全部弄完大概半小时。之后每次写文章就是：`hugo new content posts/xxx.md` → 写完 → `git push`，GitHub Actions 自动部署。

<!--more-->

## 用了一年的感受

**好的方面：**
- 构建真的快，几百篇也是毫秒级
- Markdown 写东西很专注，不用调格式
- 零成本，唯一花钱的是域名（其实也是免费的，用的 qzz.io）
- Git 管理文章，历史记录清晰，不用担心写坏

**不爽的方面：**
- 没有后台，手机没法写文章（有时候想记个灵感，只能开 GitHub 网页版）
- 图片处理麻烦，得先压缩再放 `static/` 下引用
- PaperMod 主题虽然不错，但有些小细节还是得自己改 CSS

## 总结

Hugo + GitHub Pages 适合愿意在本地写 Markdown、懂一点 Git 的人。如果你想要"打开浏览器就能写"的体验，可能 Ghost 或 WordPress 更合适。但对我来说，用了一年了，没想过换。
