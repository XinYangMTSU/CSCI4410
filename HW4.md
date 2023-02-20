# CSCI 330 Fall 2021
# Homework 4 for jQuery

# due: 11:59 pm Friday 10/22/2021

# Your boss wants you to make a meme generator. Enter an image URL, and captions to go on the top and bottom. Please finish all steps by following instructions.
## 1 Create your HTML file. (15 points)
Please create your HTML file, name it as **meme.html**. Please remember the extension should be .html. And then add the following parts to your HTML file.
### 1.1 Create a basic structure HTML
+ Declaration line.
+ `<html></html>`
+ `<head></head>`
+ `<title></title>`
+ `<body></body>`

### 1.2 Create a `<div id=“meme1”></div>` section
In the `<div id="meme1">` section, there are two elements:
+ A `<h1 id="top-caption"></h1>` to display top caption.
+ A `<h1 id="bottom-caption"></h1>` to display bottom caption.

### 1.3 Create a `<div id=“meme2”></div>` section
In the `<div id="meme2">` section, there are three `<input>` elements:

+ When text is entered into the `<input id= "top-text">`. The text of `<h1 id="top-caption"></h1>` updates.
+ When text is entered into the `<input id= "bottom-text">`. The text of `<h1 id="bottom- caption"></h1>` updates.
+ When text is entered into the `<input id= "image-url">`. The src of `<img id="img1">` updates.

+ Please add a text label above or in front of each input element to indicate what is it. (top text, bottom text,image URL)

### 1.4 Create a `<div id=“meme3”></div>` section
In the `<div id="meme3">` section, there are one elements:
+ A `<img id="img1">` element to display the image

~~~~
<div id="meme3" style=" height:100px; width:100px; position:absolute">
	<img id="img1" src="sau.jpg" style="height: 100px; width: 100px">
</div>
~~~~

### 1.5 You can add a heading title at the top of your page, eg: “Welcome to my meme Generator!”
### 1.6 The above sections are required, besides these, you can add additional sections for your webpage based on your design.

## 2. Create your jQuery file.
Please create your jQuery file, name it as **meme.js**. Please remember the extension should be .js. And then add the following parts to your jQuery file.

### 2.1 Create a `$(document).ready(function(){})`
~~~~
$(document).ready(function(){
});
~~~~

### 2.2 Create a keyup event handler for `#top-text <input>` element inside the function of `$document`.
+ attach a **keyup()** event handler to the **#top-text input** so that it can respond to when a user types a key.
+ Inside the keyup event handler, get the text entered into the **#top-text input** using **.val()**.
+ Then set it as the text of `<h1 id=“top-caption”></h1>` using **.html()**.
### 2.3 Create a keyup event handler for `#bottom-text <input>` element inside the function of `$document`.
+ attach a **keyup()** event handler to the **#bottom-text input** so that it can respond to when a user types a key.
+ Inside the keyup event handler, get the text entered into the **#bottom-text input** using **.val()**.
+ Then set it as the text of `<h1 id="bottom-caption"></h1>` using `.html()`.
### 2.4 Create a keyup event handler for` #image-url <input>` element inside the function of `$document`.
+ attach a **keyup()** event handler to the **#image-url input** so that it can respond to when a user types a key.
+ Inside the keyup event handler, get the text entered into the **#image-url input** using **.val()**.
+ Then set it as the **src** attribute of the element `<img>` using **.attr()**.
**Note that: the incomplete src will yield ERR_FILE_NOT FOUND error, the image will only be displayed when you input the whole image directory. If you want to avoid this, you can choose to add one button to get the text entered into the #image-url input using .val() after the complete src has been inputed instead of keeping updating the src attribute, if you just update the src every time you input a character, it is OK.**

### 2.5 Create a keyup or keydown event handler for `$document` inside the function of `$document`.
+ attach a **keyup()** or **keydown()** event handler to `$document`.
+ Inside the keyup event handler, check if `event.which==37`(left arrow), `event.which==38`(up arrow),`event.which==39`(right arrow),`event.which==40`(down arrow), then move the div/image correspondingly.
~~~~
if (event.which==37) {
  $("div").animate({
    // add code here to move the div/image to the right by 100px (or left by -100px)
  });}
~~~~

### 2.6 Link JavaScript file to HTML file by using <script> </script>.
~~~~
<script src="meme.js"></script>
~~~~

## 3. Create your CSS file.

Please create your CSS file, name it as **meme.css**. Please remember the extension should be .css. And then add the following parts to your css file.

### 3.1 Create your own style for the webpage.
### 3.2 Link your CSS file to HTML file by using `<link>`.
~~~~
<link type="text/css" rel="stylesheet" href="meme.css" />
~~~~

## Submit your Lab4 to [blackboard](https://blackboard.sau.edu/webapps/login/)
Please zip the three files to an archive, name it as "CSCI330_Homework4_JohnDoe(01234567)" and submit the archive file to [blackboard](https://blackboard.sau.edu/webapps/login/).
