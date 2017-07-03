# NodeJS | Express 




Create folder anywhere on system where project folder will reside (preferebly in documents or direct under user)

```git
$ mkdir <projectfoldername>
```


Initialize NPM

```git
$ npm init
```


Open project inside of text editor (atom, sublime) &  create server.js file inside root of project folder
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/9096788e-dd24-4c4e-86ac-76ce4b424c14/00000015.png)


Include the following code inside of server.js

```javascript
var express = require ('express');   // telling server to use express

var app = express(); // to get express commands with app.

app.get('/', function(req, res) {   // <--- this is the function that creates the
  var name = "Batman";                   //home page.
  res.json("My name is " + name);
});

app.listen(3000, function(err) {    // viewable URL at localhost:3000
  if (err) throw err;
  console.log("Server is Running");
});

```


Install express

```git
$ npm install express --save
```


To automatically refresh server after project changes use [nodemon](https://www.npmjs.com/package/nodemon)

```git
$ sudo npm install nodemon -g
```


Run server

```git
$ nodemon server
```
