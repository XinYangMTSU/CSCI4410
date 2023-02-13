# CSCI 330 Fall 2021
# Part 6: PHP

## What is PHP?
+ PHP is an acronym for "PHP: Hypertext Preprocessor"
+ PHP is a widely-used, open source scripting language
+ PHP scripts are executed on the server
+ PHP is free to download and use
+ PHP 8 is the latest stable release.
## What is a PHP File?
+ PHP files can contain text, HTML, CSS, JavaScript, and PHP code
+ PHP code is executed on the server, and the result is returned to the browser as plain HTML
+ PHP files have extension ".php"

## What Can PHP Do?
+ PHP can generate dynamic page content
+ PHP can create, open, read, write, delete, and close files on the server
+ PHP can collect form data
+ PHP can send and receive cookies
+ PHP can add, delete, modify data in your database
+ PHP can be used to control user-access
+ PHP can encrypt data

## Why PHP?
+ PHP runs on various platforms (Windows, Linux, Unix, Mac OS X, etc.)
+ PHP is compatible with almost all servers used today (Apache, IIS, etc.)
+ PHP supports a wide range of databases
+ PHP is free. Download it from the official PHP resource: www.php.net
+ PHP is easy to learn and runs efficiently on the server side


## Basic PHP Syntax
+ A PHP script can be placed anywhere in the document.

+ A PHP script starts with `<?php` and ends with `?>`:

+ PHP statements end with a semicolon (;)
~~~~
<!DOCTYPE html>
<html>
<body>

<?php
echo "My first PHP script!";
?>

</body>
</html>
~~~~

## PHP Case Sensitivity

+ No case sensitivity for keywords (e.g. if, else, while, echo, etc.), classes, functions, and user-defined functions.
~~~~
<!DOCTYPE html>
<html>
<body>

<?php
ECHO "Hello World!<br>";
echo "Hello World!<br>";
EcHo "Hello World!<br>";
?>

</body>
</html>
~~~~
+ Case sensitivity for all variable names!
~~~~
<!DOCTYPE html>
<html>
<body>

<?php
$color = "red";
echo "My car is " . $color . "<br>";
echo "My house is " . $COLOR . "<br>";
echo "My boat is " . $coLOR . "<br>";
?>

</body>
</html>
~~~~

## Comments
+ single-line comments
~~~~
<?php
// This is a single-line comment

# This is also a single-line comment
?>
~~~~
+ multi-line comments
~~~~
<?php
/*
This is a multiple-lines comment block
that spans over multiple
lines
*/
?>
~~~~

## PHP Variables
### Creating (Declaring) PHP Variables
In PHP, a variable starts with the $ sign, followed by the name of the variable
~~~~
<?php
$txt = "Hello world!";
$x = 5;
$y = 10.5;
$flag = True;
?>
~~~~
Note: Unlike other programming languages, PHP has no command for declaring a variable. It is created the moment you first assign a value to it.
### Output Variables
The PHP echo statement is often used to output data to the screen.
~~~~
<?php
$txt = "SAU";
echo "I love $txt!";
?>
~~~~

~~~~
<?php
$txt = "SAU";
echo "I love " . $txt . "!";
?>
~~~~
### PHP Variables Scope
PHP has three different variable scopes:
+ local
+ global
+ static
#### local

~~~~
<?php
function myTest() {
    $x = 5; // local scope
    echo "<p>Variable x inside function is: $x</p>";
}
myTest();

// using x outside the function will generate an error
echo "<p>Variable x outside function is: $x</p>";
?>
~~~~

#### global
+ using x inside this function will generate an error
~~~~
<?php
$x = 5; // global scope

function myTest() {
    // using x inside this function will generate an error
    echo "<p>Variable x inside function is: $x</p>";
}
myTest();

echo "<p>Variable x outside function is: $x</p>";
?>
~~~~

+ The **global** keyword is used to access a global variable from within a function.

~~~~
<?php
$x = 5;
$y = 10;

function myTest() {
    global $x, $y;
    $y = $x + $y;
}

myTest();
echo $y; // outputs 15
?>
~~~~

