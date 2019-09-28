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


### 1. CSS3 - Cascading Style Sheets
Advantages of CSS
CSS saves time − You can write CSS once and then reuse same sheet in multiple HTML pages.
Pages load faster − If you are using CSS, you do not need to write HTML tag attributes every time. Just write one CSS rule of a tag and apply it to all the occurrences of that tag. So less code means faster download times.
Easy maintenance − To make a global change, simply change the style, and all elements in all the web pages will be updated automatically.
Superior styles to HTML − CSS has a much wider array of attributes than HTML, so you can give a far better look to your HTML page in comparison to HTML attributes.
Multiple Device Compatibility − Style sheets allow content to be optimized for more than one type of device. By using the same HTML document, different versions of a website can be presented for handheld devices such as PDAs and cell phones or for printing.
Global web standards − Now HTML attributes are being deprecated and it is being recommended to use CSS. So its a good idea to start using CSS in all the HTML pages to make them compatible to future browsers.

Who Creates and Maintaines CSS:
CSS is created and maintained through a group of people within the W3C called the CSS Working Group. The CSS Working Group creates documents called specifications. When a specification has been discussed and officially ratified by the W3C members, it becomes a recommendation

CSS Versions
Cascading Style Sheets level 1 (CSS1) came out of W3C as a recommendation in December 1996. This version describes the CSS language as well as a simple visual formatting model for all the HTML tags.

CSS2 became a W3C recommendation in May 1998 and builds on CSS1. This version adds support for media-specific style sheets e.g. printers and aural devices, downloadable fonts, element positioning and tables.

CSS Syntax:
A CSS comprises of style rules that are interpreted by the browser and then applied to the corresponding elements in your document. A style rule is made of three parts −

Selector − A selector is an HTML tag at which a style will be applied. This could be any tag like <h1> or <table> etc.

Property − A property is a type of attribute of HTML tag. Put simply, all the HTML attributes are converted into CSS properties. They could be color, border etc.

Value − Values are assigned to properties. For example, color property can have value either red or #F1F1F1 etc.

You can put CSS Style Rule Syntax as follows −

selector { property: value }
table{ border :1px solid #C00; }

Various Selectors: Selecting specific type
The Type Selectors:
h1 {
   color: #36CFFF; 
}

The Universal Selectors: Rather than selecting elements of a specific type, the universal selector quite simply matches the name of any element type −

* { 
   color: #000000; 
}

The Descendant Selectors
Suppose you want to apply a style rule to a particular element only when it lies inside a particular element. 
Example, style rule will apply to <em> element only when it lies inside <ul> tag.

ul em {
   color: #000000; 
}

The Class Selectors: You can define style rules based on the class attribute of the elements. All the elements having that class will be formatted according to the defined rule.

.black {
   color: #000000; 
}

h1.black {
   color: #000000; 
}
This rule renders the content in black for only <h1> elements with class attribute set to black.
  
ID Selectors:
You can define style rules based on the id attribute of the elements. All the elements having that id will be formatted according to the defined rule.
#black {
   color: #000000; 
}
This rule renders the content in black for every element with id attribute set to black in our document.

h1#black {
   color: #000000; 
}
This rule renders the content in black for only <h1> elements with id attribute set to black.
The true power of id selectors is when they are used as the foundation for descendant selectors, For example −

#black h2 {
   color: #000000; 
}
In this example all level 2 headings will be displayed in black color when those headings will lie with in tags having id attribute set to black.

The Child Selectors: which is very similar to descendants but have different functionality. Consider the following example −

body > p {
   color: #000000; 
}
This rule will render all the paragraphs in black if they are direct child of <body> element. Other paragraphs put inside other elements like <div> or <td> would not have any effect of this rule.
  
The Attribute Selectors
You can also apply styles to HTML elements with particular attributes. The style rule below will match all the input elements having a type attribute with a value of text −

input[type = "text"] {
   color: #000000; 
}
The advantage to this method is that the <input type = "submit" /> element is unaffected, and the color applied only to the desired text fields.

There are following rules applied to attribute selector.

p[lang] − Selects all paragraph elements with a lang attribute.

p[lang="fr"] − Selects all paragraph elements whose lang attribute has a value of exactly "fr".

p[lang~="fr"] − Selects all paragraph elements whose lang attribute contains the word "fr".

p[lang|="en"] − Selects all paragraph elements whose lang attribute contains values that are exactly "en", or begin with "en-".

Grouping Selectors
You can apply a style to many selectors if you like. Just separate the selectors with a comma, as given in the following example −

h1, h2, h3 {
   color: #36C;
   font-weight: normal;
   letter-spacing: .4em;
   margin-bottom: 1em;
   text-transform: lowercase;
}



## Node
Node.js run000s single-threaded, non-blocking, asynchronously programming, which is very memory efficient.

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

Node module: URL
var url = require('url');
var adr = 'http://localhost:8080/default.htm?year=2017&month=february';
var q = url.parse(adr, true);

console.log(q.host); //returns 'localhost:8080'
console.log(q.pathname); //returns '/default.htm'
console.log(q.search); //returns '?year=2017&month=february'

var qdata = q.query; //returns an object: { year: 2017, month: 'february' }
console.log(qdata.month); //returns 'february'


Node module: FS

var http = require('http');
var fs = require('fs');
http.createServer(function (req, res) {
  fs.readFile('demofile1.html', function(err, data) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write(data);
    res.end();
  });
}).listen(8080);

fs.appendFile('mynewfile1.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});

fs.open('mynewfile2.txt', 'w', function (err, file) {
  if (err) throw err;
  console.log('Saved!');
});

fs.writeFile('mynewfile3.txt', 'Hello content!', function (err) {
  if (err) throw err;
  console.log('Saved!');
});

var uc = require('upper-case');

var events = require('events');
var eventEmitter = new events.EventEmitter();

//Create an event handler:
var myEventHandler = function () {
  console.log('I hear a scream!');
}

//Assign the event handler to an event:
eventEmitter.on('scream', myEventHandler);

//Fire the 'scream' event:

eventEmitter.emit('scream');


File Upload using node:
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
  res.write('<input type="file" name="filetoupload"><br>');
  res.write('<input type="submit">');
  res.write('</form>');
  return res.end();
}).listen(8080);


Parsing the uploaded file and placing it in temporary location:
var http = require('http');
var formidable = require('formidable');

http.createServer(function (req, res) {
  if (req.url == '/fileupload') {
    var form = new formidable.IncomingForm();
    form.parse(req, function (err, fields, files) {
      res.write('File uploaded');
      res.end();
    });
  } else {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write('<form action="fileupload" method="post" enctype="multipart/form-data">');
    res.write('<input type="file" name="filetoupload"><br>');
    res.write('<input type="submit">');
    res.write('</form>');
    return res.end();
  }
}).listen(8080);


Node Mailer:
var nodemailer = require('nodemailer');

var transporter = nodemailer.createTransport({
  service: 'gmail',
  auth: {
    user: 'youremail@gmail.com',
    pass: 'yourpassword'
  }
});

var mailOptions = {
  from: 'youremail@gmail.com',
  to: 'myfriend@yahoo.com',
  subject: 'Sending Email using Node.js',
  text: 'That was easy!'
};

transporter.sendMail(mailOptions, function(error, info){
  if (error) {
    console.log(error);
  } else {
    console.log('Email sent: ' + info.response);
  }
});
