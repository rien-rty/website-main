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
git clone https://github.com/rien-rty/website-main.git
# over SSH with SSH keys
git clone git@github.com:rien-rty/website-main.git
```


