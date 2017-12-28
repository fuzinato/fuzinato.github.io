---
layout: post
title: Renaming git branch
date: 2017-12-28 00:00:00 +0000
category: git
tags: git
resources: https://multiplestates.wordpress.com/2015/02/05/rename-a-local-and-remote-branch-in-git/
updated: ''
published: ''
---
If there is a need to rename a git branch follow these steps.

## Rename your local branch

 If you are on the branch you want to rename run:
 ```bash
 git branch -m new_name
 ```
 or if you are on a different branch run:
 ```bash
 git branch -m old_name new_name
 ```

## Push to remote
```bash
git push origin new_name
```
or
```bash
git push origin HEAD
```
if you don't want to type name of new branch (git can obtain the branch name itself)

## Delete old remote branch
In case old branch is already on remote, you will need to delete it:
```bash
git push origin :old_branch
```