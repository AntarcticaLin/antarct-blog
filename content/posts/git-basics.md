---
title: "从零开始学 Git：常用命令与工作流"
date: 2026-06-13
description: "一篇适合初学者的 Git 入门教程，覆盖日常工作流中最常用的命令"
tags: ["tutorial", "git", "dev"]
comments: true
---

Git 是现代开发的必备技能。不管你是独立开发者还是团队协作，掌握 Git 都能让你的工作更高效。

## 什么是 Git？

Git 是一个分布式版本控制系统。简单说，它能帮你记录文件的每一次修改，随时回退到任意历史版本，还能和他人协作开发。

## 基础概念

在开始之前，先理解三个核心区域：

- **工作区（Working Directory）**：你当前编辑的文件
- **暂存区（Staging Area）**：准备提交的修改
- **仓库（Repository）**：Git 保存历史版本的地方

## 基础配置

安装 Git 后，先设置你的身份：

```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```

其他推荐配置：

```bash
git config --global init.defaultBranch main
git config --global pull.rebase true
```

## 常用命令

### 初始化与克隆

```bash
# 初始化一个新仓库
git init

# 克隆远程仓库
git clone https://github.com/用户名/仓库名.git
```

### 日常操作

```bash
# 查看文件状态
git status

# 添加文件到暂存区
git add 文件名      # 添加单个文件
git add .           # 添加所有变更

# 提交到仓库
git commit -m "feat: 添加新功能"

# 查看提交历史
git log --oneline
```

### 分支操作

```bash
# 查看分支
git branch

# 创建新分支
git branch feature-login

# 切换分支
git checkout feature-login

# 创建并切换（快捷方式）
git checkout -b feature-login

# 合并分支
git checkout main
git merge feature-login

# 删除分支
git branch -d feature-login
```

### 远程仓库

```bash
# 添加远程仓库
git remote add origin https://github.com/用户/仓库.git

# 推送代码
git push origin main

# 拉取最新代码
git pull origin main

# 推送新分支
git push -u origin feature-login
```

## 推荐工作流

### 单人开发

```bash
main 分支 ← 直接在上面开发，简单直接
```

### 功能分支工作流

```bash
main        ← 稳定版本
  └─ feature/login   ← 开发新功能
  └─ feature/header  ← 开发另一个功能
```

开发流程：

```bash
# 1. 从 main 创建功能分支
git checkout -b feature/my-feature

# 2. 开发... 然后提交
git add .
git commit -m "feat: 完成功能开发"

# 3. 切回 main 拉取最新代码
git checkout main
git pull

# 4. 合并功能分支
git merge feature/my-feature

# 5. 推送
git push origin main
```

## 常用 Git 别名

让 Git 用起来更顺手：

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.lg "log --oneline --graph"
```

设置后就可以用 `git st` 代替 `git status` 了。

## 遇到冲突怎么办？

冲突并不可怕。当两个人修改了同一个文件时：

1. Git 会标出冲突位置
2. 手动编辑文件，保留正确的代码
3. 去掉 `<<<<<<<`、`=======`、`>>>>>>>` 标记
4. `git add` 然后 `git commit`

## 结语

Git 其实不需要一次学会所有命令。记住 `add → commit → push` 这个核心循环，然后按需学习其他功能就好。用得越多，越熟练。