+ PHP also stores all global variables in an array called **`$GLOBALS[index]`**. The index holds the name of the variable.

~~~~
<?php
$x = 5;
$y = 10;

function myTest() {
    $GLOBALS['y'] = $GLOBALS['x'] + $GLOBALS['y'];
}

myTest();
echo $y; // outputs 15
?>
~~~~

#### static
+ sometimes we want a local variable **NOT** to be deleted by using the **static** keyword.

~~~~
<?php
function myTest() {
    static $x = 0;
    echo $x;
    $x++;
}

myTest();
myTest();
myTest();
?>
~~~~



## PHP echo and print Statements
+ They are both used to output data to the screen.
+ **echo** has no return value.
+ **print** has a return value of 1

~~~~
<?php
$txt1 = "Learn PHP";
$txt2 = "W3Schools.com";
$x = 5;
$y = 4;

echo "<h2>" . $txt1 . "</h2>";
echo "Study PHP at " . $txt2 . "<br>";
echo $x + $y;

print "<h2>" . $txt1 . "</h2>";
print "Study PHP at " . $txt2 . "<br>";
print $x + $y;

?>
~~~~


## PHP Data Types

PHP supports the following data types:

+ String: A string can be any text inside quotes
~~~~
$s = "Hello World";
var_dump($s);
~~~~
Note: var_dump() function returns the data type and value;
+ Integer
~~~~
$x = 100;
var_dump($x);
~~~~
+ Float (floating point numbers - also called double)
~~~~
<?php
$x = 10.365;
var_dump($x);
?>
~~~~
+ Boolean
~~~~
$x = true;
$y = false;
~~~~
+ Array
~~~
<?php
$cars = array("Volvo","BMW","Toyota");
var_dump($cars);
?>
~~~


+ Object
    - An object is a data type which stores data and information on how to process that data.

    - In PHP, an object must be explicitly declared.
~~~~
<?php
class Car {
    function Car() {
        $this->model = "VW";
    }
}

// create an object
$herbie = new Car();

// show object properties
echo $herbie->model;
?>
~~~~


+ NULL
    - Null is a special data type which can have only one value: NULL.

    - A variable of data type NULL is a variable that has no value assigned to it.

    - If a variable is created without a value, it is automatically assigned a value of NULL.

    - Variables can also be emptied by setting the value to NULL:
~~~~
<?php
$x = "Hello world!";
$x = null;
var_dump($x);
?>
~~~~
+ Resource
    - The special resource type is not an actual data type. It is the storing of a reference to functions and resources external to PHP.

    - A common example of using the resource data type is a database call.

## PHP String Functions
+ **strlen()**: Return the Length of a String

~~~~
<?php
echo strlen("Hello world!"); // outputs 12
?>
~~~~

+ **str_word_count()**: Count the Number of Words in a String

~~~~
<?php
echo str_word_count("Hello world!"); // outputs 2
?>
~~~~

+ **strrev()**: Reverse a String

~~~~
<?php
echo strrev("Hello world!"); // outputs !dlrow olleH
?>
~~~~

+ **strpos()**: Search For a Text Within a String

~~~~
<?php
echo strpos("Hello world!", "world"); // outputs 6, 6 is the start index of "world", 0 is the first index in PHP
?>
~~~~

+ **str_replace()**: Replace Text Within a String

~~~~
<?php
echo str_replace("world", "Dolly", "Hello world!"); // outputs Hello Dolly!
echo str_replace("World", "Dolly", "Hello world!"); // outputs Hello world!
?>
~~~~

## PHP Numbers
### PHP Integers
+ PHP has the following functions to check if the type of a variable is integer:
    - is_int()
    - is_integer(): alias of is_int()
    - is_long(): alias of is_int()
    
~~~~
<?php
$x = 5985;
var_dump(is_int($x));

$x = 59.85;
var_dump(is_int($x));
?>
~~~~

### PHP Floats
+ PHP has the following functions to check if the type of a variable is float:
    - is_float()
    - is_double(): alias of is_float()
### PHP Infinity
+ PHP has the following functions to check if a numeric value is finite or infinite:
    - is_finite()
    - is_infinite()
