---
title: "How I created this blog"
date: 2022-09-12T10:00:00+00:00
tags: ["go","blog", "hugo"]
author: "Friedrich"
showToc: true
TocOpen: false
draft: false
hidemeta: true
comments: false
description: "quick overview on was done to create this blog"
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
Frist I [installed hugo](https://gohugo.io/getting-started/installing).  

Next, I created two public repos on Github. The first is named `blog` and it will contain the data to work with; adding new pages, editing configs and such. The second is named `friedrichwilken.github.io` and it is where the website will actually be published. I add an empty (for now) `readme.md` in both. Finally I clone `blog` locally.

Okay, in `blog/` I run
```shell
hugo new site friedrichwilken -f yml
```
which creates a new folder `friedrichwilken/` that contains all the needed boilerplate code for Hugo. The `-f yml` cased there to be a `config.yml` instead of the default `config.toml`.

Cool, now I pick a [theme](https://themes.gohugo.io). I will pick [papermod](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-installation/) and do what they recommend:
```shell
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1
```
and edit my  `config.yml` to this:
```
baseURL: https://friedrichwilken.github.io/
languageCode: en-us
title: friedrichwilken
theme: "PaperMod"
```
I run `hugo server -D` and open [http://localhost:1313](http://localhost:1313) to verify that everything is working. Looks fine.

I wanted to go fancy so I created a new template in the `archetype/` dir called `post.md`. Now I can run
```
hugo new --kind post posts/this_blog.md
```
then edit it (it's in `/content/posts/this_blog.md`).

Now I delete the `public/` dir. Then I will add the second repo, `friedrichwilken.github.io` in here as a submodule in a new dir called `public/`:
```shell
git submodule add -b main https://github.com/friedrichwilken/friedrichwilken.github.io.git public
```

To create a the static files I run
```shell
hugo -t PaperMod
```
where PaperMod is my **theme**.

I go to `public/` and commit the changes (they will go to the submodule `friedrichwilken.github.io`).
