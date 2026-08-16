---
title: "Use Hugo and PaperMod to set up Github Blog"
date: 2026-08-16
draft: false
---

# Hello Hugo

This post records how I set up this blog using Hugo, PaperMod, and GitHub Pages.

## 1. Make sure Hugo version is greater than 0.158.0

Check the Hugo version:

```powershell
hugo version
```

## 2. Install PaperMod
```powershell
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

## 3. Make a blog directory
```powershell
mkdir d:\blog
```

## 4. In the directory, create Hugo site
```powershell
hugo new project liuguiyu.github.io
```

## 5. Edit hugo.toml to be:
> baseURL = 'https://liuguiyu.github.io/'
>
> languageCode = 'en-us'
>
> title = 'My Blog'
>
> theme = 'PaperMod'
>
> [params]
>   defaultTheme = 'auto'
>
>   ShowReadingTime = true
>
>   ShowShareButtons = true
>
>   ShowPostNavLinks = true
>
>   ShowCodeCopyButtons = true

##   6. Create first blog
```powershell
hugo new content/posts/my-first-post.md
```

##   7. Edit the blog 

