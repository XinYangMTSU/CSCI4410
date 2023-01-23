# CSCI 330 Fall 2021
# Part 2: CSS

# What is CSS?
+ CSS stands for Cascading Style Sheets. 
+ CSS defines how HTML elements are to be displayed.
+ CSS saves a lot of work. It can control the layout of multiple web pages all at once.
  - CSS contains all styling information: where HTML elements should go, what color they should be, how big they should be, and more.

![html_css_js.JPG](../Resources/html_css_js.JPG)
# CSS Syntax
+ A CSS rule set consists of a **selector** and a **declaration block**:
![](../Resources/CSS1.png)
+ The selector points to the HTML element you want to style.
+ The declaration block contains one or more declarations separated by semicolons.
  - The importance of semicolons
    + As you start adding more and more property-value pairs for each CSS selector, it’s important to remember to put a semicolon (;) at the end of each line.
    + The semicolon tells CSS that one property-value pair is over and it’s time to move on to the next one.
    + Without semicolons, it’ll become confused and your page won’t look right.
    + Also, don’t forget: all property-value pairs for a selector are surrounded by curly braces {}.
+ Each declaration includes a CSS property name and a value, separated by a colon.
+ A CSS declaration always ends with a semicolon, and declaration blocks are surrounded by curly braces.

# CSS How To ...
When a browser reads a style sheet, it will format the HTML document according to the information in the style sheet.


There are three ways of inserting a style sheet:

+ Inline style.
+ Internal style sheet. 
+ External style sheet. 

# Inline style.
+ An inline style may be used to apply **a unique style for a single element**.
+ To use inline styles, add the **style attribute** to the relevant tag.
+ The style attribute can contain any CSS property.
~~~~

<h1>This is a heading</h1>
<h1 style="color: blue;text-align: center">This is a heading with inline style</h1>

~~~~


![css2](../Resources/CSS2.png)

+ Note: An inline style loses so many of the advantages of a style sheet(by mixing content with presentation). Use this method sparingly.

# Internal Style Sheet
+ An internal style sheet may be used if one single page has a unique style.
+ Internal styles are defined within the <style> element, inside the <head> section of an HTML page.

~~~~
    <style type="text/css">
    	
    	h1{ 
        color: blue;
        text-align: center";
        }

    </style>
~~~~

![css3](../Resources/CSS3.png)



# External Style Sheet
+ With an external style sheet, you can change the look of an entire website by changing just one file!
+ Each page must include a reference to the external style sheet file inside the `<link>` element. The `<link>` element goes inside the `<head>` section:
  - in HTML:
~~~~
<head>
    <title>csci 330</title>
    
    <link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
~~~~
  - in CSS:
  ~~~~
  h1{
    color: blue;
    text-align: center;
  }
  ~~~~

	
![css4](../Resources/CSS4.png)

+ Make sure HTML file can see the external CSS information by putting a `<link>` tag between the `<head>`...`</head>` tags of the HTML page. Your `<link>` tag needs three attributes:
  - A **type** attribute that should be always be equal to “text/css”.
  - A **rel** attribute that should be always be equal to “stylesheet”. It is used to define the relationship between the linked file and the HTML document.
  - A **href** attribute that should point to the web address of your CSS file.


+ Note that:
  - An external style sheet can be written in any text editor.
  - The file should not contain any html tags.
  - The style sheet file must be saved with a **.css** extension.
# Cascading Order
+ What style will be used when there is more than one style specified for an HTML element?
+ Generally speaking we can say that all the styles will ”cascade” into a new ”virtual” style sheet by the following rules, where number 1 has the highest priority:
<ol>
  <li>Inline style (inside an HTML element).</li>
  <li> External and internal style sheets (in the head section)</li>
  <li> Browser default</li>
  </ol>
  
![css5](../Resources/CSS5.png)
![css6](../Resources/CSS6.png)
+ An inline style (inside a specific HTML element) has the highest priority, which means that it will override a style defined inside the <head> tag, or in an external style sheet, or a browser default value.
+ The priority of internal and external style is determined by their order in `<head></head>` tag. The later one will overwrite the earlier one.
  
# CSS color
+ Colors in CSS are most often specified by:
  - a valid color name - like `red`.
  - an RGB value - like `rgb(255, 0, 0)`. 
  - a HEX value - like `#ff0000`.
