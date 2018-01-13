---
layout: post
title: 'npm: Setting default configuration for npm init'
date: 2018-01-09 00:00:00 +0100
category: npm
tags: npm
resources: https://medium.com/p/422f55a248df/edit
categories: npm
---
After initiating new module (with `npm init -y`) you get default package.json file with mostly empty fields. Setting default values in global configuration can be useful time saver. 
```bash
npm set <key> <value> [-g|--global]
```
For example setting authors name:
```bash
npm set init-author-name "Dario Fuzinato" -g
```
Now every time new package.json is being initiated, author name will be set to it. Here is a list of properties you can change:
- init-author-name
- init-author-email
- init-author-url
- init-license
- init-version

*Note: All settings are stored in .npmrc file in your root folder `~/.npmrc`*