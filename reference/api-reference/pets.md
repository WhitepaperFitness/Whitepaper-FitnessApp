---
description: https://expressjs.com/
---

# 🌼 Express

## Web Applications

{% hint style="info" %}
**Good to know:** Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications.
{% endhint %}

## APIs

{% hint style="info" %}
**Good to know:** With a myriad of HTTP utility methods and middleware at your disposal, creating a robust API is quick and easy.
{% endhint %}

## Performance

{% hint style="info" %}
**Good to know:** Express provides a thin layer of fundamental web application features, without obscuring Node.js features that you know and love.
{% endhint %}

## Frameworks

{% hint style="info" %}
**Good to know:** Many [popular frameworks](https://expressjs.com/en/resources/frameworks.html) are based on Express.
{% endhint %}

## Setting up&#x20;

After we have ensured that dependencies were installed successfully, we create a file called **server.js** with the following code.:

```
// mern/server/server.js
const express = require("express");
const app = express();
const cors = require("cors");
require("dotenv").config({ path: "./config.env" });
const port = process.env.PORT || 5000;
app.use(cors());
app.use(express.json());
app.use(require("./routes/record"));
// get driver connection
const dbo = require("./db/conn");
 
app.listen(port, () => {
  // perform a database connection when server starts
  dbo.connectToServer(function (err) {
    if (err) console.error(err);
 
  });
  console.log(`Server is running on port: ${port}`);
});

```

Here, we are requiring express and cors to be used. const port process.env.port will access the port variable from the config.env we required.

