---
title: Git命令速查手册
published: 2026-05-04
description: Git命令速查手册请查收~
image: Firefly/src/content/posts/git-cheatsheet/1755946172864.png
tags:
  - Git
category: 技术
pinned: false
author: lanye
licenseName: MIT
password:
---
## 仓库操作

 git init                    # 初始化仓库  
 git clone <url>             # 克隆仓库  
 git remote -v               # 查看远程仓库  
 git remote add origin <url> # 添加远程仓库

## 提交与暂存

 git status                  # 查看工作区状态  
 git diff                    # 查看未暂存的改动  
 git add <file>              # 暂存文件  
 git add .                   # 暂存全部  
 git commit -m "msg"         # 提交  
 git commit --amend          # 修改上次提交

## 分支

 git branch                  # 列出分支  
 git branch <name>           # 新建分支  
 git switch <name>           # 切换分支  
 git switch -c <name>        # 新建并切换  
 git merge <branch>          # 合并分支到当前分支  
 git rebase <branch>         # 变基  
 git branch -d <name>        # 删除分支

## 远程同步

 git pull                    # 拉取并合并  
 git fetch                   # 拉取（不合并）  
 git push                    # 推送  
 git push -u origin <branch> # 首次推送并设上游  
 git push --force            # 强制推送（危险）

## 日志与历史

 git log --oneline           # 简洁日志  
 git log --graph             # 图形化日志  
 git log -3                  # 最近3条  
 git reflog                  # 操作历史（可救命）

## 撤销操作

 git restore <file>          # 撤销工作区改动  
 git restore --staged <file> # 取消暂存  
 git reset --soft HEAD~1     # 撤销commit，保留改动  
 git reset --hard HEAD~1     # 彻底撤销（危险）  
 git revert <commit>         # 反向提交（安全撤销）

## 暂存与拣选

 git stash                   # 暂存当前改动  
 git stash pop               # 恢复暂存  
 git stash list              # 暂存列表  
 git cherry-pick <commit>    # 拣选提交

## 标签

 git tag v1.0                # 创建标签  
 git tag                    # 列出标签  
 git push --tags             # 推送标签

## 合并冲突处理

# 手动编辑冲突文件 → git add → git commit  
git merge --abort           # 放弃本次合并

> **核心流程**：`status → add → commit → pull → push` 覆盖日常 90% 场景。