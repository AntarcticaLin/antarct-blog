+++
title = '我写博客的 Markdown 习惯'
date = 2026-06-13
description = '没多少技巧，但有些小细节'
tags = ['writing', 'markdown']
comments = true
+++

Markdown 没什么好教的，语法就那么多。说几个我写博客时注意到的小事情。

<!--more-->

## 标题

Markdown 本身可以写一级标题，但在这个博客里，PaperMod 已经把文章标题渲染成一级标题，所以正文从 `##` 开始写，层级更清楚。

`#` 和标题文字之间**一定要空格**，否则有些渲染器不认。`##标题` → 改成 `## 标题`。

## 列表

有序列表的每一项我都写 `1.`。大部分渲染器会自动递增编号，调整顺序时不用改数字：

```markdown
1. 第一项
1. 第二项
1. 第三项
```

## 链接

链接描述文字不要写"点击这里"或"详情"。写有意义的话：

```
❌ 详情请看这里
✅ 详情请看 [Hugo 官方文档](https://gohugo.io)
```

屏幕阅读器会一条条读链接，"点击这里"没有任何上下文。

## 代码块

代码块一定要标注语言。不标的话没有语法高亮，代码看起来一片灰：

```python
def hello():
    print("hi")
```

```text
纯文本内容
```

## 图片

图片放 `static/images/` 下，引用路径 `/images/xxx.jpg`。写的时候我习惯在图片下面加一行说明：

```
![Hugo 目录结构](/images/hugo-dir.jpg)
*`hugo new site` 生成的目录*
```

## Front matter

我会给每篇文章写 `description`。它会出现在 RSS 和搜索引擎结果里；不填时 Hugo 通常会截取文章前几句，有时不够完整。

```yaml
description: "没多少技巧，但有些小细节"
tags: ["writing", "markdown"]
```

我也会补上 `tags`，让 PaperMod 生成标签导航，方便读者找到同类文章。

## 写作流程

我不用任何 Markdown 编辑器。VS Code 写，Hugo server 实时预览，`git push` 发布。写完后第二天再看一遍——当天检查永远发现不了问题。