~~~~
<?php
$x = 1.9e411;
var_dump($x);
echo "<br>";
var_dump(is_infinite($x));
?>
~~~~

### PHP NaN
+ PHP has the following functions to check if a value is not a number:
    - is_nan()
    
~~~~
<?php
$x = acos(8);
var_dump(is_nan($x));
?>
~~~~

### PHP Numerical Strings
+ The PHP is_numeric() function can be used to find whether a variable is numeric. The function returns true if the variable is a number or a numeric string, false otherwise.

~~~~
<?php
$x = 5985;
var_dump(is_numeric($x));

$x = "5985";
var_dump(is_numeric($x));

$x = "59.85" + 100;
var_dump(is_numeric($x));

$x = "Hello";
var_dump(is_numeric($x));
?>
~~~~



## PHP Constants
+ A constant is an identifier (name) for a simple value. The value cannot be changed during the script.

+ A valid constant name starts with a letter or underscore (no $ sign before the constant name).

+ Unlike variables, constants are automatically global across the entire script.

+ To create a constant, use the **define()** function.

~~~~
define(name, value, case-insensitive)
~~~~

~~~~
<?php
define("GREETING", "Welcome to W3Schools.com!"); // case-insensitive is false by default(GREETING is case-sensitive by deafault)
echo GREETING;
?>
~~~~

~~~~
<?php
define("GREETING", "Welcome to W3Schools.com!", true); // GREETING is not case-sensitive now.
echo greeting;
?>
~~~~

### PHP Constant Arrays

~~~~
<?php
define("cars", [
    "Alfa Romeo",
    "BMW",
    "Toyota"
]);
echo cars[0];
?>
~~~~

## PHP Operators

+ Arithmetic operators
+ Assignment operators
+ Comparison operators
+ Increment/Decrement operators
+ Logical operators
+ String operators
+ Array operators
+ Conditional assignment operators

### PHP Arithmetic Operators

|Operator|Name|Example|
|----|----|----|
|+|Addition|$x + $y|
|-|Subtraction|$x - $y|
|`*`|Multiplication|$x `*` $y|
|/|Division|$x / $y|
|%|Module|$x % $y|
|`**`|Exponentiation|$x` **` $y|


### PHP Assignment Operators
|Assignment|same as|
|---|---|
|x = y|x = y|
|x += y| x = x+ y|
|x -= y|x = x - y|
|x *= y|x = x*y|
|x /= y|x = x/y|
|x %= y|x = x%y|


### PHP Comparison Operators

|Operator|Name|Example|Result|
|----|----|----|----|
|==|Equal|$x == $y|Returns true if $x is equal to $y|
|===|Identical|$x == $y|Returns true if $x is equal to $y, and they are of the same type|
|!=|Not Equal|||
|<>|Not Equal|||
|!==|Not Identical|||
|>|Greater than|||
|>|Less than|||
|>=|Greater than or equal to|||
|<=|Less than or equal to|||
|<=>|Spaceship|$x <=> $y|Returns an integer less than, equal to, or greater than zero, depending on if $x is less than, equal to, or greater than $y. Introduced in PHP 7.|


~~~~
<!DOCTYPE html>
<html>
<body>

<?php
$x = 5;  
$y = 10;

echo ($x <=> $y); // returns -1 because $x is less than $y
echo "<br>";

$x = 10;  
$y = 10;

echo ($x <=> $y); // returns 0 because values are equal
echo "<br>";

$x = 15;  
$y = 10;

echo ($x <=> $y); // returns +1 because $x is greater than $y
?>  

</body>
</html>
~~~~~



### PHP Increment / Decrement Operators

|Operator|Name|Description|
|----|----|----|
|++$x|Pre-increment|Increments $x by one, then returns $x|
|$x++|Post-increment|Returns $x, then increments $x by one|
|--$x|Pre-decrement|Decrements $x by one, then returns $x|
|$x--|Post-decrement|Returns $x, then decrements $x by one|


