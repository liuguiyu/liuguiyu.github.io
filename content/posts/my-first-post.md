---
title: "Building My GitHub Blog with Hugo and PaperMod: From 404 to Deployment"
summary: "In this post, I walk through setting up a blog with Hugo and PaperMod and fixing the deployment problems encountered on GitHub Pages."
date: 2026-08-16
draft: false
tags: ["Hugo", "PaperMod", "Github Pages", "Makedown"]
ShowToc: true
TocOpen: true
categories: Technology
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
hugo new site liuguiyu.github.io
```

## 5. Edit hugo.toml to be:
```toml
baseURL = 'https://liuguiyu.github.io/'
languageCode = 'en-us'
title = 'My Blog'
theme = 'PaperMod'
[params]
  defaultTheme = 'auto'
  ShowReadingTime = true
  ShowShareButtons = true
  ShowPostNavLinks = true
  ShowCodeCopyButtons = true
```

##   6. Create first blog
```powershell
hugo new content/posts/my-first-post.md
```

##   7. Edit the blog 
refer to https://www.markdownguide.org/basic-syntax/

## 8. create .gitignore file 
Make sure the /public folder will never commit to github.
> /public/   
> /resources/   
> .hugo_build.lock   
> .DS_Store

## 9. Verify using git status & git submodule status
```powershell
git status
git submodule status
```

## 10. Commit for the first time 
```powershell
git commit -m "Initial Hugo blog"
```

## 11. Connect to remote GitHub repository 
```powershell
git remote add origin https://github.com/liuguiyu/liuguiyu.github.io.git
git remove -v
```

## 12. Git push, triger Github action
```powershell
git push
```

## 13. 404 error
The site works corretly on localhost, so 404 error normally caused by invalid hugo.yml, try use Hugo recommaned configuration. 

## 14. GitHub Pages Deployment Failed
The GitHub Actions log showed:
> Creating Pages deployment failed
and
> status: 503  
> No server is currently available to service your request.
The failure happened when GitHub tried to create the Pages deployment. I checked with Copilot, turns out GitHub itself was experiencing an outage.
refer to: https://devops.com/github-hit-by-widespread-outage-halting-work-for-global-developers/
![GitHub issue](/images/hugo-blog/unicorn.png)