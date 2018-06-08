---
layout: post
title: Enabling git hooks on react project
date: 2018-06-08 00:00:00 +0000
category: git
tags: ''
resources: 'https://www.atlassian.com/git/tutorials/git-hooks , '
---
Git hooks are great for running tests before commit or push. After making new file  _pre-commit_ (or _pre-push_) inside _.git/hooks/_ folder and in it list of tasks. You have to make it executable with `chmod +x pre-commit`.
By default, create-react-app executes test with `--watch` flag which will hang and prevent hook to finish. Disable it by adding `--coverage` flag to `npm test` command. To run both unit and integration test prior to commit write:

    #!/bin/sh
    
    npm test -- --coverage && npm run e2e
    RESULT=$?
    [ $RESULT -ne 0 ] && exit 1
    exit 0
    `