### PHP Logical Operators
|Operator|Name|Example|Result|
|----|----|----|----|
|and|	And|	$x and $y|	True if both $x and $y are true|
|or	|Or	|$x or $y|	True if either $x or $y is true|
|xor	|Xor	|$x xor $y	|True if either $x or $y is true, but not both|
|&&	|And	|$x && $y	|True if both $x and $y are true|
|\|\|	|Or	|$x \|\| $y|	True if either $x or $y is true|
|!	|Not	|!$x	|True if $x is not true|


### PHP String Operators
|Operator|Name|Example|Result|
|----|----|----|----|
|.|Concatenation|$txt1 . $txt2|Concatenation of $txt1 and $txt2|
|.=|Concatenation assignment|$txt1 .= $txt2|Appends $txt2 to $txt1|

### PHP Array Operators
|Operator|Name|Example|Result|
|----|----|----|----|
|+	|Union|	$x + $y	|Union of $x and $y	|
|==	|Equality|	$x == $y|	Returns true if $x and $y have the same key/value pairs	|
|===|	Identity|	$x === $y|	Returns true if $x and $y have the same key/value pairs in the same order and of the same types	|
|!=|	Inequality|	$x != $y|	Returns true if $x is not equal to $y	|
|<>	|Inequality|	$x <> $y|	Returns true if $x is not equal to $y|	
|!==|	Non-identity|	$x !== $y	|Returns true if $x is not identical to $y|


