---
layout: post
title: GitLab prohibits force push to master branch
date: 2018-01-05 00:00:00 +0000
category: git
tags: git, gitlab
resources: https://about.gitlab.com/2014/11/26/keeping-your-code-protected/
---
As I was making major changes to one project, I've **-f** pushed only to be rejected. After few stubborn attempts I cared to read the error message on console: `remote: GitLab: You are not allowed to force push code to a protected branch on this project`. Indeed, it seems that GitLab is protecting master branch from force pushing (as well as deleting it).

Protection can be disabled/added via _Settings > Repository > Protected Branches_