# HTML BASICS


## HTML Boiler Plate Code
HTML code required to begin creating a web page

```markup
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>

</body>
</html>
```
## Heading Elements
list of heading elements available in HTML. They are ordered from largest to smallest in size.

```markup
 <h1>
 <h2>
 <h3>
 <h4>
 <h5>
 <h6>
```
Often times, headings are meant to emphasize or enlarge only a few words.
If you want to add content in paragraph format, you can add a paragraph using the paragraph element<p>


## Lists
Unordered list - Unordered list for text you decide to format in bullet points

```markup
<ul>
  <li>Limes</li>
  <li>Tortillas</li>
  <li>Chicken</li>
</ul>
```
Ordered list - Ordered lists are like unordered lists, except that each list item is numbered

```markup
<ol>
  <li>Preheat the oven to 350 degrees.</li>
  <li>Mix whole wheat flour, baking soda, and salt.</li>
  <li>Cream the butter, sugar in separate bowl.</li>
  <li>Add eggs and vanilla extract to bowl.</li>
</ol>
```
## Anchor
You can add links to a web page by adding an anchor element <a> and including the text of the link in between the opening and closing tags.

```markup
Incomplete: <a>This Is A Link To Wikipedia</a>
```
The anchor element in the example above is incomplete without the **href** attribute.
Attributes are made up of the following two parts:
1. The name of the attribute.
1. The value of the attribute.
For anchor elements, the name of the attribute is href and its value must be set to the URL of the page you'd like the user to visit.

```markup
<a href="https://www.wikipedia.org/">This Is A Link To Wikipedia</a>
<a> </a> -- Anchor element
<a>This is an anchor element</a> -- Without link
<a href="http://www.google.com/">This is an anchor element</a> -- With link
<a href="https://en.wikipedia.org/wiki/Brown_bear" target="_blank">The Brown Bear</a>
```
In the example above, the link would read The Brown Bear and open up the relevant Wikipedia page in a new window.


## Image
The <img> element lets you add images to a web page. This element is special because it does not have a closing tag, it only has an opening tag. This is because the <img> element is a self-closing element.

```markup
<img src="https://www.example.com/picture.jpg" />
```
Note that the <img> element has a required attribute called src, which is similar to the hrefattribute in links. In this case, the value of srcmust be the URL of the image. Also note that the end of the <img> element has a forward slash /. This is required for a self-closing element.


So far, we've added links that were made up of only text, like the following:

```markup
<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank">Prickly Pear</a>

<a href="https://en.wikipedia.org/wiki/Opuntia" target="_blank"><img src="#" alt="A red prickly pear fruit"/></a>
```
## Line Break
If you are interested in modifying the spacing in the browser, you can use HTML's line break element: 

```markup
<br/>
```
The line break element is one self-closing tag. You can use it anywhere within your HTML code and a line break will be shown in the browser.

```markup
Shall I compare thee to a summer's day?<br/>Thou art more lovely & more temperate
```


HTML files also allow you to add comments to your code.

```markup
Comments begin with <!-- and end with -->. Any characters in between will be treated as a comment.
```


