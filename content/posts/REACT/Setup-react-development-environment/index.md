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


# Create React App

Create your eact project with following commands

    npx create-react-app myapp
    cd myapp
    npm start


the most important files in your project will now show up like this:

    myapp
    ├── node_modules
    ├── public
    │   └── index.html
    ├── src
    │   ├── App.css
    │   ├── App.js
    │   ├── index.css
    │   └── index.js
    └── packages.json

# Install React Developer Tools
React dev tools for Chrome: https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi

React dev tools for Firefox: https://addons.mozilla.org/en-GB/firefox/addon/react-devtools/


#  Start developing your application

You can start by editing **App.js** file. There are two way to code new components.

## Component as a Class

    import { Component } from 'react';
    class App extends Component (){
        constructor(){
            super();
            this.state = { name:'Ernest' }
        }
        render(){
            return (
                <div>
                    <h1> Hello {this.state.name} </h1>
                    <button onClick={()=>{ this.setState({ name:'Noah'})} }>
                        Change Name
                    </button>
                </div>
            )
        }
    }