## PHP - The if Statement
+ syntanx
~~~~
if (condition) {
    code to be executed if condition is true;
}
~~~~
+ example
[PHP date function](https://www.w3schools.com/php/func_date_date.asp)
~~~~
<?php
$t = date("H");

if ($t < "20") {
    echo "Have a good day!";
}
?>
~~~~


## PHP - The if...else Statement

~~~~
if (condition) {
    code to be executed if condition is true;
} else {
    code to be executed if condition is false;
}
~~~~

## PHP - The if...elseif...else Statement

~~~~
if (condition) {
    code to be executed if this condition is true;
} elseif (condition) {
    code to be executed if first condition is false and this condition is true;
} else {
    code to be executed if all conditions are false;
}
~~~~

## PHP - The switch Statement
+ syntax

~~~~
switch (n) {
    case label1:
        code to be executed if n=label1;
        break;
    case label2:
        code to be executed if n=label2;
        break;
    case label3:
        code to be executed if n=label3;
        break;
    ...
    default:
        code to be executed if n is different from all labels;
}
~~~~

+ example
~~~~
<?php
$favcolor = "red";

switch ($favcolor) {
    case "red":
        echo "Your favorite color is red!";
        break;
    case "blue":
        echo "Your favorite color is blue!";
        break;
    case "green":
        echo "Your favorite color is green!";
        break;
    default:
        echo "Your favorite color is neither red, blue, nor green!";
}
?>
~~~~

## PHP while Loops
+ syntax
~~~~
while (condition is true) {
    code to be executed;
}
~~~~

+ example
~~~~
<?php
$x = 1;

while($x <= 5) {
    echo "The number is: $x <br>";
    $x++;
}
?>
~~~~


##  PHP do...while Loop
+syntax
~~~~
do {
    code to be executed;
} while (condition is true);
~~~~

## PHP for Loops
+syntax
~~~~
for (init counter; test counter; increment counter) {
    code to be executed;
}
~~~~
+ example
~~~~
<?php
for ($x = 0; $x <= 10; $x++) {
    echo "The number is: $x <br>";
}
?>
~~~~
## PHP foreach Loop
+ syntax
~~~~
foreach ($array as $value) {
    code to be executed;
}
~~~~
+ example
~~~~
<?php
$colors = array("red", "green", "blue", "yellow");

foreach ($colors as $value) {
    echo "$value <br>";
}
?>
~~~~

## PHP Functions
+ syntax
~~~~
function functionName() {
    code to be executed;
}
~~~~
+ example
~~~~
<?php
function writeMsg() {
    echo "Hello world!";
}

writeMsg(); // call the function
?>
~~~~

### PHP Function Arguments

~~~~
<?php
function familyName($fname) {
    echo "$fname Refsnes.<br>";
}

familyName("Jani");
familyName("Hege");
familyName("Stale");
familyName("Kai Jim");
familyName("Borge");
?>
~~~~

~~~~
<?php
function familyName($fname, $year) {
    echo "$fname Refsnes. Born in $year <br>";
}

familyName("Hege", "1975");
familyName("Stale", "1978");
familyName("Kai Jim", "1983");
?>
~~~~

### Loose Type vs Strict Type
+ compare the following two examples

~~~~
<?php
function addNumbers(int $a, int $b) {
    return $a + $b;
}
echo addNumbers(5, "5 days");
// since strict is NOT enabled "5 days" is changed to int(5), and it will return 10
?>
~~~~

~~~~
<?php declare(strict_types=1); // strict requirement

function addNumbers(int $a, int $b) {
    return $a + $b;
}
echo addNumbers(5, "5 days");
// since strict is enabled and "5 days" is not an integer, an error will be thrown
?>
~~~~


### PHP Default Argument Value

~~~~
<?php declare(strict_types=1); // strict requirement
function setHeight(int $minheight = 50) {
    echo "The height is : $minheight <br>";
}

setHeight(350);
setHeight(); // will use the default value of 50
setHeight(135);
setHeight(80);
?>
~~~~


### PHP Functions - Returning values
~~~~
<?php declare(strict_types=1); // strict requirement
function sum(int $x, int $y) {
    $z = $x + $y;
    return $z;
}

echo "5 + 10 = " . sum(5, 10) . "<br>";
echo "7 + 13 = " . sum(7, 13) . "<br>";
echo "2 + 4 = " . sum(2, 4);
?>
~~~~

## PHP Arrays

### create an array
~~~~
<?php
$cars = array("Volvo", "BMW", "Toyota");
echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";
?>
~~~~

### Get The Length of an Array - The count() Function
~~~~
<?php
$cars = array("Volvo", "BMW", "Toyota");
echo count($cars);
?>
~~~~


### Loop Through an Indexed Array
~~~~
<?php
$cars = array("Volvo", "BMW", "Toyota");
$arrlength = count($cars);

for($x = 0; $x < $arrlength; $x++) {
    echo $cars[$x];
    echo "<br>";
}
?>
~~~~
### PHP Associative Arrays
~~~~
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");
echo "Peter is " . $age['Peter'] . " years old.";
?>
~~~~
### Loop Through an Associative Array
~~~~
<?php
$age = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach($age as $x => $x_value) {
    echo "Key=" . $x . ", Value=" . $x_value;
    echo "<br>";
}
?>
~~~~

### PHP - Sort Functions For Arrays
+ sort() - sort arrays in ascending order
+ rsort() - sort arrays in descending order
+ asort() - sort associative arrays in ascending order, according to the value
+ ksort() - sort associative arrays in ascending order, according to the key
+ arsort() - sort associative arrays in descending order, according to the value
+ krsort() - sort associative arrays in descending order, according to the key

## PHP Global Variables - Superglobals [More details here](https://www.w3schools.com/php/php_superglobals.asp)
+ `$GLOBALS`: `$GLOBALS` is a PHP super global variable which is used to access global variables from anywhere in the PHP script (also from within functions or methods).
~~~~
<?php
$x = 75;
$y = 25;
 
function addition() {
    $GLOBALS['z'] = $GLOBALS['x'] + $GLOBALS['y'];
}
 
addition();
echo $z;
?>
~~~~
+`$_SERVER`: `$_SERVER` is a PHP super global variable which holds information about headers, paths, and script locations.
~~~~
<?php
echo $_SERVER['PHP_SELF'];
echo "<br>";
echo $_SERVER['SERVER_NAME'];
echo "<br>";
echo $_SERVER['HTTP_HOST'];
echo "<br>";
echo $_SERVER['HTTP_REFERER'];
echo "<br>";
echo $_SERVER['HTTP_USER_AGENT'];
echo "<br>";
echo $_SERVER['SCRIPT_NAME'];
?>
~~~~
+ `$_REQUEST`: PHP `$_REQUEST` is used to collect data after submitting an HTML form.
~~~~
<html>
<body>

<form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
  Name: <input type="text" name="fname">
  <input type="submit">
</form>

<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // collect value of input field
    $name = $_REQUEST['fname'];
    if (empty($name)) {
        echo "Name is empty";
    } else {
        echo $name;
    }
}
?>

