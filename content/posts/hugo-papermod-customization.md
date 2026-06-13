---
title: "Hugo PaperMod 主题美化指南"
date: 2026-06-13
description: "手把手教你自定义 PaperMod 主题，打造属于你的个性化博客"
tags: ["tutorial", "hugo", "blog"]
---

承接上一篇 Hugo 搭建教程，这篇文章专门讲如何美化 PaperMod 主题。

## 为什么选 PaperMod？

PaperMod 是 Hugo 生态中最受欢迎的博客主题之一。它简洁、快速、支持深色模式，而且提供了丰富的自定义接口——你不需要修改主题源码，就能实现各种个性化效果。

## 1. 自定义颜色主题

PaperMod 使用 CSS 变量来控制颜色。在 `assets/css/extended/` 目录下创建自定义 CSS 文件，就可以覆盖主题默认颜色：

```css
:root {
  --accent: #6366f1;
  --theme: #f8f9fc;
  --entry: #ffffff;
  --primary: #1a1d23;
  --secondary: #6b7280;
  --border: rgba(0,0,0,0.07);
}

[data-theme="dark"] {
  --accent: #818cf8;
  --theme: #0b0d11;
  --entry: #15171e;
  --primary: #e8eaed;
  --secondary: #9aa0ac;
  --border: rgba(255,255,255,0.06);
}
```

## 2. 更换字体

在同一个 CSS 文件中引入 Google Fonts：

```css
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;500;700&display=swap');

body {
  font-family: 'Noto Sans SC', -apple-system, BlinkMacSystemFont, sans-serif;
}
```

国内用户可以换成思源黑体或方正兰亭等中文字体。

## 3. 自定义导航栏

PaperMod 的导航栏支持 `menu` 配置。在 `hugo.toml` 中：

```toml
[menu]
  [[menu.main]]
    identifier = 'archives'
    name = "归档"
    url = '/archives'
    weight = 10
  [[menu.main]]
    identifier = 'search'
    name = "搜索"
    url = '/search'
    weight = 20
  [[menu.main]]
    identifier = 'about'
    name = "关于"
    url = '/about'
    weight = 30
```

## 4. 添加社交图标

PaperMod 内置了大量社交图标。在配置中添加：

```toml
[[params.socialIcons]]
  name = 'github'
  url = 'https://github.com/你的用户名'
```

支持的图标包括 GitHub、Twitter/X、Bluesky、RSS 等几十种。

## 5. 开启文章功能

```toml
[params]
  ShowReadingTime = true    # 显示阅读时间
  ShowWordCount = true      # 显示字数
  ShowCodeCopyButtons = true # 代码块复制按钮
  ShowShareButtons = true    # 分享按钮
```

## 6. 归档与搜索页面

PaperMod 支持开箱即用的归档和搜索。创建两个页面文件即可：

`content/archives.md`：
```
---
title: "归档"
layout: "archives"
url: "/archives/"
summary: archives
---
```

`content/search.md`：
```
---
title: "搜索"
layout: "search"
url: "/search/"
summary: search
---
```

## 结语

PaperMod 的设计哲学是"约定优于配置"，你不需要成为 CSS 专家就能做出漂亮的博客。关键在于用好 `assets/css/extended/` 和 `layouts/` 这两个覆盖目录。

下一篇我会分享我的完整配置文件和常用技巧，敬请期待！
