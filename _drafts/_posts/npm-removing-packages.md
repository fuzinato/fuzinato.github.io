---
layout: post
title: 'npm: Removing packages'
date: 2018-01-13 00:00:00 +0000
category: ''
tags: ''
resources: ''
---
To uninstall and remove from _package.json_ and _node_modules_ run `npm rm <package>`.
Sometimes it can happened that node package in not needed anymore, and we might remove it from _package.json_. To make sure this package is also removed from node_modules as well, run `npm prune`  

To uninstall global package, run `npm rm -g <package>`