</body>
</html>
~~~~
+ `$_POST`: PHP `$_POST` is widely used to collect form data after submitting an HTML form with method="post". `$_POST` is also widely used to pass variables.
~~~~
<html>
<body>

<form method="post" action="<?php echo $_SERVER['PHP_SELF'];?>">
  Name: <input type="text" name="fname">
  <input type="submit">
</form>

<?php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    // collect value of input field
    $name = $_POST['fname'];
    if (empty($name)) {
        echo "Name is empty";
    } else {
        echo $name;
    }
}
?>

</body>
</html>
~~~~
+ `$_GET`: 
    - PHP `$_GET` can also be used to collect form data after submitting an HTML form with method="get".

    - `$_GET` can also collect data sent in the URL.

~~~~
<!-- Assume we have an HTML page that contains a hyperlink with parameters: -->
<html>
<body>

<a href="test_get.php?subject=PHP&web=W3schools.com">Test $GET</a>

</body>
</html>
~~~~

~~~~
/*
When a user clicks on the link "Test $GET", the parameters "subject" and "web" are sent to "test_get.php", and you can then access their values in "test_get.php" with $_GET.

The example below shows the code in "test_get.php":
*/
<html>
<body>

<?php
echo "Study " . $_GET['subject'] . " at " . $_GET['web'];
?>

</body>
</html>

~~~~
+ `$_FILES`
+ `$_ENV`
+ `$_COOKIE`
+ `$_SESSION`

## Forms
The PHP superglobals `$_GET` and `$_POST` are used to collect form-data.
### GET vs. POST
+ Both `GET` and `POST` create an array (e.g. array( key1 => value1, key2 => value2, key3 => value3, ...)). This array holds `key/value` pairs, where keys are the names of the form controls and values are the input data from the user.

+ Both `GET` and `POST` are treated as `$_GET` and `$_POST`. These are superglobals, which means that they are always accessible, regardless of scope - and you can access them from any function, class or file without having to do anything special.

+ `$_GET` is an array of variables passed to the current script via the URL parameters.

+ `$_POST` is an array of variables passed to the current script via the HTTP POST method.

+ **Information sent from a form with the GET method is visible to everyone, GET may be used for sending non-sensitive data**
+ **Information sent from a form with the POST method is invisible to others, Developers prefer POST for sending form data.**

### `$_POST`

~~~~
<!-- in test.html -->
<!DOCTYPE html>
<html>
<body>

<form action="test.php" method="post">
Name: <input type="text" name="name"><br>
E-mail: <input type="text" name="email"><br>
<input type="submit">
</form>

</body>
</html>
~~~~
When the user fills out the form above and clicks the submit button, the form data is sent for processing to a PHP file named "test.php". The form data is sent with the HTTP POST method.
~~~~
<!-- in test.php -->

<html>
<body>

Welcome <?php echo $_POST["name"]; ?><br>
Your email address is: <?php echo $_POST["email"]; ?>

</body>
</html>
~~~~
### `$_GET`

~~~~
<!-- in test.html -->
<html>
<body>

<form action="test.php" method="get">
Name: <input type="text" name="name"><br>
E-mail: <input type="text" name="email"><br>
<input type="submit">
</form>

</body>
</html>
~~~~

~~~~
<!-- in test.php -->
<html>
<body>

Welcome <?php echo $_GET["name"]; ?><br>
Your email address is: <?php echo $_GET["email"]; ?>

</body>
</html>
~~~~


## PHP Form Validation
Proper validation of form data is important to protect your form from hackers and spammers!

~~~~
<!-- test.php -->
<!DOCTYPE HTML>  
<html>
<head>
</head>
<body>  

<?php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>

<h2>PHP Form Validation Example</h2>
<form method="post" action="<?php echo htmlspecialchars($_SERVER['PHP_SELF']);?>">  
  Name: <input type="text" name="name">
  <br><br>
  E-mail: <input type="text" name="email">
  <br><br>
  Website: <input type="text" name="website">
  <br><br>
  Comment: <textarea name="comment" rows="5" cols="40"></textarea>
  <br><br>
  Gender:
  <input type="radio" name="gender" value="female">Female
  <input type="radio" name="gender" value="male">Male
  <input type="radio" name="gender" value="other">Other
  <br><br>
  <input type="submit" name="submit" value="Submit">  
