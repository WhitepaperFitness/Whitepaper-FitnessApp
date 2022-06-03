---
description: https://www.mongodb.com/
---

# 🍃 MongoDB



{% hint style="info" %}
**Knowledge:** MongoDB is a document database with the scalability and flexibility that you want with the querying and indexing that you need
{% endhint %}

## Advantages

* MongoDB **stores data in flexible, JSON-like documents**, meaning fields can vary from document to document and data structure can be changed over time
* The document model **maps to the objects in your application code**, making data easy to work with
* **Ad hoc queries, indexing, and real time aggregation** provide powerful ways to access and analyze your data
* MongoDB is a **distributed database at its core**, so high availability, horizontal scaling, and geographic distribution are built in and easy to use
* MongoDB is **free to use**. Versions released prior to October 16, 2018 are published under the AGPL. All versions released after October 16, 2018, including patch fixes for prior versions, are published under the [Server Side Public License (SSPL) v1](https://www.mongodb.com/licensing/server-side-public-license).

## Install the library

We will also install the dependencies.

{% tabs %}
{% tab title="NPM" %}
```
# Install via NPM
npm install mongodb express cors dotenv
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**Good to know:** command installs MongoDB database driver that allows your Node.js applications to connect to the database and work with data.
{% endhint %}

## Connecting to MongoDB Atlas

It’s time to connect our server to the database. We will use MongoDB Atlas as the database. MongoDB Atlas is a cloud-based database service that provides robust data security and reliability. MongoDB Atlas provides a free tier cluster that never expires and lets you access a subset of Atlas features and functionality.

Follow the [Get Started with Atlas](https://docs.atlas.mongodb.com/getting-started/) guide to create an account, deploy your first cluster, and locate your cluster’s connection string.

Now that you have the connection string, go back to the ‘_server_’ directory and create a ‘_config.env_’ file. There, assign the connection string to a new `ATLAS_URI` variable. Once done, your file should look similar to the one below. Replace `<username>` and the `<password>` with your database username and password.

{% hint style="info" %}
**mern/server/config.env:** ATLAS\_URI=mongodb+srv://:@sandbox.jadwj.mongodb.net/employees?retryWrites=true\&w=majority PORT=5000
{% endhint %}

Create a folder under the **server** directory—_**db**_—and inside it, a file—_**conn.js**_. There we can add the following code to connect to our database.

**mern/server/db/conn.js**

{% tabs %}
{% tab title="JS" %}
```javascript
// require the myapi module and set it up with your API key
const { MongoClient } = require("mongodb");
const Db = process.env.ATLAS_URI;
const client = new MongoClient(Db, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
});
 
var _db;
 
module.exports = {
  connectToServer: function (callback) {
    client.connect(function (err, db) {
      // Verify we got a good "db" object
      if (db)
      {
        _db = db.db("employees");
        console.log("Successfully connected to MongoDB."); 
      }
      return callback(err);
         });
  },
 
  getDb: function () {
    return _db;
  },
};
```
{% endtab %}
{% endtabs %}
