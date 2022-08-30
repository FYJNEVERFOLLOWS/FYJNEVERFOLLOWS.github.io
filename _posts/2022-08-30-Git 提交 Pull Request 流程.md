---
layout: post
title: Git 提交 Pull Request 流程
---

使用 Github / GitLab 等代码协同平台时，需要将本地 master 分支上的修改推送到远端仓库 origin 上，记录一下流程：

# Merge Request / Pull Request 流程 A：
git checkout master（切换到 master 分支）

完成新特性开发 / 其他修改（直接在本地 master 分支上完成新特性开发 / 其他修改）

git pull（确保本地 master 分支是最新的，这个操作如果提示冲突，可以强制拉下来再手动解冲突）

git checkout -b your_branch（切换到新建指定分支）

git add & commit -m ""

git push

在 Github / GitLab 的 Pull Requests / Merge Requests 中提交

# Merge Request / Pull Request 流程 B：
已在本地 your_branch 分支上完成新特性开发 / 其他修改

git checkout master（切换到 master 分支）

git pull（确保本地 master 分支是最新的）

git checkout your_branch（切换到指定分支）

git add & commit

git rebase master（合并 master 到本地分支）

git push

在 Github / GitLab 的 Pull Requests / Merge Requests 中提交

# 其他：
// 在 master 分支时，用 git merge your_branch（合并本地 your_branch 分支到 master）
// git merge 出现冲突时需要手动解冲突（把想要的 code 粘贴到 both modified 的那些文件）后 git add & commit

git 远程分支覆盖本地分支
```shell
git fetch --all
git reset --hard origin/master
git pull
```
更新时保存本地与远程不同的部分：
```shell
git stash
git pull
git stash pop
```
git checkout filename 可使某文件恢复
​
![](https://raw.githubusercontent.com/FYJNEVERFOLLOWS/Picture-Bed/main/202208/image.png)
