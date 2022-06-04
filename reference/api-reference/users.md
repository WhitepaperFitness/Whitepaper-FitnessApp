---
description: https://reactjs.org/
---

# 🌏 ReactJS

React is a JavaScript-based UI development library. Facebook and an open-source developer community run it. Although React is a library rather than a language, it is widely used in web development. The library first appeared in May 2013 and is now one of the most commonly used frontend libraries for web development.

React offers various extensions for entire application architectural support, such as Flux and React Native, beyond mere UI.

{% hint style="info" %}
**Good to know:** If you don’t experience the problems described above or don’t feel comfortable using JavaScript tools yet, consider [adding React as a plain `<script>` tag on an HTML page](https://reactjs.org/docs/add-react-to-a-website.html), optionally [with JSX](https://reactjs.org/docs/add-react-to-a-website.html#optional-try-react-with-jsx).&#x20;
{% endhint %}

## Declarative

React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.

Declarative views make your code more predictable and easier to debug.

## Component-Based

Build encapsulated components that manage their own state, then compose them to make complex UIs.

Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.



## Learn Once, Write Anywhere

\
We don’t make assumptions about the rest of your technology stack, so you can develop new features in React without rewriting existing code.

React can also render on the server using Node and power mobile apps using [React Native](https://reactnative.dev/).



## Create React App

[Create React App](https://github.com/facebookincubator/create-react-app) is a comfortable environment for **learning React**, and is the best way to start building **a new** [**single-page**](https://reactjs.org/docs/glossary.html#single-page-application) **application** in React.

It sets up your development environment so that you can use the latest JavaScript features, provides a nice developer experience, and optimizes your app for production. You’ll need to have [Node >= 14.0.0 and npm >= 5.6](https://nodejs.org/en/) on your machine. To create a project, run

{% tabs %}
{% tab title="NPM" %}


```
npx create-react-app my-app
cd my-app
npm start
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
`npx` on the first line is not a typo — it’s a [package runner tool that comes with npm 5.2+](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b).
{% endhint %}

Create React App doesn’t handle backend logic or databases; it just creates a frontend build pipeline, so you can use it with any backend you want. Under the hood, it uses [Babel](https://babeljs.io/) and [webpack](https://webpack.js.org/), but you don’t need to know anything about them.

When you’re ready to deploy to production, running `npm run build` will create an optimized build of your app in the `build` folder. You can learn more about Create React App [from its README](https://github.com/facebookincubator/create-react-app#create-react-app--) and the [User Guide](https://facebook.github.io/create-react-app/).\


## Setting up the React Application&#x20;

Let’s flesh out the application, but before we do, we need to install two additional dependencies that will be used in our project. Open a new terminal emulator, navigate to the “client” directory, and install `bootstrap` and `react-router-dom`.

```
npm install bootstrap react-router-dom
```

`bootstrap` lets you quickly deploy a template and components for your new web application without having to do everything from scratch. And, the `react-router-dom` installs React router components for web applications. Make sure your server application is still running!



## Setting Up the React Router <a href="#setting-up-the-react-router" id="setting-up-the-react-router"></a>

Let's start by emptying the _**src**_ folder and adding two new files in it: **index.js** and **App.js**.

```
rm src/**/*
touch src/index.js src/App.js
```

Inside **src/index.js**, we add the following code:

**mern/client/src/index.js**

```jsx
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";
import { BrowserRouter } from "react-router-dom";

ReactDOM.render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```

We have used `BrowserRouter` to keep our UI in sync with the URL. BrowserRouter helps with seamless transitions while switching between components. Basically, it will only reload/refresh the component that needs to be changed instead of refreshing/reloading the entire page. Though BrowserRouter is not a necessity, it is a must if you want your app to be responsive.\