</form>

<?php
echo "<h2>Your Input:</h2>";
echo $name;
echo "<br>";
echo $email;
echo "<br>";
echo $website;
echo "<br>";
echo $comment;
echo "<br>";
echo $gender;
?>

</body>
</html>
~~~~

### The Form Element
~~~~
<form method="post" action="<?php echo htmlspecialchars($_SERVER['PHP_SELF']);?>">
~~~~

+ When the form is submitted, the form data is sent with method="post".
+ The `$_SERVER["PHP_SELF"]` is a super global variable that returns the filename of the currently executing script.
+ The htmlspecialchars() function converts special characters to HTML entities. This means that it will replace HTML characters like `<` and `>` with `&lt`; and `&gt`;. This prevents attackers from exploiting the code by injecting HTML or Javascript code (Cross-site Scripting attacks) in forms.
+ **The `$_SERVER["PHP_SELF"]` variable can be used by hackers!** 
+ `$_SERVER["PHP_SELF"]` exploits can be avoided by using the htmlspecialchars() function. [See details here](https://www.w3schools.com/php/php_form_validation.asp)

### Validate Form Data With PHP
+ The first thing we will do is to pass all variables through PHP's htmlspecialchars() function.
+ Strip unnecessary characters (extra space, tab, newline) from the user input data (with the PHP trim() function)
+ Remove backslashes `(\)` from the user input data (with the PHP stripslashes() function)
~~~~
<?php
// define variables and set to empty values
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>
~~~~

+ Remove multiple backslashes

~~~~
<?php
function removeslashes($string)
{
    $string=implode("",explode("\\",$string));
    return stripslashes(trim($string));
}

/* Example */

$text="My dog don\\\\\\\\\\\\\\\\'t like the postman!";
echo removeslashes($text);
?>
~~~~


## PHP Forms - Required Fields

~~~~
<!-- test.php -->
<!DOCTYPE HTML>  
<html>
<head>
</head>
<body>  


<?php
// define variables and set to empty values
$nameErr = $emailErr = $genderErr = $websiteErr = "";
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  if (empty($_POST["name"])) {
    $nameErr = "Name is required";
  } else {
    $name = test_input($_POST["name"]);
  }

  if (empty($_POST["email"])) {
    $emailErr = "Email is required";
  } else {
    $email = test_input($_POST["email"]);
  }

  if (empty($_POST["website"])) {
    $website = "";
  } else {
    $website = test_input($_POST["website"]);
  }

  if (empty($_POST["comment"])) {
    $comment = "";
  } else {
    $comment = test_input($_POST["comment"]);
  }

  if (empty($_POST["gender"])) {
    $genderErr = "Gender is required";
  } else {
    $gender = test_input($_POST["gender"]);
  }
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>

<h2>PHP Form Validation Example</h2>
<form method="post" action="<?php echo htmlspecialchars($_SERVER['PHP_SELF']);?>">  
Name: <input type="text" name="name">
<span class="error">* <?php echo $nameErr;?></span>
<br><br>
E-mail:
<input type="text" name="email">
<span class="error">* <?php echo $emailErr;?></span>
<br><br>
Website:
<input type="text" name="website">
<span class="error"><?php echo $websiteErr;?></span>
<br><br>
Comment: <textarea name="comment" rows="5" cols="40"></textarea>
<br><br>
Gender:
<input type="radio" name="gender" value="female">Female
<input type="radio" name="gender" value="male">Male
<input type="radio" name="gender" value="other">Other
<span class="error">* <?php echo $genderErr;?></span>
<br><br>
<input type="submit" name="submit" value="Submit">
</form>

<?php
echo "<h2>Your Input:</h2>";
echo $name;
echo "<br>";
echo $email;
echo "<br>";
echo $website;
echo "<br>";
echo $comment;
echo "<br>";
echo $gender;
?>

</body>
</html>
~~~~

## PHP Forms - Validate Name, E-mail and URL
### PHP - Validate Name
~~~~
$name = test_input($_POST["name"]);
if (!preg_match("/^[a-zA-Z ]*$/",$name)) {
  $nameErr = "Only letters and white space allowed";
}
~~~~

### PHP - Validate E-mail
~~~~
$email = test_input($_POST["email"]);
if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
  $emailErr = "Invalid email format";
}
~~~~

