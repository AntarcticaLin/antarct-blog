+++
title = '如何用手机更新这个博客'
date = 2026-08-15
description = '没有后台也能随时写文章：手机浏览器直接发。'
tags = ['hugo', 'blog', 'workflow']
+++

之前写过这个博客没有后台、手机上不好写文章。其实有办法：**GitHub 网页版就能发文章**，整个过程不需要电脑，也不需要装任何 App。

<!--more-->

## 原理

这个博客是 Hugo + GitHub Pages，文章就是一个 Markdown 文件。GitHub 的网页版支持直接编辑仓库里的文件，编辑完保存就是一次提交，提交后 GitHub Actions 自动构建部署。

所以"在手机上写文章" = "在 GitHub 网页版新建一个 Markdown 文件"。

## 操作步骤

**1. 打开仓库的 posts 目录**

手机浏览器访问：
`https://github.com/AntarcticaLin/antarct-blog/tree/main/content/posts`

**2. 新建文件**

点右上角 **Add file → Create new file**。

文件名规则：`文章名.md`（用英文或拼音，比如 `my-new-post.md`）。中文文件名 GitHub 也支持，但英文更保险。

**3. 写内容**

文件开头要有 front matter（文章的"身份证"）：

```markdown
+++
title = '文章标题'
date = 2026-08-16  # 改成写文章当天的日期
description = '一句话摘要，会显示在搜索结果里'
tags = ['tag1', 'tag2']
+++

正文从这里开始，用 Markdown 写。
```

正文写好保存，文章就发布了。整个流程约 1 分钟。

## 小技巧

- **手机浏览器打开 GitHub 网页版，用"桌面版网站"模式**，界面更好操作
- 先写一篇测试文章试试流程，成功后再删掉
- 图片暂时不方便传，手机发文先以文字为主
- 没灵感的时候可以先把标题和 front matter 写好，正文慢慢填，随时保存（GitHub 允许中途保存为草稿，只要文件不推送到 main 就行——新建文件时选 **Create a new branch** 即可，之后合并）

## 局限性

- GitHub 网页版的编辑器比 VS Code 弱，没有实时预览
- 图片上传麻烦（GitHub 支持拖拽上传，但手机上不太好操作）
- 每次保存就是一次提交，GitHub Actions 会重新部署，频繁保存会触发多次构建（GitHub 免费版 Actions 有额度，个人博客完全够用）

对偶尔想记点东西的场景，这个方案足够了。正经写长文还是电脑上舒服，但"手机只能看不能写"的痛点算解决了。
