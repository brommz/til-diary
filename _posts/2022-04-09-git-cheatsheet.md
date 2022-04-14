---
layout: post
title: "GIT cheatsheet"
date: 2022-04-09 12:00:00 +0100
description: ""
img:  # Add image post (optional)
---

```bash
git init

git config
  - --global
  - --local
  - --system
  - --list

git config --global core.editor "nano"

# Git stage filtered
git add *.files*

# Edit last commit
git commit --amend
git commit --amend --author="Rosa, Bartlomiej, brommz@brommz.brommz"
git commit --fixup=commitId

git fetch origin
git checkout --track origin/branch

# Clean all nontracking oraz ignored files and dirs
git clean -fdx

# Clean old branches locally (WSL or git bash)
1. git checkout develop
2. git branch --merge (listuje branche zmergowane do develop)
3. git branch -D `git branch --merge` (usuwa te branche)

#  Clean old branches locally on Windows
git branch --format "%(refname:short)" --merged  | Out-GridView -PassThru | % { git branch -d $_ }

# Delete prune branches (which tracks delete remote branches)
git remote prune origin --dry-run

# List of all files changed in a commit:
git diff-tree --no-commit-id --name-only -r <commit-ish>

# Gid diff between commits:
git diff from-commit to-commit

# Git diff between branches:
git diff develop..feature/branch_name

# Git log commits difference USEFUL - show you commits that branch has but develop doesn't.
git log develop..branch

# Git log only n-commits from top from tip
git log -n 3

# Git log (short-text version)
git log --oneline

# Git log visualize tree
git log --graph --all --decorate --oneline

# Return commit where topic branch diverges (last common commit for branches)
git log -1 \$(git merge-base master feature_branch)

# Rebase onto other branches
git rebase --onto newbase old_branch new_branch

# Rebase current branch to tip of master
git rebase master

# Rebase feature_branch to tip of master
git rebase master feature_branch

# Rebase conflicts
git rebase --continue
git rebase --skip
git rebase --abort

# Rebase interactive last N-commits (3 commit for example)
git rebase -i HEAD~3

# Rebase pull
git pull -r
git pull --rebase=interactive

# Git blame lines 100-105
git blame -L 100,+5 -w file

# Git bisect
git bisect start
gi bisect bad sha1commit/HEAD
git bisect good sha1commit

# Cherry-pick commits range
git cherry-pick 3855fc14005..1706330b39b

# Cherry-pick listy commitów:
git rev-list --reverse --grep '^commitname' release..develop
git cherry-pick $(git rev-list --reverse --grep '^commitname' release..develop)

# GIT ALIASES
git config --global alias.forg 'fetch origin'



```
