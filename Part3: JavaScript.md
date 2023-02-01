# CSCI 330 Fall 2021
# JavaScript

# Why JavaScript ?
JavaScript is one of the 3 languages all web developer must learn:   
+ HTML to define the content of the web pages.
+ CSS to specify the layout of web pages.
+ JavaScript to program the behavior of web pages.

# What can we use JavaScript for?
+ Make websites respond to user interaction.
+ Build apps and games.
+ Organize and present data.

# JavaScript Where To?
+ In HTML, JavaScript code must be inserted between `<script>` and `</script>` tags.
+ Scripts can be placed in the `<body>`, or in the `<head>` section of an HTML page, or in both.
+ External scripts are practical when the same code is used in many different web pages.
  - JavaScript files have the file extension .js.
  - To use an external script, put the name of the script file in the
    src (source) attribute of a `<script>` tag.
  - External scripts cannot contain `<script>` tags.
  - Placing scripts in external files has some advantages:
    + It separates HTML and code.
    + It makes HTML and JavaScript easier to read and maintain.
    + Cached JavaScript files can speed up page loads.
# Example
in html
~~~~
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Demo</title>
    <script type="text/javascript" src="demo.js"></script>
</head>
<body>
    <button onclick="my_function()">Try it</button>
</body>
</html>
~~~~
in js
~~~~
function my_function() {
	var name = prompt("what is your name?");
	confirm("Hello! " + name + " Welcome to CSCI 330!");
}
~~~~

# What is programming ?
+ Programming is like writing a list of instructions to the computer so it can do cool stuff with your information.
+ A computer program is a list of “instructions” to be “executed” by the computer.
+ JavaScript is a programming language.

# JavaScript Syntax
+ JavaScript syntax is the set of rules, how JavaScript programs are constructed.
+ In a programming language, these program instructions are called statements.
+ JavaScript statements are composed of: Variables, Operators, Expressions, Keywords, and Comments.
# Data Types I, II, III: Numbers & String & Boolean
+ Numbers are quantities.
+ Strings are sequences of characters.
+ A boolean is either true or false.

# JavaScript Variables
+ JavaScript variables are containers for storing data values.
+ We do this by defining a variable with a specific,
case-sensitive name.
+ Once you create (or declare) a variable as having a particular name, you can then call up that value by typing the variable name.

# JavaScript Identifiers
+ All JavaScript variables must be identified with unique names.
+ These unique names are called identifiers.
+ Identifiers can be short names (like x and y) or more descriptive names (age, sum, totalVolume).
# The general rules for constructing names for variables (unique identifiers)
+ Names can contain letters, digits, underscores, and dollar signs.
+ Names must begin with a letter.
+ Names are case sensitive (eg: y and Y are different
variables).
+ Reserved words (like JavaScript keywords) cannot be used as names.
# Declaring(Creating) JavaScript Variables
+ Creating a variable in JavaScript is called “declaring” a varialbe.
+ You declare a JavaScript variable with the **var** keyword.
+ After the declaration, the variable has no value. (Technically it has the value of undefined). To assign a value to the variable, use the equal sign.
+ example:
  ~~~~
  // syntax
  var var_name = data;
  // example
  var my_name = "Ning";
  var my_age = 33;
  var is_male = true;
  ~~~~
 
  # JavaScript Operators
  + JavaScript Arithmetic Operators are used to perform arithmetic on numbers.
  
  |operator|description|
  |----|----|
  |+|addition|
  |-|subtraction|
  |*|multiplication|
  |/|division|
  |%|module|
  |++|increment|
  |--|decrement|
  
  + JavaScript Assignment Operators assign values to JavaScript variables.
  
  |operator|example|same as|
  |----|----|----|
  |=|x = y|x=y|
  |+=|x += y|x = x + y|
  |-=|x -= y|x = x - y|
  |*=|x *= y|x = x * y|
  |/=|x /= y|x = x / y|
  |%=|x %= y|x = x % y|
  
  + JavaScript Comparison Operators and Logical Operators are used to test for true or false.
  
  |comparison operator|description|
  |----|----|
  |==|equal to|
  |===| <b>equal value and equl type</b> |
  |!=|not equal|
  |!==|<b>not equal value or not equal type</b>|
  |>|greater than|
  |<|less than|
  |>=|greater than or equal to|
  |<=|less than or equal to|
  |?|<b>ternary operator</b>|
  
  
  |logical operator|description|
  |----|----|
  |&&|logical and|
  | &#124;&#124; |logical or|
  |!|logical not|
  

  
  # JavaScript Functions
  + A JavaScript function is a block of code designed to perform a particular task.
  + You can reuse code: Define the code once, and use it many times.
  # JavaScript Functions Syntax
  + A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().
  + The parentheses may include parameter names separated by commas: (parameter1, parameter2, ...).
  + The code to be executed, by the function, is placed inside curly brackets:
  ~~~~
  function func_name(parameter1, parameter2,...){
  	//code to be executed
  }
  ~~~~
  # Function Return
  + When JavaScript reaches a return statement, the function will stop executing.
  + Functions often compute a return value. The return value is “returned” back to the “caller”.
  ~~~~
  var x = my_function(3,4);
  
  function my_function(x,y){
  	return x * y;
  }
  ~~~~
  
  + Example
  
