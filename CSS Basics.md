# CSS Basics


## CSS Setup

```markup
<link href="style.css" type="text/css" rel="stylesheet">
```
The HTML file must know exactly where the CSS code is kept, otherwise, the styling can't be applied the web page. In order to apply the styling to the web page, we'll have to link the HTML file and the CSS file together.


When linking an HTML file and a CSS file together, the <link> element will look like the following:

```markup
<link href="https://www.codecademy.com/stylesheets/style.css" type="text/css" rel="stylesheet">
```
If the CSS file is stored in the same directory as your HTML file, then you can specify a relative path instead of a URL, like so:

```markup
<link href="/style.css" type="text/css" rel="stylesheet">
```


## Basic CSS Structure & Syntax
To style an HTML element using CSS, you must first select that element in the CSS file. For example, to style a <p> element, the syntax to select it using CSS is:

```css
p { }
```
1. Property - the property you'd like to style of that element (i.e., size, color, etc.).
1. Value - the value of the property (i.e., 18pxfor size, Blue for color, etc.).

```css
h1 { color: Blue; }
```
Fortunately, you can select multiple elements at once so that you can save time styling a shared property.

```css
h1, h2, p { color: Green; }
```
In the example above, the <h1> heading, the <h2> heading, and the paragraph have all been styled to appear Green using a multiple element selector. A multiple element selector can save you time when you want to style the same property across many elements.
here's a special selector that can instantly select every single element on the web page: the universal selector.

```css
* { font-family: Arial; }
```
In the example above, the universal selector, *, is used to select every element on the page and set the font to Arial. Just like HTML, you can also leave comments in your CSS file. CSS comments begin with /* and end with */, like so:

```css
/* This is a comment in CSS! */
```
In CSS, these two design aspects can be styled with the following two properties:

1. Color - this property styles an element's foreground color.
1.  Background-color - this property styles an element's background color.

```css
h1 { color: Red; background-color: Blue; }
```
To use RGB colors, you can use the rgb() value when styling a color.

```css
h1 {
  color: rgb(123, 20, 233);
  background-color: rgb(99, 21, 127);
}
```
When specifying an RGB color mixture, the values are in base 10. Hex color codes, however, use base 16, or hexadecimal base (hence the name), to specify color mixtures.

```css
h1 { color: #09AA34; }
```
You can use HSL colors in your CSS like this:

```css
h1 { color: hsl(182, 20%, 50%); }
```
Notice that using HSL is very similar to using RGB.
The extra a character in the rgba() value is known as the alpha value. It represents the opacity of a color. The alpha value can be a number between 0 or 1, inclusive.

```css
h1 { color: rgba(123, 88, 9, 0.5); }
```
To change the typeface of text on your web page, you can use the font-familyproperty.

```css
h1 { font-family: Garamond; }
```
In the example above, the font family for all main heading elements has been set to Garamond.
The default typeface for all HTML elements is Times New Roman

When the name of a typeface consists of more than one word, it must be enclosed in double quotes (otherwise it will not be recognized), like so:

