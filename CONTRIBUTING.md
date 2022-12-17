# Contribution guidelines: 

## Table of contents:
1) Prologue.
2) How Github-pages work.
3) Edit/Add new links.
4) Generate HTML lectures from PDF/PPTX files (Using Libre-office).
5) Integrate HTML websites into the generated github-page.
6) Pushing bug fixes changes guide (branch naming, commits and PRs).
7) Pushing new features guide (branch naming, commits and PRs).
8) Updating your local repository with the remote repository.
-----------------------------------

### 1) Prologue:

This roadmap is provided by gdsc-sohag under GPLv3 open-source license.

**To contribute to this repository (edit/add new links, edit/add/generate new lectures on docs, edit/add custom websites) follow this guide.**

### 2) How Github-pages work: 

- Every repository you create under your account is accompained by a domain that host your github-page when deploying it.
- Github-pages deploys web-pages using [Docker](https://www.docker.com/) on an Ubuntu virtual server, in general you don't need to touch or know any 
of the linux virtualization processes as it's an automated process.
- To publish a user site, you must create a repository owned by your personal account that's named <username>.github.io. 
- To publish an organization site, you must create a repository owned by an organization that's named <organization>.github.io.
- The source files for a project site are stored in the same repository as their project. 
- Steps to reproduce the automated github-page on your own: 
  
| Illustrations | Steps |
|----------------------|-----------|
| ![](https://user-images.githubusercontent.com/60224159/208230918-88ba1b46-da92-4ef0-ad1e-01d798d5372d.png) | 1) Head to the repository settings. <br/>2) Navigate to pages. <br> 3) Activate the `build and deployment from a branch` and select your deployment branch. <br> 4) Optionally restrict the build process to the `./docs` directory. |

- Now you have a working automated deployment to your repo, in this case i am specifying the `./docs` folder as my deployment directory for the site, so docker won't include the rest of the branch in the building process, this saves much time in the deployment process.
- For more (as customizing your site and setting up themes with jekyll), refer to the [Github-pages docs](https://docs.github.com/en/pages).

