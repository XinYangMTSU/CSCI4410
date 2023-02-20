# CSCI 330 Fall 2021
# Homework 6 for PHP

# due: 11:59 pm Wednesday 11/10/2021

## Q1(15 points): PHP is case-sensitive for ___, NOT case-sensitive for ___.
A. keywords <br>
B. variable names

## Q2(15 points): $x is a ___ variable, $y is a ___ variable, $z is a ___ variable, and the value of $z is ___ after calling myTest() 4 times.
A. local <br>
B. global<br>
C. static<br>

~~~~
<?php
$x = 5; 

function myTest() {
    $y = 10;
    static $z = 100;
    $z -= 10;
    
}

myTest();
myTest();
myTest();
myTest();

?>
~~~~

## Q3(15 points): Define a function, which takes an indexed array as the only parameter, echo "The array is empty." if there is no item in the array, echo each item otherwise.

~~~~
<?php

function echo_indexed_array_info($arr) {
// add your code here
    
}

// also add some test code
?>
~~~~

## Q4(15 points): Define a function, which takes an associative array as the only parameter, echo "The array is empty." if there is no item in the array, echo each item (both key/name and value for each item) otherwise.

~~~~
<?php

function echo_accociative_array_info($arr) {
// add your code here
    
}

// also add some test code
?>
~~~~

## Q5(50 points): Create a form as following. 
+ You can choose one single php file or separate html and php files.
+ You can choose either POST or GET method.
+ Hints:
    - string concatenation
    ~~~~
    $txt1 . $txt2 //Concatenation of $txt1 and $txt2
    ~~~~
    - You can choose either switch-case or if-elseif-else statement for different types of calculation. Here is an example using switch-case
    ~~~~
    // suppose you define a global variable $operator in your php script, and assign the operator in $_POST or $_GET to $operator
    switch ($operator) {
  case '+':
    $ans =  $num1+$num2;
    break;
  case '-':
    $ans =  $num1-$num2;
    break;
  case '*':
    $ans =  $num1*$num2;
    break;
  case '/':
    $ans =  $num1/$num2;
    break;
  default:
    $ans = "";
    break;
    }
    ~~~~

![hw61](../Resources/hw61.png)

![hw62](../Resources/hw62.png)

![hw63](../Resources/hw63.png)

**Note**: 
+ You just need to provide the basic calculation: addition, subtraction, multiplication and division. We just suppose people will enter the correct operands everytime.
+ There will be a bonus of 10 points if you can deal with non-numeric inputs for the two operands.

# Step 1: Save the answers of Q1 - Q4 in PDF file.
# Step 2: Save the answer of Q5 in a PHP file or a html and a php file.
# Step 3: Submit your work to [blackboard](https://blackboard.sau.edu/webapps/login/)
Please zip the two or three files to an archive, name it as "CSCI330_Homework6_JohnDoe(01234567)" and submit the archive file to [blackboard](https://blackboard.sau.edu/webapps/login/).
