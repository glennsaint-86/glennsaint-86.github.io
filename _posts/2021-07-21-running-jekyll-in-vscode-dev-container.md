---
layout: single
title:  "Running Jekyll in VS Code Dev Container"
date:   2021-07-21 00:05:35 +0800
categories: blog
toc: true
toc_sticky: true
tags: vscode ms-vscode-remote remote-containers Jekyll
#permalink:
published: true
---
I've used Jekyll for this site, before I bought a new PC I was doing my blogs entries it with my Macbook Pro 2011. Since I'm a newbie on Jekyll, I have to set it up all in my Mac. With this new PC, I plan to run it over VS Code Dev Containers to keep my host machine as clean as possible without the need of installing a bunch of development SDKs in the host machine for various type of development.

Luckily VS code does have a prebuild container for Jekyll, below is a sample illustration on where it can be found.
![vscode jekyll dev container](/assets/images/vscode-jekyll-containers-01.gif)

Digging into the `.devcontainer` folder would have 3 files, below are highlighted items from each file on how the container was created:
* Dockerfile
  * Uses `ruby:0-2.7` docker image from MCR (Micorosoft Container Registry)
  * Install Ruby Gem bundler
  * Install the LTS of node
* devcontainer.json
  * Forward to port 4000 (or it can be different) - This is to serve the jekyll locally when hitting the browser http://localhost:4000
  * Forward to port 35729 for live reload server
* post-create.sh
  * Install the Gem bundler version that was download in the Dockerfile
  * Install Jekyll

The experience I had was great and the prebuild container for Jekyll did all the job installing all the dependencies of Jekyll. To know more about VS code dev containers, see [VS Code Dev Containers](https://code.visualstudio.com/docs/remote/create-dev-container).