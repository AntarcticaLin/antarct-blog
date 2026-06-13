+++
title = 'PaperMod 我只改了这几处'
date = 2026-06-13
description = '我实际用到的 PaperMod 自定义'
tags = ['hugo', 'blog']
comments = true
+++

PaperMod 是个很完整的主题，默认就很好看。我只改了 4 个地方：

<!--more-->

## 1. 配色

改的颜色不多，就换了三个值：

```css
:root {
  --accent: #2563eb;      // 链接和强调色
  --theme: #ffffff;        // 页面背景
  --entry: #f9fafb;        // 文章卡片背景
}
```

PaperMod 用了 CSS 变量，在 `assets/css/extended/` 下建个文件覆盖就行，不用碰主题源码。

## 2. 字体

```css
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;500;600&display=swap');
body {
  font-family: 'Noto Sans SC', -apple-system, BlinkMacSystemFont, sans-serif;
}
```

其实 PaperMod 默认的字体也不错，换了思源黑体感觉阅读稍微舒服点，差别不大。

## 3. 代码块

默认代码块的复制按钮我觉得放上面有点碍眼，保留了但没改样式。主要调整了行距和内边距：

```css
.post-content pre {
  font-size: 0.88rem;
  line-height: 1.5;
}
```

代码块背景用了深色 `#1e293b`，跟默认的灰色做区分。

## 4. 文章页边距和行距

PaperMod 默认文章页间距我觉得有点紧，调整了行距和标题边距：

```css
.post-content {
  line-height: 1.8;
}
.post-content h2 {
  margin: 2em 0 0.8em;
}
```

## 没改的

- 没改导航栏（默认的够用）
- 没加社交图标以外的任何功能
- 没用 Shortcodes
- 没用 Profile Mode

PaperMod 的好处就是默认够好，我只动了真正觉得不舒服的几个像素。
