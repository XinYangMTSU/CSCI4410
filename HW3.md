# CSCI 330 Fall 2021
# Homework 3
# due: 11:59 pm Wednesday 10/06/2021

# You are working for a large supermarket and the cash register has just failed. The boss is not happy as he can’t make any money. To save the day it happens that you let slip to your boss that you know JavaScript and can build a quick virtual cash register until head office sends support staff. Your boss is over the moon and wants you to get started right away.

# Step 1: Create your JavaScript file. (70 points)
Please create your JavaScript file, name it as cash.js. Please remember the extension should be .js. And then add the following three parts to your javascript file.

## 1.1 Create a cashRegister object.
+ Create a new object called **cashRegister** with **two properties**, and **one method**.
+ The first property is **total**, it should be initialized to 0.
+ The second property is **item**, it should be initialized to 0.
+ The method is called **add** with one parameter **itemCost**.
+ Inside the **add** method, add **itemCost** to **this.total** by using +=. So that you can add items cost together by calling the method **add**:
  - cashRegister.add(0.98)
  - cashRegister.add(1.23)
## 1.2 Create a scan function.
+ Create a function called **scan** with no parameters.
+ Ask the user to enter the total items number by using **prompt**, and save the entered number to **cashRegister.item**.
+ Then use a **for loop** to **prompt** the user to enter the cost for each item.
+ You need to add each item cost to the total by calling the method **add**.
+ Note that the variables you receive from **prompt** is a string, not a number. You can use **parseFloat/parseInt** to convert the string cost to float/int cost, eg:
  - cashRegister.add(parseFloat(cost));
  
## 1.3 Create a print function.

+ Create a function called **print** with no parameters.
+ Please use **if/else** statement to print out the results by using **confirm**.
  - If cashRegister.total equal to 0, then you need to print out “Please enter your items cost first”.
  - Else you need to print out the total items cost by using cashRegister.total.
  
# Step 2: Create your HTML file.
Please create your HTML file, name it as **cash.html**. Please remember the extension should be .html. And then add the following parts to your HTML file.
## 2.1 Create a basic structure HTML (15 points)
+ Declaration line.
+ `<html></html> `
+ `<head></head> `
+ `<title></title> `
+ `<body></body>`
## 2.2 Link JavaScript file to HTML file by using `<script> </script>`

## 2.3 Create a button scan

+ Please create a button called **Scan your item** by using `<button></button>` tags.
+ When you click this button, the function **scan()** you create in cash.js file will be called.


## 2.4 Create a button print
+ Please create a button called **Total** by using `<button></button>` tags.
+ When you click this button, the function **print()** you create in cash.js file will be called.


## 2.5 You can add a heading title at the top of your page, eg: “Welcome to use my cash Register!”

## 2.6 You can use `<div></div>` block tags to create container for your webpage.

# Step 3: Create your CSS file. (15 points)

+ Please create your CSS file, name it as **cash.css**. Please remember the extension should be .css.
+ Design your own CSS style.
+ Link your CSS file to HTML file by using `<link>`

# Step 4: Zip the 3 files (js, html and css) as one archive, name it as "CSCI330_Homework3_JohnDoe(01234567)" and submit it to [Blackboard](https://blackboard.sau.edu)

