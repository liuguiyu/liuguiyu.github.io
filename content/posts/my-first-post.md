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

## 0. The Technology Stack
The overall workflow looks like this:

![Hugo GitHub Pages architecture](/images/hugo-blog/tech.png)

## 1. Make sure Hugo version is greater than 0.158.0

Check the Hugo version:

```bash
hugo version
```

## 2. Install PaperMod
```bash
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

## 3. Make a blog directory
```bash
mkdir d:\blog
```

## 4. In the directory, create Hugo site
```bash
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
```bash
hugo new content/posts/my-first-post.md
```

##   7. Edit the blog 
refer to https://www.markdownguide.org/basic-syntax/

## 8. create .gitignore file 
Make sure the /public folder will never commit to github.
```gitignore
/public/   
/resources/   
.hugo_build.lock   
.DS_Store
```

## 9. Verify using git status & git submodule status
```bash
git status
git submodule status
```

## 10. Commit for the first time 
```bash
git commit -m "Initial Hugo blog"
```

## 11. Connect to remote GitHub repository 
```bash
git remote add origin https://github.com/liuguiyu/liuguiyu.github.io.git
git remove -v
```

## 12. Git push, triger Github action
```bash
git push
```

## 13. 404 error
The site works corretly on localhost, so 404 error normally caused by invalid hugo.yml, try use Hugo recommaned configuration. 

## 14. GitHub Pages Deployment Failed
The GitHub Actions log showed:
```bash
Creating Pages deployment failed
```
and
```bash
status: 503  
No server is currently available to service your request.  
```

The failure happened when GitHub tried to create the Pages deployment. I checked with Copilot, turns out GitHub itself was experiencing an outage.    

refer to: https://devops.com/github-hit-by-widespread-outage-halting-work-for-global-developers/  
![GitHub issue](/images/hugo-blog/unicorn.png)

## 15. Add comments and analysis 
create \layouts\partials\comments.html and \layouts\partials\extend_footer.html  
for comments, we can use https://giscus.app/zh-CN  
for analysis, we can use https://busuanzi.ibruce.info/  

## 16. Add SEO
Go to https://search.google.com/search-console/welcome, add your website, google will generate a html for verification, you will need put the html into \static folder.  
