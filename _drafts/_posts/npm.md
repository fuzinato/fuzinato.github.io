---
layout: post
title: 'npm: List executable commands'
date: 2018-01-17 22:15:48 +0100
category: npm, tips
tags: npm, tips
resources: ''
categories: npm, tips
---
Some packages after local instillation provide custom command (i.e. karma, browserify…) and some don’t. To list all available commands, navigate to `node_modules/.bin` and list directory contents files `ls`. All listed packaged can be executed from npm package.