##### CSS
* Selectors & Properties
* Advanced Selectors
* Colors & Formatting
* Fonts & Text Manipulation
* Layout Positioning
* Flexbox & Grid
* Animations & Transitions

CSS Advantages:
* Saves Time -> write once and reuse
* Pages load faster -> write rule for a tag, it will be applicable across
* Easy maintenance -> Making global changes easy
* Multiple device compatibility-> supports multi device

Selectors:
selector: HTML tag
Property: attribute of HTML tag
value: values are assigned to properties
selector {property: value }
Ex: table { border : 1px solid #C00; }

Element or Type selectors: 
p {
  color: red; 
}

Universal Selector: matches the name of any element type -
* {
  color: #000000;
}

Descendant Selectors: Apply styles to particular element only, when it lies inside a particular element.
Ex: ul em {
  color: #000000;
}
As above rule, style rule will apply to all <em> element only when it lies inside <ul> tag.

Class selectors: based on class attribute of the elements.
.black {
  color: #000000;
}
Above rule set to black for every element with class attribute set to.

h1.black {
  color: #000000;
}
Above rule set to black only for h1 elements having class attribute as black.

Id Selectors: Define rules based on id attribue of elements.
```
#black {
  color: #000000;
}
```
Above rule renders the content in black for every element with id attribute as black.

`h1#black {
  color: #000000;
}`
Above rule renders the content in black for only <h1> elements

`#black h2 {
  color: #000000;
}`
Above rule, all the level 2 headeings will be displayed in black color when those headings will lie with in tags 
having id attribute set to black.

Child Selectors: Similar to descendant selectors but different functionality.
`body > p {
  color: #000000;
}`
Above rule renders all the paragraphs in black if they are direct child of <body> element. Other paragraphs put inside the other 
elements 

Attribute Selectors: The style rule below will match all the input elements having a type attribute with a value of text −
`input[type = "text"] {
   color: #000000; 
}`
The advantage to this method is that the <input type = "submit" /> element is unaffected,
More attribute selectors ->
p[lang] − Selects all paragraph elements with a lang attribute.
p[lang="fr"] − Selects all paragraph elements whose lang attribute has a value of exactly "fr".
p[lang~="fr"] − Selects all paragraph elements whose lang attribute contains the word "fr".
p[lang|="en"] − Selects all paragraph elements whose lang attribute contains values that are exactly "en", or begin with "en-".

Specificity:
Element selectors are less powerful than class selectors.
Class selectors are less powerful than id selectors.
inline styles are powerful than id selectors.

Universal selectors(*) < Element selectors < class selectors < id selectors < inline styles

Psuedo Selectors:
h1:hover { 
  color: red;
}

li:first-child {
  color: steerblue;
}
li:last-child {
 color: blue;
}
li:nth-child(2) {
  color: green;
}
li:only-child {
  color: purple;
}

`<a href="http://www.google.com" id="google-link">Google</a>
#google-link:link {
  color: blue;
}
#google-link:visited {
  color: red;
}`

Sibling Selectors:  a tilde character (~) and then the selector you wish to target, you can target elements by requiring the
presence of another element within the same parent element. 
~ -> with in the same parent
<style type="text/css">
h2 ~ p {
	font-style: italic;
}
</style>

<div id="content">
	<h1>Hello, world!</h1>
	<p>Some text here</p>
	<h2>Hello, world!</h2>
	<p>Some text here</p>
	<p>More text here</p>
  <div>
		<p>More text here</p> // it will not impact with the above selector, since this p is not direct sibling
	</div>
</div>

Adjacent selectors: using the Adjacent sibling selector, you can limit this to only include the first element which comes
directly after the first element in themarkup.