### PHP - Validate URL
~~~~
$website = test_input($_POST["website"]);
if (!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i",$website)) {
  $websiteErr = "Invalid URL";
}
~~~~

## PHP Complete Form Example
### PHP - Keep The Values in The Form
+ To show the values in the input fields after the user hits the submit button, we add a little PHP script inside the value attribute of the following input fields: name, email, and website. In the comment textarea field, we put the script between the <textarea> and `</textarea>` tags. The little script outputs the value of the $name, $email, $website, and $comment variables. 

+ Then, we also need to show which radio button that was checked. For this, we must manipulate the checked attribute (not the value attribute for radio buttons)

~~~~
<!DOCTYPE HTML>  
<html>
<head>
<style>
.error {color: #FF0000;}
</style>
</head>
<body>  

<?php
// define variables and set to empty values
$nameErr = $emailErr = $genderErr = $websiteErr = "";
$name = $email = $gender = $comment = $website = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  if (empty($_POST["name"])) {
    $nameErr = "Name is required";
  } else {
    $name = test_input($_POST["name"]);
    // check if name only contains letters and whitespace
    if (!preg_match("/^[a-zA-Z-' ]*$/",$name)) {
      $nameErr = "Only letters and white space allowed";
    }
  }
  
  if (empty($_POST["email"])) {
    $emailErr = "Email is required";
  } else {
    $email = test_input($_POST["email"]);
    // check if e-mail address is well-formed
    if (!filter_var($email, FILTER_VALIDATE_EMAIL)) {
      $emailErr = "Invalid email format";
    }
  }
    
  if (empty($_POST["website"])) {
    $website = "";
  } else {
    $website = test_input($_POST["website"]);
    // check if URL address syntax is valid (this regular expression also allows dashes in the URL)
    if (!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i",$website)) {
      $websiteErr = "Invalid URL";
    }
  }

  if (empty($_POST["comment"])) {
    $comment = "";
  } else {
    $comment = test_input($_POST["comment"]);
  }

  if (empty($_POST["gender"])) {
    $genderErr = "Gender is required";
  } else {
    $gender = test_input($_POST["gender"]);
  }
}

function test_input($data) {
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>

<h2>PHP Form Validation Example</h2>
<p><span class="error">* required field</span></p>
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>">  
  Name: <input type="text" name="name" value="<?php echo $name;?>">
  <span class="error">* <?php echo $nameErr;?></span>
  <br><br>
  E-mail: <input type="text" name="email" value="<?php echo $email;?>">
  <span class="error">* <?php echo $emailErr;?></span>
  <br><br>
  Website: <input type="text" name="website" value="<?php echo $website;?>">
  <span class="error"><?php echo $websiteErr;?></span>
  <br><br>
  Comment: <textarea name="comment" rows="5" cols="40"><?php echo $comment;?></textarea>
  <br><br>
  Gender:
  <input type="radio" name="gender" <?php if (isset($gender) && $gender=="female") echo "checked";?> value="female">Female
  <input type="radio" name="gender" <?php if (isset($gender) && $gender=="male") echo "checked";?> value="male">Male
  <input type="radio" name="gender" <?php if (isset($gender) && $gender=="other") echo "checked";?> value="other">Other  
  <span class="error">* <?php echo $genderErr;?></span>
  <br><br>
  <input type="submit" name="submit" value="Submit">  
</form>

<?php
echo "<h2>Your Input:</h2>";
echo $name;
echo "<br>";
echo $email;
echo "<br>";
echo $website;
echo "<br>";
echo $comment;
echo "<br>";
echo $gender;
?>

</body>
</html>
~~~~
# Reference:
[www.w3schools.com](https://www.w3schools.com/php/default.asp)

