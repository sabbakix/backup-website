---
title: "Flask - Deploy A Flask Application To Your Ubuntu Server"
categories: ["Flask","Ubuntu", "Python", "Linux", "Deployment"]
tags: ["Flask", "Ubuntu", "Python","Linux", "Web Application"]
date: 2021-12-5
weight: 2
author: "Sabbadin Stefy"
---

# Setup an Ubutu Server For Deployment

We will asume that you have a fresh istance of Ubuntu Server at hand.

First step we will create a new user to our Ubuntu Server. In our case we name our user **sir**

    adduser sir

Here the console will ask to enter a **password** for your new user. Choose a strong password that you can easily remenber.

Now we need to give to the new user the ability to run program with the sudo command.

    usermod -aG sudo sir

And switch user

    su - sir

Now we need to copy our Flask application folder to the remote server. We will use secure copy command **scp**

    scp -r flaskAppDir sir@101.102.103.104

The **-r** option let the command run recursively and so the entire folder, in our case *flaskAppDir*, and subfolder will be copied to the remote location. Set the user and ip address accordinly to your case.

Update the Ubuntu server and install the python3 interpreter and the pip3 package manager.

    sudo apt update
    sudo apt upgrade

    sudo apt install python3
    sudo apt install python3-pip
    
    sudo pip3 install virtualenv
    sudo pip3 install flask

    sudo apt install nginx


Configure teh **nano** text editor to use 4 spaces istead of tabs.

    nano .nanorc

Add teh followinf text:

    set tabsize 4
    set tabstospaces


Create an virtual environment for your application. For this we will use the **virtuenv** command

    cd flaskAppDir
    virtualenv venv
    source venv/bin/activate
    
Install wsgi 

    pip3 install uwsgi flask


Open specific port to allow resquest to reach the server.

    sudo ufw allow 8090


Configure WSGI

    nano wsgi.py

Insert the follwing text

    from flaskAppFile import App
    if __name__ == "__main__":
        App.run()

Configura uwsgi

    uwsgi --socket 0.0.0.0:8090 --protocol=http -w wsgi:pp


Exit Virtualenv

    deactivate











