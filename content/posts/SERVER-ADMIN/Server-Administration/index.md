---
title: "Server Administration"
categories: ["Ubuntu", "Linux", "Deployment","server", "Administration"]
tags: ["Ubuntu", "Linux", "Deployment","server", "Administration"]
date: 2021-08-23
weight: 2
author: "Sabbadin Stefy"
---

# Server Administration

We will assume you have an fresh new instance of Ubuntu hosted somewhere, or you a new create VM on your local computer for development purposes

## Let's create a new user

For security reasons, we will create a new user "weby" with the following command

    adduser weby

and set a password:

    passwd weby

Add the new user to the wheel group

    gpasswd -a weby wheel

