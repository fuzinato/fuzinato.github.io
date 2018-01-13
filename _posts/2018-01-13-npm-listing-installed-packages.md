---
layout: post
title: 'npm: Listing installed packages'
date: 2018-01-13 00:00:00 +0000
category: npm, tips
tags: npm, tips, cli
resources: ''
---
To get list of installed packages in current folder run`npm ls` or `npm ls -g` to list globally installed packages. 

To view only portion of the list, i.e. to display max depth of the dependency tree, there is a useful flag `--depth=<number>` .   
Whole command looks like this: `npm ls --depth=0` or
`npm ls --depth=1 -g`

Note: If some packages are not registered in _npm_ registry, there will be marked with “extraneous”