---
description: https://nodejs.org/
---

# 💚 NodeJS

* Node.js is an open source server environment
* Node.js is free
* Node.js runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.)
* Node.js uses JavaScript on the server

## What can NodeJS do?

* Node.js can generate dynamic page content
* Node.js can create, open, read, write, delete, and close files on the server
* Node.js can collect form data
* Node.js can add, delete, modify data in your database



## What is a Node.js File?

* Node.js files contain tasks that will be executed on certain events
* A typical event is someone trying to access a port on the server
* Node.js files must be initiated on the server before having any effect
* Node.js files have extension ".js"\


## Install Node



To get started, you will need to do the following:

1. **Install Node**\
   To install Node, go to [https://nodejs.org/en/](https://nodejs.org/en/) and download either the LTS version or the current version.
2. **Have or Install a Code Editor**\
   You can use any code editor of your choice for this tutorial. However, for the sake of demonstration, we will be using VS Code editor with the plugin prettier and vscode icons.



## Setting Up the Project

Let’s start by creating an empty directory: _**mern**_. This folder will hold all our files after we create a new project. Then we will create a React app—_**client**_—in it.

{% tabs %}
{% tab title="mern" %}
```
mkdir mern
cd mern
npx create-react-app client
```
{% endtab %}
{% endtabs %}



Then, we create a folder for the back end and name it _**server**_.

```
mkdir server
```

Then, we create a folder for the back end and name it _**server**_.

```
mkdir server
```

We will jump into the _**server**_ folder that we created previously and create the server. Then, we will initialize package.json using npm init.

```
cd server
npm init -y
```