```css
h1 { font-family: "Courier New"; }
```
Google offers [Google Fonts](http://fonts.google.com), a directory of thousands of open-source fonts that are free to use by anyone.
To use a Google Font, you can use a <link> element, just like you did for a CSS stylesheet:

```css
<head> <link href="https://fonts.googleapis.com/css?family=Raleway" type="text/css" rel="stylesheet" > </head>
```
In the example above, the href attribute is set to the following URL, which was retrieved from Google Fonts:

```css
https://fonts.googleapis.com/css?family=Raleway
```
The URL in the example above specifies the Raleway typeface from Google Fonts.


To move, or align, text, we can use the text-align property.

```css
h1 { text-align: right; }
```
The text-align property can be set to one of the following three values:
1. left - aligns text to the left hand side of the browser.
1. center - centers text.
1. right - aligns text to the right hand side of the browser.


## Box Model
To modify the default dimensions an element's box in CSS, you can use the width and height properties.
These two properties can be specified with the following units of measurement:
**Pixels** - You learned about pixels when you learned about fonts. This unit lets you set the exact size of an element's box.
**Ems** - This unit sets the dimensions of the box relative to the size of the text within the box.
**Percentages** - This unit sets the dimensions of the box relative to the size of the box that it is encased in. For example, consider an element (a box) of class blue set to a height of 200 pixels and a width of 200 pixels. Inside of blue, consider another box of class red, set to a height of 37% and a width of 45%. The resulting dimensions of the red box would be a height of 74 pixels and a width of 90 pixels.

Developers often use ems or percentages to set box dimensions. Because many web pages are now accessed on mobile devices and other displays of differing sizes, ems and percentages allow boxes to scale depending on the size of a user's display.


Because a web page can be viewed through displays of differing screen size, the content on the web page can suffer from those changes in size. To avoid this problem, CSS offers two properties that can limit how narrow or how wide an element's box can be sized to.
**min-width** - this property ensures a minimum width for an element's box.
**max-width** - this property ensures a maximum width for an element's box.

```css
p { min-width: 300px; max-width: 600px; }
```
In the example above, the width of all paragraphs will not shrink below 300 pixels, nor will the width exceed 600 pixels.
Content, like text, can become difficult to read when a browser window is narrowed or expanded. These two properties ensure that content is legible by limiting the minimum and maximum widths of an element.

You can also limit the minimum and maximum height of an element.
**min-height** - this property ensures a minimum height for an element's box.
**max-height** - this property ensures a maximum height for an element's box.

```css
p { min-height: 150px; max-height: 300px; }
```
In the example above, the height of all paragraphs will not shrink below 150 pixels and the height will not exceed 300 pixels.
What will happen to the contents of an element's box if the max-height property is set too low? It's possible for the content to spill outside of the box, resulting in content that is not legible. You'll learn how to work around this issue in the next exercise.

When the value of the max-height property is set too low, the contents will spill outside of the box. How can we ensure that this doesn't happen?
The overflow property controls what happens to content when it spills, or overflows, outside of its box. It can be set to one of the following values:
**hidden** - when set to this value, any content that overflows be hidden from view.
**scroll** - when set to this value, a scrollbar will be added to the element's box so that the rest of the content can be viewed by scrolling.

```css
p { min-width: 300px; max-width: 600px; min-height: 150px; max-height: 300px; overflow: scroll; }
```


## Borders
 It's not possible to view a box's border if the border's style has not been set. A border's style can be set with the border-style property. This property can take on one of the following values:

* solid - border is a solid line.
* dashed - border is a series of lines or dashes.
* dotted - border is a series of square dots.
* double - border is two solid black lines.
* groove - border is a groove (or carving).
* inset - border appears to cut into the screen.
* outset - border appears to pop out of the screen.
* ridge - border appears as a picture frame.
* hidden or none - no border.

```css
div { border-style: solid; }
```
In the example above, a solid black line will appear around all divs on the page.

You can control the thickness, or width, of borders with the border-widthproperty. The value of border-width is given in pixels.

```css
p { border-style: solid; border-width: 5px; }
```
In the example above, the solid borders of all paragraphs on the page would be set to a thickness of 5 pixels.
It's also possible to also set the border-width property to one of the following named thicknesses:
- thin
- medium
- thick

While these values are perfectly valid, you may not see them often, but it's good to know that they exist.

What if you don't want the border thickness to be the same on all four sides?
In that case, another version of the border-width property allows you to specify the width for each side of the border.

```css
p { border-style: solid; border-width: 3px 1px 2px 1px; }
```
The values in the example above refer to the border width in clockwise order (top: 3 pixels, right: 1 pixel, bottom: 2 pixels, left: 1 pixel).
If you'd like to be even more specific about the width of different sides of the border, you can use the following properties:
- border-top-width
- border-right-width
- border-bottom-width
- border-left-width
Each property affects the width of only one side of the border, giving you more flexibility in customization.

```css
p { border-style: solid; border-left-width: 4px; }
```
In the example above, only the left side of the border will be set to a width of 4 pixels.
The color of a border can also be customized with the border-color property.

```css
div.container { border-style: solid; border-width: 3px; border-color: rgb(22, 77, 100); }
```
The border-color property accepts colors in the various formats you learned about earlier: named colors, RGB(a) colors, and hex colors. It's common to use hex colors for borders, but you'll likely also come across RGB(a) colors as well.

The shorthand way of setting border style, width, and color can be achieved with the border property. Let's look at how we can decrease the amount of code bloat with this property.

```css
div.container { border-style: solid; border-width: 3px; border-color: rgb(22, 77, 100); }
```
The code in the example above can be shortened using the border property:

```css
div.container { border: 3px solid rgb(22, 77, 100); }
```
Note that the border property includes all of the properties that we previously styled individually: width, style, and color.
It's considered best practice to follow the width-style-color order when using the border property.

Ever since we revealed the borders of boxes, you may have noticed that the borders highlight the true shape of an element's box: square. Thanks to CSS, a border doesn't have to be square.
The corners of an element's border box can be modified with the border-radius property.

```css
div.container { border: 3px solid rgb(22, 77, 100); border-radius: 5px; }
```
The code in the example above will set all four corners of the border to a radius of 5 pixels (i.e. the same curvature that a circle with radius 5 pixels would have).
You can create a border that is a perfect circle by setting the radius equal to the height of the box, or to 100%.

```css
div.container { height: 60px; width: 60px; border: 3px solid rgb(22, 77, 100);border-radius: 100%; }
```




