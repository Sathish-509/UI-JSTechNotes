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


If you’re wanting to style occurrences of a certain class inside another class, you can write the following:
.nav .nav-item { ... }
The above targets any .nav-item inside .nav. If you only want those that are immediately inside the .nav as opposed to any level deep, you can add the > character, like so:

.nav > .nav-item { ... }
Want to target a button only if it’s next to another button? The + character has got you covered:

.button + .button { ... }

h1, h2, h3 {
   color: #36C;
   font-weight: normal;
   letter-spacing: .4em;
   margin-bottom: 1em;
   text-transform: lowercase;
}

Embedded CSS - The <style> Element
  
  <head>
      <style type = "text/css" media = "all">
         body {
            background-color: linen;
         }
         h1 {
            color: maroon;
            margin-left: 40px;
         }
      </style>
   </head> 
   
Inline CSS - The style Attribute
You can use style attribute of any HTML element to define style rules. These rules will be applied to that element only. Here is the generic syntax −

<element style = "...style rules....">
  
External CSS - The <link> Element
  <head>
   <link type = "text/css" href = "..." media = "..." />
</head>

Now you can include this file mystyle.css in any HTML document as follows −

<head>
   <link type = "text/css" href = "mystyle.css" media = " all" />
</head>
Imported CSS - @import Rule
@import is used to import an external stylesheet in a manner similar to the <link> element. Here is the generic syntax of @import rule.

<head>
   <@import "URL";
</head>
  
 <head>
   <@import url("URL");
</head>
Example
Following is the example showing you how to import a style sheet file into HTML document −

<head>
   @import "mystyle.css";
</head>
CSS Rules Overriding
We have discussed four ways to include style sheet rules in a an HTML document. Here is the rule to override any Style Sheet Rule.
Any inline style sheet takes highest priority. So, it will override any rule defined in <style>...</style> tags or rules defined in any external style sheet file.
Any rule defined in <style>...</style> tags will override rules defined in any external style sheet file.
Any rule defined in external style sheet file takes lowest priority, and rules defined in this file will be applied only when above two rules are not applicable.

Handling old Browsers
There are still many old browsers who do not support CSS. So, we should take care while writing our Embedded CSS in an HTML document. 

<style type = "text/css">
   <!--
      body, td {
         color: blue;
      }
   -->
</style>
CSS Comments
 /*.....this is a comment in style sheet.....*/.
 
 Unit	Description	Example
%	Defines a measurement as a percentage relative to another value, typically an enclosing element.	p {font-size: 16pt; line-height: 125%;}
cm	Defines a measurement in centimeters.	div {margin-bottom: 2cm;}
em	A relative measurement for the height of a font in em spaces. Because an em unit is equivalent to the size of a given font, if you assign a font to 12pt, each "em" unit would be 12pt; thus, 2em would be 24pt.	p {letter-spacing: 7em;}
ex	This value defines a measurement relative to a font's x-height. The x-height is determined by the height of the font's lowercase letter x.	p {font-size: 24pt; line-height: 3ex;}
in	Defines a measurement in inches.	p {word-spacing: .15in;}
mm	Defines a measurement in millimeters.	p {word-spacing: 15mm;}
pc	Defines a measurement in picas. A pica is equivalent to 12 points; thus, there are 6 picas per inch.	p {font-size: 20pc;}
pt	Defines a measurement in points. A point is defined as 1/72nd of an inch.	body {font-size: 18pt;}
px	Defines a measurement in screen pixels.	p {padding: 25px;}

You can specify your color values in various formats. Following table lists all the possible formats −

Format	Syntax	Example
Hex Code	#RRGGBB	p{color:#FF0000;}
Short Hex Code	#RGB	p{color:#6A7;}
RGB %	rgb(rrr%,ggg%,bbb%)	p{color:rgb(50%,50%,50%);}
RGB Absolute	rgb(rrr,ggg,bbb)	p{color:rgb(0,0,255);}
keyword	aqua, black, etc.	p{color:teal;}

list of 216 colors which are supposed to be most safe and computer independent colors. These colors vary from hexa code 000000 to FFFFFF. These colors are safe to use because they ensure that all computers would display the colors correctly when running a 256 color palette 

Background:
The background-color property is used to set the background color of an element.
The background-image property is used to set the background image of an element.
The background-repeat property is used to control the repetition of an image in the background.
The background-position property is used to control the position of an image in the background.
The background-attachment property is used to control the scrolling of an image in the background.
The background property is used as a shorthand to specify a number of other background properties.

Shorthand Property
You can use the background property to set all the background properties at once. For example −
<p style = "background:url(/images/pattern1.gif) repeat fixed;">
   This parapgraph has fixed repeated background image.
</p>

Font:
The font-family property is used to change the face of a font.
The font-style property is used to make a font italic or oblique.
The font-variant property is used to create a small-caps effect.
The font-weight property is used to increase or decrease how bold or light a font appears.
The font-size property is used to increase or decrease the size of a font.
The font property is used as shorthand to specify a number of other font properties.

Logical Tags:
In HTML there are both logical tags and physical tags. Logical tags are designed to describe (to the browser) the enclosed text's meaning. An example of a logical tag is the <strong> </strong> tag. By placing text in between these tags you are telling the browser that the text has some greater importance. By default all browsers make the text appear bold when in between the <strong> and </strong> tags, but the point to take away from this is that the strong tag implies that importance of that text. This has impact with search engines like Google who look for such tags to help figure out what the page is about.

There are many logical tags and they include:

<strong> : Strong - as above.
<em> : emphasize - usually renders (made to look like by the browsers) as italic.
<span> : a neutral inline container. - read about this distinction below.
<div> : a neutral block element. - read about this distinction below.

Logical tags, as mentioned above, have default ways in which browsers (like IE or Opera) render them. But it is understood that CSS should be used to give them their style, or in other words their 'look'.

Physical Tags:
Physical tags on the other hand provide specific instructions on how to display the text they enclose. Examples of physical tags include:

<b> : Makes the text bold.
<big> : Makes the text usually one size bigger than what's around it.
<font> : Used to apply a font-face (like Arial or Helvetica) and font-color.
<i> : Makes text italic.

Physical tags are more straightforward; <i> makes the text italic, <b> makes text bold and <font> is used to set the font face and color for the text.
  
Block Level vs. Inline tags
What is the point of 'inline' in the description of the tag categories?

In HTML, tags are either 'inline' or block-level elements. Block-level elements exist in their own virtual 'box' and are always followed by a carriage return (like hitting the 'enter' key after typing in some text). Inline tags (elements) become a part of the 'flow' of text in which they are inserted and have no 'box' around them and don't have the carriage return either. An example of a block tag is a <p> tag (paragraph) and an example of an inline tag is the <b> (bold) tag.

Pseudo class:
The pseudo-class concept is introduced to permit selection based on information that lies outside of the document tree or that cannot be expressed using the other simple selectors.



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
