# Contribution guidelines: 

## Table of contents:
1) [Prologue](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#1-prologue)
2) [How Github-pages work](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#2-how-github-pages-work)
3) [Editing/Adding new links](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#3-editingadding-new-links)
4) [Generating HTML lectures from PDF/PPTX files (Using Libre-office)](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#4-generating-html-lectures-from-pdfpptx-files-using-libre-office)
5) [Integrating HTML websites into the generated github-page](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#5-integrating-html-websites-into-the-generated-github-page)
6) [Pushing bug fixes changes guide (branch naming, commits and PRs)](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#6-pushing-bug-fixes-changes-guide-branch-naming-commits-and-prs)
7) [Pushing new features guide (branch naming, commits and PRs)](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#7-pushing-new-features-guide-branch-naming-commits-and-prs)
8) [Updating your local repository with the remote repository](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#8-updating-your-local-repository-with-the-remote-repository)
9) [Creating issues at this repository](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/CONTRIBUTING.md#9-creating-issues-at-this-repository)
-----------------------------------

### 1) Prologue:

This roadmap is provided by gdsc-sohag under [GPLv3 open-source license](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/LICENSE).

**To contribute to this repository (edit/add new links, edit/add/generate new lectures on docs, edit/add custom websites) follow this guide.**

### 2) How Github-pages work: 

- Every repository you create under your account is accompained by a domain that host your github-page when deploying it.
- Github-pages deploys web-pages using [Docker](https://www.docker.com/) on an Ubuntu virtual server, in general you don't need to touch or know any 
of the linux virtualization processes as it's an automated process.
- To publish a user site, you must create a repository owned by your personal account that's named `<username>.github.io`. 
- To publish an organization site, you must create a repository owned by an organization that's named `<organization>.github.io`, for example `google-developers-sohag.github.io/Embedded-Systems-Roadmap`.
- The source files for a project site are stored in the same repository as their project. 
- Steps to reproduce the automated github-page on your own: 
  
| Illustrations | Steps |
|----------------------|-----------|
| ![](https://user-images.githubusercontent.com/60224159/208230918-88ba1b46-da92-4ef0-ad1e-01d798d5372d.png) | 1) Head to the repository settings. <br/>2) Navigate to pages. <br> 3) Activate the `build and deployment from a branch` and select your deployment branch. <br> 4) Optionally restrict the build process to the `./docs` directory. |

- Now you have a working automated deployment to your repo, in this case i am specifying the `./docs` folder as my deployment directory for the site, so docker won't include the rest of the branch in the building process, this saves much time in the deployment process.
- Create a configuration yaml file [_config.yml](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/docs/_config.yml) in your deployment directory `./docs`, with these basic attributes: 
```yml
title: Embedded Systems Tutorial by GDSC-Sohag
description: A concise introduction to embedded engineering and C programming langauge
show_downloads: true
theme: jekyll-theme-slate
```
- For a specific theme, visit [Github-pages supported themes](https://pages.github.com/themes/), however, you can still write your own theme using pure HTML5/CSS3 with a minimal js code.
- For more (as customizing your site and setting up themes with jekyll), refer to the [Github-pages docs](https://docs.github.com/en/pages).

-------------------

### 3) Editing/Adding new links:

- [Markdown](https://www.markdownguide.org/getting-started/) and [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) files inside `./docs` are added to the build and deploy actions performed by github-pages.
- Markdown files are [rendered into HTML files](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/actions/runs/3719082740/jobs/6307710544) in this process with the theme specified previously in the `.scss` assets by the theming engine selected previously in your config yaml file.
- HTML files are included in the build directly.
- The [index.md](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/blob/master/docs/index.md) or `index.html` will be the default homepage for your deployed web-page.
- You can write in both markdown or HTML and the github-pages action will deploy them to your github-page.

-------------------

### 4) Generating HTML lectures from PDF/PPTX files (Using Libre-office): 

> NB: [Libreoffice](https://www.libreoffice.org/get-help/install-howto/windows/) is preferred.

- Using your powerpoint renderer application: `Menu -> File -> Save-as -> Web-page/HTML -> Save as "index.html"` and select the save directory.
- Test your `index.html` and apply your changes to the html code if feasible.

-------------------

### 5) Integrating HTML websites into the generated github-page: 

1) Fork and Clone your fork locally: 
```bash
$ cd ./Projects && git clone https://github.com/[your-username]/Embedded-Systems-Roadmap.git
```
2) Create a new feature branch: 
```bash
$ git checkout master -b feature-a
```
3) Add your generated html directory to the local repo `./docs` deployment folder.
4) Add, commit and push the changes to the new featured branch.
```bash
$ git add ./docs/[feature-a] && git commit -m "docs/feature-a: [details-in-brief]" && git push origin feature-a
```
5) Now, head to **your fork** and create a pull request with some good checkpointed details about your changes.

> A PR's description should be in this form (A tasked PR).
```
Title: 
Feature-added: little description

Description: 
## This PR adds/changes/modifies/deletes the following: 
- [x] Foo-bar-A.
- [ ] Foo-bar-B.
## This PR targets this issue/feature-request: 
- #1242.
```

-------------------

### 6) Pushing bug fixes changes guide (branch naming, commits and PRs).

1) Create a new branch out off the master branch describing the issue in brief.
```bash
$ cd ./Projects/Embedded-Systems-Roadmap && git checkout master -b "foobar-fix"
```
2) Do your fix changes.
3) Now add, commit and push them.
```bash
$ git add ./[directory] && git commit -m "foobar: fixed issue-A" && git push origin foobar-fix
```
4) Now create a PR with this signature.
```
Title: 
Fix: little description

Fix-Description: 
## This PR fixes the following: 
- [x] Foo-bar-A.
- [ ] Foo-bar-B.
## This PR targets this bug: 
- #1342.
```
-----------------
### 7) Pushing new features guide (branch naming, commits and PRs): 

1) Create a new branch out off the master branch describing the feature in brief.
```bash
$ cd ./Projects/Embedded-Systems-Roadmap && git checkout master -b "feature-a"
```
2) Do your fix changes.
3) Now add, commit and push them.
```bash
$ git add ./[directory] && git commit -m "feature-a: added foobars" && git push origin feature-a
```
4) Now create a PR with this signature.
```
Title: 
Feature-added: little description

Description: 
## This PR adds/changes/modifies/deletes the following: 
- [x] Foo-bar-A.
- [ ] Foo-bar-B.
## This PR targets this issue/feature-request: 
- #1242.
```
---------------
### 8) Updating your local repository with the remote repository: 

- Pull with the rebase flag will update your current master local branch with the remote one.
```bash
$ cd ./Projects/Embedded-Systems-Roadmap && git pull origin master --rebase
```
--------------
### 9) Creating issues at this repository: 

> [Issues](https://github.com/Google-Developers-Sohag/Embedded-Systems-Roadmap/milestone/1) should be in this formula
```
 Issue-Title: brief description

Description: 
......
```
