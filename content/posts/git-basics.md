+++
title = '工作中真正在用的 Git 命令'
date = 2026-06-13
description = '不是教程，是我的日常操作'
tags = ['git', 'dev']
comments = true
+++

学了无数次 Git，记住的就那么几个命令。这是我每天真正在用的：

<!--more-->

## 核心循环

```bash
git status       # 先看看改了什么
git add -A       # 全部暂存
git commit -m "feat: xxx"   # 提交
git push         # 推送
```

就这四个。

## 分支

```bash
git checkout -b feature/xxx   # 开新分支
git checkout main             # 切回主分支
git merge feature/xxx         # 合并
git branch -d feature/xxx     # 删掉已合并的分支
```

命名规范：`feature/xxx`、`fix/xxx`、`refactor/xxx`。

## 拉取代码

```bash
git pull --rebase
```

我配了 `pull.rebase true`，所以直接 `git pull` 就是 rebase 模式。好处是提交历史是直线，没有多余的 merge commit。

rebase 冲突了怎么办：

```bash
# 解决文件冲突
git add .
git rebase --continue
```

搞不定就 `git rebase --abort` 回到之前的状态。

## 撤销

这是 Git 里最有用的知识——不同状态用不同命令：

| 状态 | 命令 |
|------|------|
| 改了还没 add | `git checkout -- 文件名` |
| 已经 add 了 | `git reset HEAD 文件名` |
| 已经 commit 了 | `git reset --soft HEAD~1` |
| 已经 push 了 | `git revert HEAD`（不是 reset） |

记住 `git revert` 而不是 `git reset` 去撤销已经推送的提交——`reset` 会改写历史，其他人会遭殃。

## 看历史

```bash
git log --oneline         # 简洁版
git log --oneline --graph # 带分支图
```

我配了别名：

```bash
git config --global alias.lg "log --oneline --graph --all"
```

现在用 `git lg` 看所有分支的拓扑。

## .gitignore

每个项目第一时间配 `.gitignore`。我遇到过同事把 `.env` 提交到仓库的事，密钥全在 GitHub 上裸奔。

```
.env
node_modules/
build/
.idea/
.DS_Store
```

## 一些习惯

- 提交信息按 [Conventional Commits](https://www.conventionalcommits.org/) 规范：`feat:` `fix:` `chore:` `docs:`。不是为了好看，是为了以后能 `git log --grep "feat"` 快速筛选
- 一个提交只做一件事。"修复登录页白屏和更新 README" 应该拆成两个提交
- `git push` 前先 `git pull --rebase`，避免推送被拒绝
- 不确定的命令先用 `git xxx --help` 看文档

Git 不需要背命令，记住 `add → commit → push` 这个循环，其他随用随查就行。