+ **color name**
  - HTML/CSS suport [140](https://www.w3schools.com/colors/colors_hex.asp) standard color names.
  ![color name example](../Resources/CSS-colorname.png)
+ **RGB**: 
  - [RGB color values](https://www.w3schools.com/colors/colors_rgb.asp) can be specified using this formula: rgb(red, green, blue).
  ![color rgb example](../Resources/CSS-colorrgb.png)
+ **Hexadecimal Colors**:
  - RGB values can also be specified using [hexadecimal color values](https://www.w3schools.com/colors/colors_hexadecimal.asp) in the form: #RRGGBB, where RR (red), GG (green) and BB (blue) are hexadecimal values between 00 and FF (same as decimal 0-255):
  ![color hex example](../Resources/CSS-colorhex.png)
  
+ ![color example](../Resources/CSS-colorexample.png)

# Text alignment
+ The text-align property is used to set the horizontal alignment of a text.
+ A text can be left or right aligned, centered, or justified.
+ The following example shows center aligned, and left and right aligned text:
  - ![text align](../Resources/CSS-textalign.png)
	
+ Bullet points/markers of a list alignment
	- Add `list-style-position: inside` to the `list` element. 
	- The default value for the `list-style-position` property is `outside`.
~~~~
ul {
    text-align: center;
    list-style-position: inside;
}	
~~~~
	
~~~~
<ul>
    <li>one</li>
    <li>two</li>
    <li>three</li>
</ul>
~~~~
# Font size
+ The font-size property sets the size of the text.
![](../Resources/CSS-fontsize.png)
# Font family
+ The font-family property sets the font family of the text.
+ Most computers will understand popular fonts like Verdana, Courier, and Garamond, but each individual computer has different fonts installed on it.
+ CSS has some built-in defaults meant to ensure your users see what you intend. They are:
  - serif: A font with little decorative bits on the ends of the strokes that make up letters. Do a search on ”serif” to see what we mean.
  - sans-serif: A plain-looking font, like this one. It doesn’t have the little doohickies on the ends of letters like a serif font does.
  - cursive:A scripty font! It looks like cursive writing.
  - See details [here](https://www.w3schools.com/css/css_font.asp)
+ font-family backup values
  - You don’t have to jump straight to a default value like cursive or sans-serif: you can tell CSS to try several, going from one to the next if the one you want isn’t available.
  - For example, if you write:
    ~~~~
    p{ font-family: Tahoma, Verdana, sans-serif; }
    ~~~~
  - CSS will first try to apply Tahoma to your paragraphs. If the user’s computer doesn’t have that font, it will try Verdana next, and if that doesn’t work, it will show a default sans-serif font.
![](../Resources/CSS-fontfamily.png)
# CSS Background
+ The CSS background properties are used to define the background effects for elements.
+ CSS background properties:
  - background-color
    + The background-color property specifies the background color of an element.
    ~~~~
    body{
	    background-color: lightblue;
    }
    h1{
	    background-color: red;
    }
    h2
    {
	    background-color: green;
    }
    h3
    {
	    background-color: blue;
    }
    ~~~~

    ![](../Resources/CSS-backgroundcolor.png)
  
  
  - background-image
    + The background-image property specifies an image to use as the background of an element.
    + By default, the image is repeated so it covers the entire element.
    ~~~~
    body{
	    background-image: url("sau.png");
    }
    ~~~~

    ![](../Resources/CSS-backgroundimage.png)
    + Note that: Do not use a background image that disturbs the text.
  - background-repeat
    + By default, the background-image property repeats an image both horizontally and vertically.
    + To repeat an image horizontally, set background-repeat: repeat-x
    ![](../Resources/CSS-repeatx.png)
    + To repeat an image vertically, set background-repeat: repeat-y
    ![](../Resources/CSS-repeaty.png)
    + No repeat, set background-repeat: no-repeat:
    ![](../Resources/CSS-norepeat.png)
  
  - background-position
    + The position of the image is specified by the background-position property.
    ~~~~
    body{
	background-image: url("sau.png");
	background-repeat: no-repeat;
	background-position: top right;
	}
    ~~~~
    
    ![](../Resources/CSS-backgroundposition)
    
    + When you use the `bottom` position, make sure you have enough elements in the `body`.
    
    + You can also specify the position by px. 
    ~~~~
    body{
	background-image: url("sau.png");
	background-repeat: no-repeat;
	background-position: bottom 7px right 5px;
	}
    ~~~~
    
  - background-attachment
   + To specify that the background image should be fixed (will not scroll with the rest of the page), use `background-attachment: fixed`.
   + To Specify that the background image should scroll with the rest of the page, use `background-attachment: scroll`.
# Comment
+ Comments are used to explain the code, and may help when you edit the source code at a later date.
+ Comments are ignored by browsers.
+ A CSS comment starts with `/*` and ends with `*/`. Comments can also span multiple lines:
  
# HTML block
+ A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).
+ One of the most versatile structure tags available to you is the `<div> </div>` tag. Short for “division”.
+ `<div>` allows you to divide your page into containers (that is, different pieces). This will come in handy when you begin learning CSS. CSS Division (div) is a container element and it is used to group related items together. Whenever there is a situation that you need to collect various objects into a larger container for scripting or styling purposes, div is the best solution. The use of < div > tag is straightforward.
+ Syntax
~~~~
<div>...</div>
~~~~
+ Examples
~~~~
<div>
  <p>A paragraph inside Div</p>
</div>
~~~~

~~~~
    <div style="width: 50px; height: 50px; background-color: red"></div>
    <div style="width: 50px; height: 50px; background-color: green"></div>
    <div style="width: 50px; height: 50px; background-color: blue"></div>
    <div style="width: 50px; height: 50px; background-color: yellow"></div>
~~~~

![](../Resources/CSS-div.png)

+ As you can probably guess, the smart use of `<div>` will eventually allow you to create visual HTML objects like sidebars, menus, and more. [example](https://www.w3schools.com/howto/howto_css_fixed_sidebar.asp)
+ You can make `<div>` clickable by wrapping them in `<a></a>` tags.

~~~~
<a href="www.google.com"><div style="width: 50px; height: 50px; background-color: yellow"></div></a>
~~~~

+ The code above is not working, why? Do not forget the `https://` for the url.

# Spantastic

+ While <div> allows you to divide your webpage up into pieces you can style individually, `<span>` allows you to control styling for smaller parts of your page, such as text.
+ For example, if you always want the first word of your paragraphs to be red, you can wrap each first word in `<span></span>` tags and make them red using CSS!
~~~~
	<p>This paragraph is black, except for the word <span style="color:red">red</span>!</p>
~~~~
![](../Resources/CSS-span.png)

+ Color is just one attribute you can selectively change with <span> tags; you can also change font size, font family, and any other style attribute you can think of!
	
# CSS selectors
+ CSS selectors are used to **find/select** HTML elements based on their element name, id, class, attribute, and more.
## name selector 
+ The name selector selects elements based on the element name.
+ This is what we leart in the previous lecture.
~~~~
p{
	color: red;
}
~~~~
## id selector
+ The id selector uses the id attribute of an HTML element to select a specific element.
+ The id of an element should be unique within a page, so the id selector is used to select one unique element.
+ To select an element with a specific id, write a `hash (#)` character, followed by the id of the element.
+ Note that: an id can not start with a number!
![](../Resources/CSS-idselector.png)
**Q:** what if I add a name selector?
~~~~
p {
	color: blue;
}
#para1 {
	color: red;
}
~~~~
or
~~~~
#para1 {
	color: red;
}
p {
	color: blue;
}


~~~~
## class Selector
+ The class selector selects elements with a specific class attribute.
+ To select elements with a specific class, write a period (.) character, followed by the name of the class.
+ In the example below, all HTML elements with class=”red” will be red:
~~~~
.red{
	color: red;
}
~~~~
![](../Resources/CSS-classselector.png)

# grouping selector
+ If you have elements with the same style definitions, like this:
~~~~
h1 {
	color:red;
}
p {
	color:red;
}
~~~~
+ It will be better to group the selectors, to minimize the code.
+ To group selectors, separate each selector with a comma.
~~~~
h1,p {
	color:red;
}
~~~~

## multiple selector
+ It is possible to nest HTML elements inside one another
~~~~
<div>
        <div>
            <p>This is a paragraph in nested divisions.</p>
        </div>
    </div>
~~~~
+ what if you want to grab `<p>` that are inside two` <div>`, and not all `<p>` ?
~~~~
div div p {
	color:red;
}
~~~~
![](../Resources/CSS-multipleselector.png)
# Parents, children, siblings
+  If you think of the `<html>` tag as the trunk of the tree, you can think of its immediate branches `<head>` and `<body>` as its children.
+ Both tags are children of `<html>`, and `<html>` is their parent element. Because they are both immediate children of `<html>` (that is, they are both only one element away), they are siblings.
+ 
## first child selector
+ It’s used to apply styling to only the elements that are the first children of their parents.
~~~~
p:first-child{
	color: red;
}
~~~~

![](../Resources/CSS-firstchild.png)
## nth child selector
+ You can actually select any child of an element after the first child with the selector nth-child; you just add the child’s number in parentheses after the pseudo-class selector. For example,

~~~~
p:nth-child(2){
	color: red;
}
~~~~
would turn every paragraph that is the second child of its parent element red.



# Box Model
+ All HTML elements can be considered as boxes. 
+ In CSS, the term "box model" is used when talking about design and layout.
+ The CSS box model is essentially a box that wraps around every HTML element.
+ It consists of: margins, borders, padding, and the actual content. The image below illustrates the box model:

	- Content: The content of the box, where text and images appear
	- Padding: Clears an area around the content. The padding is transparent
	- Border: A border that goes around the padding and content
	- Margin: Clears an area outside the border. The margin is transparent
	-![CSS-boxmodel.pn](../Resources/CSS-boxmodel.png)
+ example:
~~~~
div {
  width: 320px;
  padding: 50px;
  border: 15px solid red;
  margin: 20px;
}
~~~~
![CSS-boxexample.png](../Resources/CSS-boxexample.png)

# Display property
+ by default
~~~~
div{
	border: 1px dashed blue;
	margin: 2px;
	width: 400px;
	height: 50px;
}
~~~~
![CSS-displayblock.pn](../Resources/CSS-displayblock.png)
+ As you saw, the outermost box of each element went all the way across the page. This is why until now, your HTML elements have been sitting on top of one another: by default, they take up the full width of the page.
+ We can change all this with the first positioning property we’ll learn: the display property. We’ll learn about four possible values.
+ Four possible values for display property
	- block: This makes the element a block box. It won’t let anything sit next to it on the page! It takes up the full width.
  	- inline-block: This makes the element a block box, but will allow other elements to sit next to it on the same line.
  	- inline: This makes the element sit on the same line as another element, but without formatting it like a block. It only takes up as much width as it needs (not the whole line).
  	- none: This makes the element and its content disappear from the page entirely!

~~~~

div{
	border: 1px dashed blue;
	margin: 2px;
	width: 400px;
	height: 50px;
	display: inline-block;
}
~~~~
+ If we specify a display of inline-block, however, our blocks are still blocks, but will be able to sit next to each other on the same line.

![CSS-displayinlineblock.png](../Resources/CSS-displayinlineblock.png)

+ The **inline** value places all your elements next to one another, but not as blocks: they don’t keep their dimensions. The good news is, inline places all your elements on a single line. The bad news is that it doesn’t maintain their “box”ness: as you saw, all your `<div>` got squished to the smallest possible width!

![displayinline](../Resources/CSS-displayinline.png)

+ **display: none** removes the selected element from the page entirely, including any children and any content. (But not gone forever?changing the display value away from none will bring everything back.)

![displaynone](../Resources/CSS-displaynone.png)

# Margin
+ -![boxmodel](../Resources/CSS-boxmodel.png)
+ The margin is the space around the element. The larger the margin, the more space between our element and the elements around it.
+ We can adjust the margin to move our HTML elements closer to or farther from each other.
+ If set margin to auto, this tells the document to automatically put equal left and right margins on our element, centering it on the page.

~~~~
<!-- in html -->
<h2>Use of margin:auto</h2>
<p>You can set the margin property to auto to horizontally center the element within its container. The element will then take up the specified width, and the remaining space will be split equally between the left and right margins:</p>

<div>
This div will be horizontally centered because it has margin: auto;
</div>
~~~~
	
~~~~
/* in css */
div {
  width:300px;
  margin: auto;
  border: 1px solid red;
}
~~~~
	
![marginauto](../Resources/CSS-marginauto.png)
	
+ If you want to specify a particular margin

~~~~
margin-top: 20px; 
margin-right: 30px; 
margin-bottom: 40px; 
margin-left: 50px;
~~~~

or

~~~~
margin: 20px,30px,40px,50px;
~~~~

![](../Resources/CSS-margin4.png)

# Border
+ -![](../Resources/CSS-boxmodel.png)
+ The border is the edge of the element. It’s what we’ve been making visible every time we set the border property.

~~~~
border-width: 2px;
border-style: dotted;
border-color: red;
~~~~

or 

~~~~~

border: 2px dotted red;

~~~~~

![](../Resources/CSS-border.png)

+ You can set the properties for each side of the border. See tutorial in details [here](https://www.w3schools.com/css/css_border.asp)


# Padding
+ -![](../Resources/CSS-boxmodel.png)
+ The padding is the spacing between your innermost layer: the actual content and the border. We can adjust this value with CSS to move the border closer to or farther from the content.
+ The content is the actual “stuff” in the box. If we’re talking about a <p> element, the “stuff” is the text of the paragraph.
+ Padding can be set in two ways, just like your margins. You can either select them individually, like this:
	~~~~
	padding-top: 10px;
	padding-right: 20px;
	padding-bottom: 30px; 
	padding-left: 40px;
	~~~~
	or
	~~~~
	padding: 10px 20px 30px 40px;
	~~~~
+ if you want your padding to be the same for all four sides, you can declare that value only once. `padding: 10px` will give your HTML element 10 pixels of padding on all sides.
	
![](../Resources/CSS-padding.png)
	
# TM,TB,TP
+ You’ll see abbreviations like TM, TB, and TP in the diagram. These stand for “top margin”, “top border,” and “top padding”.
+ As we’ll see, we can adjust the top, right, left, and bottom padding, border, and margin individually.

![](../Resources/CSS-TMTB.png)
	
# Negative Values
+ If you want to move an element in the other direction, you can give CSS a negative value: margin-left: -40px will move the element fourty pixels to the left.
~~~~
margin-left: -40px;
~~~~
![](../Resources/CSS-negative.png)

# Q: How to calculate the width and height of a box model?
+ Hint: in CSS file, `width` and `height` define the width and height of the `content`.
~~~~
div {
	width: 320px;
  	height: 150px;
	padding: 50px;
	border: 15px solid green;
	margin: 20px;
}
~~~~
	
# Float
+ The float property specifies whether or not an element should float.
+ In its simplest use, the float property can be used to wrap text around images.

+ The float property can have one of the following values:
	- left: The element floats to the left of its container
	- right: The element floats to the right of its container
	- none: The element does not float (will be displayed just where it occurs in the text). This is default
	- inherit: The element inherits the float value of its parent
	
![](../Resources/CSS-floatdefaulty.png)

![](../Resources/CSS-floatright.png)

# Clear
+ The clear property is used to control the behavior of floating elements.
+ Elements after a floating element will flow around it. To avoid this, use the clear property.
+ The clear property specifies on which sides of an element floating elements are not allowed to float:
+ The clear property can have one of the following values:

	- none - Allows floating elements on both sides. This is default
	- left - No floating elements allowed on the left side
	- right- No floating elements allowed on the right side
	- both - No floating elements allowed on either the left or the right side
	- inherit - The element inherits the clear value of its parent
~~~~
img{
	float: left;
}

p{
	clear: left;
}
~~~~
![](../Resources/CSS-clear.png)

# The position Property
+ The position property specifies the type of positioning method used for an element. There are four different position values:
	- static
  	- relative   
	- fixed
  	- absolute
+ position: static
	- HTML elements are positioned static by default.
	- Static positioned elements are not affected by the top, bottom, left, and right properties.
	- An element with position: static; is not positioned in any special way; it is always positioned according to the normal flow of the page.
+ position: relative
	- An element with position: relative; is positioned relative to its normal position.
	- Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position.
+ position: fixed
	- An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled.
	- The top, right, bottom, and left properties are used to position the element.
+ position: absolute
	- An element with position: absolute; is positioned relative to the nearest positioned ancestor.
	- However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.
	
	[See examples here.](https://www.w3schools.com/css/css_positioning.asp)
	


# Navigation bar
+ Having easy-to-use navigation is important for any web site.

+ With CSS you can transform boring HTML menus into good-looking navigation bars.

+ Navigation Bar = List of Links

+ default
~~~~
    <ul>
        <li><a href="https://zhangningsau.github.io/">Home</a></li>
        <li><a href="https://zhangningsau.github.io/CSCI195/Fall2019/index.html">CSCI 195</a></li>
        <li><a href="https://zhangningsau.github.io/CSCI330/Fall2019/index.html">CSCI 330</a></li>    
    </ul>
~~~~
![](../Resources/CSS-defaultbar.png)
+ remove the bullets and the margins and padding from the list

~~~~
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
~~~~

+ Vertical Navigation Bar: To build a vertical navigation bar, you can style the <a> elements inside the list
	- Displaying the links as block elements makes the whole link area clickable (not just the text)
~~~~
li a {
  display: block;
  width: 60px;
}	
~~~~
	- problem exists when the width is too small.
![](../Resources/CSS-verticalbarproblem.png)
![](../Resources/CSS-verticalbar.png)
+ Horizontal Navigation Bar
~~~~
li  {
  display: inline;
  width: 60px;
}
~~~~
![](../Resources/CSS-horizontalbar.png)
+ Fixed Navigation Bar: Make the navigation bar stay at the top or the bottom of the page, even when the user scrolls the page.
~~~~
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;


  position: fixed;
  top: 0;
  width: 100%;
}
~~~~

+ See more examples on [w3schools.com/css](https://www.w3schools.com/css/css_navbar.asp)


[Homework 2](https://github.com/ZhangNingSAU/Fall-2021-CSCI-330-Web-Programming/blob/master/Homework/HW2.md)



[Reference: w3schools](https://www.w3schools.com/css/default.asp)
