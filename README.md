# UI-JSTechNotes
Going to have concepts of Styles(CSS3, BootStrap, LESS, SASS), Task Runners(Grunt, Gulp), HTML5, Javascript(Jquery, Ajax, ES5, ES6, ES7, ESNext, TypeScript, Angular, React(Thunk, Saga, Axios, Tiles, redux, redux-forms,react-helmet,recompose, reselect, redux-act, redux-persist, redux-persist-transform-filter), Node(Express, Https))


<a id="top"></a>

---

## Index

- [Styles Related Tech](#styles-related-tech)
  - [1. CSS3](#1.-css3)
  - [2. BootStrap](#2.-bootstrap)
  - [3. LESS](#3.-less)
- [Node](#node)

## Styles Related Tech


### 1. CSS3

## Node
Node.js runs single-threaded, non-blocking, asynchronously programming, which is very memory efficient.

Node Can Do:
Node.js can generate dynamic page content
Node.js can create, open, read, write, delete, and close files on the server
Node.js can collect form data
Node.js can add, delete, modify data in your database

Creating Node Server:

var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.end('Hello World!');
}).listen(8080);

Creating own module in Node:

exports.myDateTime = function () {
  return Date();
};

Read the Query String and Split:
http://localhost:8080/?year=2017&month=July

var http = require('http');
var url = require('url');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  var q = url.parse(req.url, true).query;
  var txt = q.year + " " + q.month;
  res.end(txt);
}).listen(8080);
