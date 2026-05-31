+++
date = '2026-05-31T17:56:31+08:00'
draft = false
title = '零成本搭建个人博客：Hugo + GitHub Pages 指南'
tags = ['tutorial', 'hugo', 'blog']
+++

## 前言

一直想搭一个个人博客，但又不想花钱买服务器？这篇文章手把手教你用 **Hugo + GitHub Pages + Cloudflare** 免费搭建一个属于自己的博客。

<!--more-->

## 为什么选 Hugo？

Hugo 是一个用 Go 语言编写的静态网站生成器，最大的特点是**快**——几百个页面的网站，一秒钟就能生成完毕。而且：

- 🚀 **极速构建** — 毫秒级生成
- 🎨 **主题丰富** — 300+ 免费主题
- 📝 **Markdown 写作** — 专注内容，无需关心排版
- 🔧 **零依赖** — 一个二进制文件搞定，无需 Node.js 或 Ruby

## 搭建步骤

### 1. 安装 Hugo

```bash
# Windows
winget install Hugo.Hugo.Extended

# macOS
brew install hugo
```

### 2. 创建站点

```bash
hugo new site my-blog
cd my-blog
git init
```

### 3. 安装主题

我推荐 [PaperMod](https://github.com/adityatelange/hugo-PaperMod)，简洁大气：

```bash
git submodule add --depth 1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

### 4. 写文章

```bash
hugo new content posts/hello-world.md
```

用 Markdown 写内容，把 `draft = true` 改成 `draft = false` 即可发布。

### 5. 部署到 GitHub Pages

配置 GitHub Actions 自动部署流程，写好文章后只需 `git push`，剩下的事情交给自动化：

```yaml
# .github/workflows/deploy.yml
name: Deploy Hugo site to GitHub Pages
on:
  push:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v3
        with:
          extended: true
      - name: Build
        run: hugo --minify
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
```

### 6. 绑定域名

在 Cloudflare 添加 DNS 记录，指向 GitHub Pages，然后在仓库 Settings → Pages 中设置自定义域名。

## 写作建议

- **保持规律** — 每周一篇比一次写十篇更有价值
- **写给自己** — 首先是为自己记录，顺便帮到别人
- **不要追求完美** — 先发出来，再慢慢改进

## 总结

搭博客最大的障碍不是技术，而是开始。现在就动手，几分钟就能拥有自己的小天地 🌟
