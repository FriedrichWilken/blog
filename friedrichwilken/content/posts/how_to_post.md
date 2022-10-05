---
title: "how to create a new post in hugo"
date: 2022-09-15T11:30:03+00:00
tags: ["go","blog","hugo"]
author: "Friedrich"
showToc: false
TocOpen: false
draft: false
hidemeta: true
comments: false
description: "super short, how I create another blog pos"
canonicalURL: "https://friedrichwilken.github.io"
disableHLJS: true # to disable highlightjs
disableShare: false
disableHLJS: false
hideSummary: false
searchHidden: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
editPost:
    URL: "https://github.com/friedrichwilken/blog/friedrichwilken/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link
---
To create a new blog post I run:
```bash
hugo new --kind post posts/<name of my new post>.md
```
(I created a template dubbed *post*. This is why I can use `--kind post`. Templates are called `archetypes` in hugo and so you can find the template under `/archetype`.)
Then I edit my post, commit and push it's changes. Boom.