in html
~~~~
<!DOCTYPE html>
<html>
<head>
    <title>JavaScript Demo</title>
    <script type="text/javascript" src="demo.js"></script>
</head>
<body>
    <button onclick="btnFunction()">Try it!</button>
    <p id="p1"></p>

</body>
</html>
~~~~
in js
~~~~
function myFunction(p1, p2) {
  return p1 * p2;
}

function btnFunction(){
  document.getElementById("p1").innerHTML = myFunction(4, 3);
}
~~~~
# global and local variables
+ Variables defined outside a function are accessible anywhere once they have been declared.
+ They are called global variables and their scope is global.
+ Variables defined inside a function are local variables. They cannot be accessed outside of that function.

# HTML `<button> </button>` tags and onclick Event Attribute
+ The `<button>` tag defines a clickable button.
+ The onclick attribute fires on a mouse click on the element.
~~~~
<button onclick = "my_function()">Click me</button>
~~~~
+ other [HTML events](https://www.w3schools.com/tags/ref_eventattributes.asp)
# Window prompt() Method
+ The prompt() method displays a dialog box that prompts the visitor for input.
+ A prompt box is often used if you want the user to input a value before entering a page.
+ When a prompt box pops up, the user will have to click either “OK” or “Cancel” to proceed after entering an input value.
+ The prompt() method returns the input value if the user clicks “OK”. If the user clicks “cancel” the method returns null.

# Window confirm() Method
+ The confirm() method displays a dialog box with a specified message, along with an OK and a Cancel button.
+ A confirm box is often used if you want the user to verify or accept something.
+ The confirm() method returns true if the user clicked “OK”, and false otherwise.


# JavaScript Arrays
+ JavaScript array is a special variable, which can hold more than one value at a time.
+ An array can hold many values under a single name, and you can access the values by referring to an index number.
+ In JavaScript, arrays always use numbered indexes.
~~~~
var cars=["BMW", 'Volvo', "Saab"];
~~~~
or 
~~~~
var cars= new Array("BMW", 'Volvo', "Saab");
~~~~
+ The two examples above do exactly the same.
+ For simplicity, readability and execution speed, use the first one.

# Access the Elements of an Array
+ You refer to an array element by referring to the index number.
+ This statement accesses the value of the first element in cars:
~~~~
var car_name = cars[0];
~~~~
# Array Properties and Methods
+ The length **property** of an array returns the length of an array (the number of array elements).
+ The sort() **method** sorts an array alphabetically.

~~~~
// the length property returns the number of elements
var x = car.length;
// the sort() method sorts the array.
var y = var.sort();
~~~~
+ The pop() method removes (and returns) the last element from an array:
~~~~
var cars=["BMW", 'Volvo', "Saab"];
cars.pop();
~~~~
+ The push() method adds a new element to an array (at the end):
~~~~
var cars=["BMW", 'Volvo', "Saab"];
cars.push('Honda');
~~~~


# JavaScript Objects
+ Objects are variables too. But objects can contain many values.
+ The values are written as name:value pairs (name and value separated by a colon).
+ JavaScript objects are containers for **named values**.
~~~~
var car = {type:"Fiat", model:"500", color:"white"};
~~~~

# Using the JavaScript Keyword new
~~~~
var car = new Object; // or var car = new Object();
car.type = "Fiat";
car.model = "500";
car.color = "white";
~~~~

# Objects Properties
+ The name:values pairs (in JavaScript objects) are called properties.

|property|property value|
|----|----|
|type|"Fiat"|
|model|"500"|
|color|"white"|

# Accessing Object Properties
+ You can access object properties in two ways:

~~~~
car.type;
~~~~

or 

~~~~
car["type"]
~~~~


# Object Methods
+ Methods are actions that can be performed on objects.
+ Methods are stored in properties as function definitions.


~~~~
var car = {
	type:"Fiat", 
	model:"500",
	color:"white",
	print_car_info: function(){
		return this.type + " " + this.model;
		}
	};
~~~~

or 


~~~~
var car = new Object; // or var car = new Object();
car.type = "Fiat";
car.model = "500";
car.color = "white";
car.print_car_info = function(){
		return this.type + " " + this.model;
		};
~~~~

## The keyword “this”
+ The keyword this acts as a placeholder.
+ It will refer to whichever object called that method when the method is actually used.

# Using an Object Constructor
+ The examples above are limited in many situations. They only create a single object.
+ Sometimes we like to have an “object type” that can be used to create many objects of one type.
+ The standard way to create an “object type” is to use an object constructor function.
+ The following function **car** is an object constructor, Once you have an object constructor, you can create new objects of the same type.

~~~~
// car constructor
function car(type, model, color){
	this.type = type;
	this.model = model;
	this.color = color;
}

var my_car1 = new car("Fiat","500","white");
var my_car2 = new car("Honda","Fit","black");
~~~~

# Array of Objects

~~~~
// car constructor
function car(type, model, color){
	this.type = type;
	this.model = model;
	this.color = color;
}

var cars = new Array();
cars[0] = new car("Fiat","500","white");
cars[1] = new car("Honda","Fit","black");
~~~~

# JavaScript Loops
+ Loops can execute a block of code a number of times.
+ Loops are handy, if you want to run the same code over and over again, each time with a different value.

~~~~
var fruits = ["apple", "banana", "pear", "peach"];
var text = "";
text += fruits[0] + "<br>";
text += fruits[1] + "<br>";
text += fruits[2] + "<br>";
text += fruits[3] + "<br>";
~~~~

~~~~
var fruits = ["apple", "banana", "pear", "peach"];
var text = "";
var i;
for(i=0; i<fruites.length; i++){
	text += fruits[i] + <br>;
}
~~~~

# Different Kinds of Loops
+ **for** - loops through a block of code a number of times.
+ **while** - loops through a block of code while a specified condition is true.
+ **do/while** - also loops through a block of code while a specified condition is true.
+ **for/in** - loops through the properties of an object.
+ **for/of** - loops through the values of an iterable object.

## for loop
+ syntax
	- statement 1 is executed before the loop(the code block) starts;
	- statement 2 defines the condition for running the loop(the code block);
	- statement 3 is executed after the loop(the code block) has been executed.
~~~~
for(statement 1; statement 2; statement 3){
	code block to be executed
}
~~~~

+ example

~~~~
var fruits = ["apple", "banana", "pear", "peach"];
var text = "";
var i;
for(i=0; i<fruites.length; i++){
	text += fruits[i] + <br>;
}
~~~~

## while loop

+ sytax

~~~~
while(condition){
	code block to be executed
}
~~~~

+ example

~~~~
var fruits = ["apple", "banana", "pear", "peach"];
var text = "";
var i = 0;
while(i<fruites.length){
	text += fruits[i] + <br>;
	i++;
}
~~~~

## do-while loop

+ syntax

~~~~
do{
	code to be executed
}
while(condition)
~~~~
+ the loop will be executed at least once.
+ example
~~~~
var fruits = ["apple", "banana", "pear", "peach"];
var text = "";
var i = 0;
do{
	text += fruits[i] + <br>;
	i++;
}
while(i<fruites.length)
~~~~
## for/in
### for/in over objects
+ Syntax
~~~
for (key in object) {
  // code block to be executed
}
~~~

~~~~
const person = {fname:"John", lname:"Doe", age:25};

let text = "";
for (let x in person) {
  text += person[x];
}
~~~~
#### Explanation
+ The for in loop iterates over a `person` object
+ Each iteration returns a `key` (x)
+ The key is used to access the value of the key
+ The value of the key is `person[x]`
### For In Over Arrays
+ Syntax
~~~
for (variable in array) {
  code
}
~~~
~~~~
const numbers = [45, 4, 9, 16, 25];

let txt = "";
for (let x in numbers) {
  txt += numbers[x];
}
~~~~
## for/of
+ **variable** - For every iteration the value of the next property is assigned to the variable. Variable can be declared with `const`, `let`, or `var`.
+ **iterable** - An object that has iterable properties.
~~~~
const cars = ["BMW", "Volvo", "Mini"];

let text = "";
for (let x of cars) {
  text += x;
}
~~~~

~~~~
let language = "JavaScript";

let text = "";
for (let x of language) {
text += x;
}
~~~~


# Conditional Statements
+ Conditional statements are used to perform di↵erent actions based on different conditions.
	- Use `if` to specify a block of code to be executed, if a specified condition is true.
	- Use `else` to specify a block of code to be executed, if the same condition is false.
	- Use `else if` to specify a new condition to test, if the first condition is false.
## if statement
+ syntax

~~~~
if(condition){
	code to be executed if the condition is true
}
~~~~

+ example
	- Note: Some special charaters can not be displayed if those charaters are used directly in your HTML file.
	~~~~
	& becomes &amp
	< becomes &lt
	> becomes &gt
	" becomes &quot
	' becomes &#39
	~~~~

~~~~
var a = 1;
var b = 2;
if(a < b){
	document.getElementById("p1").innerHTML = 'a<b';
}
~~~~

## else statment
+ syntax

~~~~
if(condition){
	code to be executed if the condition is true
}
else{
	code to be executed if the condition is false
}
~~~~

+ example

~~~~
var a = 1;
var b = 2;
if(a < b){
	document.getElementById("p1").innerHTML = 'a<b';
}
else{
	document.getElementById("p1").innerHTML = 'a>=b';
}
~~~~

## else if
+ syntax

~~~~
if(condition1){
	code to be executed if the condition 1 is true
}
else if(condition 2){
	code to be executed if the condition 2 is true
}
else{
	code to be executed if the condition 2 is false
}
~~~~

+ example

~~~~
var a = 1;
var b = 2;
if(a < b){
	document.getElementById("p1").innerHTML = 'a<b';
}
else if(a > b){
	document.getElementById("p1").innerHTML = 'a>b';
}
else{
	document.getElementById("p1").innerHTML = 'a==b';
}
~~~~

# break and continue
+ The break statement "jumps out" of a loop.
+ The continue statement "jumps over" one iteration in the loop.

~~~~
var i;
for (i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}
~~~~

~~~~
var i;
for (i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}
~~~~

# switch statement
+ The switch statement is used to perform di↵erent actions based on di↵erent conditions.
+ syntax
~~~~
switch(expression){
	case x:
		code to be executed if expression == x
		break;
	case y:
		code to be executed if expression == y
		break;
	case z:
		code to be executed if expression == z
		break;
	default:
		code to be executed
}
~~~~
+ the `switch` expression is evaluated once;
+ the value of the expression is compared with the values of each case;
+ if the is a match, the associated block of code will be executed.

~~~~
switch(new Date().getDay()){
	case 0: 
	day = "Sunday";
	break;
	case 1: 
	day = "Monday";
	break;
	case 2: 
	day = "Tuesday";
	break;
	case 3: 
	day = "Wednesday";
	break;
	case 4: 
	day = "Thursday";
	break;
	case 5: 
	day = "Friday";
	break;
	case 6: 
	day = "Saturday";
	break;
}
~~~~

# JavaScript Comments
+ JavaScript comments can be used to explain JavaScript code, and to make it more readable.
+ JavaScript comments can also be used to prevent execution, when testing alternative code.
## Single Line Comments
+ Single line comments start with //.

## Multi-line Comments
+ Multi-line comments start with /* and end with */.

# Debug
+ console.log(var_name)
+ Right click the webpage, choose `Inspect`, then the `Console` tab.(In this class, we use Google Chrome as our default web browser.)

# [Homework 3](https://github.com/ZhangNingSAU/Fall-2021-CSCI-330-Web-Programming/blob/master/Homework/HW3.md)

