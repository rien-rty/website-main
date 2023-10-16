# Git Submodules in GitHub: POC

This repository will walk you through how to use GitHub with Git Submodules.

## Create a GitHub account

To do certain actions like push your local changes to the repo you need a GitHub account. GitHub doesn't like simple username+password logins since it's too insecure, so you'll need to setup [Personal access tokens](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) or [SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh). I have no experience with personal access tokens, so I'll be using SSH keys.

## Setup Git

Install Git and if preferred a [GUI](https://git-scm.com/downloads/guis) (the example commands will be for the git cli, since that's what I prefer). To identify yourself with your commits, you'll need to tell Git who you are. This can be done with

```sh
git config --global user.email <your email>
git config --global user.name <your name>
```

## Clone the repository

To get started, clone the repository with

```sh
# over HTTP with personal access tokens
git clone --recurse-submodules https://github.com/rien-rty/website-main.git
# over SSH with SSH keys
git clone --recurse-submodules git@github.com:rien-rty/website-main.git
```

Note: You can always check the status of Git with `git status`.

## Create a branch

Create a new branch to work in and switch to it with

```sh
git checkout -b <branch>
```

The option `-b` is to create a new branch. This is the equivalent as 

```sh
git branch <branch>
git checkout <branch>
```

Make some changes and commit them to the remote with

```sh
# stage your changes
git add *
# commit your changes
git commit -m "commit message"
# upload your changes to the remote
git push origin <branch>
```

## Pull requests

Once you've made some changes and pushed them to a remote branch, you can [create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) in GitHub for it to be merged to the main branch. Once a pull request is created, someone can review it and leave comments on the whole pull request, on a specific file, or on a specific change in the file. I've already created a pull request for the "changes" branch that you can review.

I've now set it up so that you can't directly push to main and a pull request needs to be reviewed by at lease one person before it can be merged into main.

## Submodules

To make changes in a submodule, you just have to go into the directory the submodule is nested in, and use git as if you were in the root of a project, because you are. To create a pull request for a submodule, just go the the corresponding repository and create a pull request. One thing to note is that by making changes in a submodule (creating a branch, commiting things) will mark the folder as altered with the HEAD pointing to one of the latest commit. Committing these changes to the main repo will also set the current commit for that branch. This is why the submodule "plugin" will be checked out in the "changes" branch.
