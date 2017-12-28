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
## Rename your local branch

 If you are on the branch you want to rename run
 ```bash
 git branch -m new_name
 ```
 
and push it to remote.

## Delete old remote branch
In case old branch is already on remote, you will need to delete it:
```bash
git push origin :old_branch
```