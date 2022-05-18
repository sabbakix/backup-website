---
title: "React - Setup React development environment"
#summary: "How to setup OpenMediaVault as a backup server"
categories: ["React", "Web Development"]
tags: ["React", "Web Development"]
date: 2021-08-19
weight: 2
author: "Sabbadin Stefy"
draft: False
---

React is one of the most popular frontend framework, and for a good reason. It allow you to build your frontend application using components. Which are elements that encapsulate functionalities, visual elements, and data, into single units, that you can reuse, like lego blocks. Allowing you to organize and nest your components into a large and articulate application.


# Setup
To start developing your react app, you will need to install some tools:


VsCode or your text editor of choice. https://code.visualstudio.com/

Node with npm, we sugest the LTS stable version. https://nodejs.org/en/
Once  node  and npm are instaled check versions:

    node -v
    npm -v

To update your node version you can install NVM on windows: https://github.com/coreybutler/nvm-windows or on linux https://github.com/nvm-sh/nvm#installation-and-update.

    nvm install lts
    nvm list
    nvm use xx.xx.xx

if you prefer *yarn* instead of npm, you can also install it using 
    
    npm install --global yarn

Check installed version:

    yarn -v


