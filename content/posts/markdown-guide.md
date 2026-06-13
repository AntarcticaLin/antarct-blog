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

一篇文章只用一个 `#`。因为 PaperMod 的主题标题本身就是一级标题，文章里再用一级标题就乱了。我从 `##` 开始写。

`#` 和标题文字之间**一定要空格**，否则有些渲染器不认。`##标题` → 改成 `## 标题`。

## 列表

有序列表我都写 `1.`，不写 `1. 2. 3.`。大部分渲染器会自动递增编号，调整顺序时不用改数字。

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
    
    ```text   ← 没有匹配语言也写 text
    纯文本内容
    ```

## 图片

图片放 `static/images/` 下，引用路径 `/images/xxx.jpg`。写的时候我习惯在图片下面加一行说明：

```
![Hugo 目录结构](/images/hugo-dir.jpg)
*`hugo new site` 生成的目录*
```

## Front matter

每篇文章必填 `description`。它会出现在 RSS 和搜索引擎结果里。不填的话 Hugo 会截取文章前几句，有时候截得不完整。

```yaml
description: "没多少技巧，但有些小细节"
tags: ["writing", "markdown"]
```

`tags` 也必填，PaperMod 会自动生成标签导航，方便读者找到同类文章。

## 写作流程

我不用任何 Markdown 编辑器。VS Code 写，Hugo server 实时预览，`git push` 发布。写完后第二天再看一遍——当天检查永远发现不了问题。
