---
title: "React - Start a React-application"
#summary: "How to setup OpenMediaVault as a backup server"
categories: ["React", "Web Development"]
tags: ["React", "Web Development"]
date: 2022-02-12
weight: 2
author: "Sabbadin Stefy"
draft: False
---


Writing a React.js app involves several steps, from setting up your development environment to deploying the app. Here's a step-by-step guide to help you create a basic React.js app:


# Prerequisites:


## 1. Node.js and npm:
Make sure you have Node.js and npm (Node Package Manager) installed on your machine. You can download them from https://nodejs.org/

## 2.Create React App:
React provides a tool called Create React App that sets up a new React project with a good default configuration. To install it, open your terminal and run:

    npx create-react-app your-app-name

Replace **your-app-name** with the desired name for your project.

# Project Structure:

Your React app project structure will look like this:

    your-app-name/
    ├── node_modules/
    ├── public/
    │   ├── index.html
    │   └── ...
    ├── src/
    │   ├── index.js
    │   ├── App.js
    │   └── ...
    ├── package.json
    └── ...

# Development:

## 1. Navigate to Your App's Directory:

Change into your app's directory:

    cd your-app-name

## 2. Run the Development Server:

Start the development server:

    npm start

This command will open a new browser window/tab with your React app running at http://localhost:3000.

# Components and Styling:

## 1.Create Components:

In the **src** folder, create components for different parts of your app. For example, you can create a **Header.js** and a **Footer.js** component

## 2. Styling:

Style your components using CSS or a styling library like styled-components. Import your styles in the corresponding components.

# State and Props:

## 1. State

Use the useState hook to manage state within your components.

    import React, { useState } from 'react';

    function ExampleComponent() {
        const [count, setCount] = useState(0);

        return (
            <div>
            <p>You clicked {count} times</p>
            <button onClick={() => setCount(count + 1)}>
                Click me
            </button>
            </div>
        );
    }

## 2. Props:

Pass data between components using props.

    // ParentComponent.js
    import React from 'react';
    import ChildComponent from './ChildComponent';

    function ParentComponent() {
        const data = 'Hello from Parent!';

        return (
            <ChildComponent message={data} />
        );
    }

    // ChildComponent.js
    import React from 'react';

    function ChildComponent(props) {
        return (
            <p>{props.message}</p>
        );
    }


# Routing:

## 1. React Router:

If your app has multiple pages, use React Router for navigation.

    npm install react-router-dom


Example usage:

    // App.js
    import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
    import Home from './components/Home';
    import About from './components/About';

    function App() {
    return (
        <Router>
        <Switch>
            <Route path="/" exact component={Home} />
            <Route path="/about" component={About} />
        </Switch>
        </Router>
    );
    }


# Build and Deployment:

## 1. Build:
When you're ready to deploy your app, create a production build:

    npm run build

This command generates optimized and minified production-ready files in the **build** folder.

## 2. Deployment:

You can deploy your app to platforms like Netlify, Vercel, GitHub Pages, or any other hosting service. Follow their respective documentation for deployment instructions.

Congratulations! You've created a basic React.js app. This guide covers the fundamentals, and you can explore more advanced topics as you gain experience with Reac

