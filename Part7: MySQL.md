# CSCI 330 Fall 2021
# Part 7: MySQL

## Why MySQL
+ With PHP, you can connect to and manipulate databases.

+ MySQL is the most popular database system used with PHP.

## What is MySQL?
+ MySQL is a database system used on the web
+ MySQL is a database system that runs on a server
+ MySQL is ideal for both small and large applications
+ MySQL is very fast, reliable, and easy to use
+ MySQL uses standard SQL
+ MySQL compiles on a number of platforms
+ MySQL is free to download and use
+ MySQL is developed, distributed, and supported by Oracle Corporation

## MySQL in XAMPP
+ type localhost in your web browser and you will see
![](../Resources/server-xamppworks.png)
+ click phpMyAdmin, you will see a website that can deal with database.
![](../Resources/mysql-admin.png)
+ Here is one [tuotrial](https://blog.templatetoaster.com/xampp-phpmyadmin/) to create databases, tables, and reset username and password in XAMPP. 
+ Here is [another](https://skillforge.com/how-to-create-a-database-using-phpmyadmin-xampp/)

## PHP + MySQL
+ Here is one example to open a MySQL database
+ In XAMPP, the servername is `localhost`, username is `root` and password is empty by default.
~~~~
<!DOCTYPE html>
<html>
<head>
	<title></title>
</head>
<body>
<?php
$servername = "localhost";
$username = "root";
$password = "";

// Create connection
$conn = new mysqli($servername, $username, $password);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";

$conn->close();
?>
</body>
</html>
~~~~

+ another example
~~~~
<?php
$servername = "localhost";
$username = "root";
$password = "";

// Create connection
$conn = new mysqli($servername, $username, $password);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Create database
$sql = "CREATE DATABASE myDB";
if ($conn->query($sql) === TRUE) {
    echo "Database created successfully";
} else {
    echo "Error creating database: " . $conn->error;
}

$conn->close();
?>
~~~~

**Note**: It is much easier to create databases and tables in http://localhost/phpmyadmin/
See [tutorial](https://skillforge.com/how-to-create-a-database-using-phpmyadmin-xampp/).

+ example 3: usually, we connect to some mysql database.
+ **mysqli_fetch_all()** function fetches all result rows and returns the result-set as an associative array, a numeric array, or both.
	- syntax
	~~~~
	mysqli_fetch_all(result,resulttype);
	~~~~
	- Parameter Values
	
	|Parameter|Description|
	|----|----|
	|result|Required. Specifies a result set identifier returned by mysqli_query(), mysqli_store_result() or mysqli_use_result()|
	|resulttype|Optional. Specifies what type of array that should be produced. Can be one of the following values:<br>MYSQLI_ASSOC<br>MYSQLI_NUM<br>MYSQLI_BOTH|
+ **print_r**: Prints human-readable information about a variable
~~~~
<?php
$servername = "localhost";
$username = "root";
$password = "";
$database = "csci330";
// Create connection
$conn = new mysqli($servername, $username, $password, $database);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// write the query
$sql = "SELECT * FROM students";
// make query & get result
$result = mysqli_query($conn, $sql);
// fetch the resulting rows as an associated array
$info = mysqli_fetch_all($result, MYSQLI_ASSOC);

print_r($info);



$conn->close();
?>
~~~~
### For MySQL INSERT, DELETE, and UPDATE queries 

~~~~
<?php
$servername = "localhost";
$username = "root";
$password = "";
$database = "csci330";
// Create connection
$conn = new mysqli($servername, $username, $password, $database);
// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// write the query
$sql = "DELETE FROM students WHERE Name = 'Ning Zhang'";
// make query & get result
if ($conn->query($sql) === TRUE) {
    echo "Record deleted successfully";
} else {
    echo "Error deleting record: " . $conn->error;
}



$conn->close();
?>

~~~~
### MySQL database
+ The data in a MySQL database are stored in tables. A table is a collection of related data, and it consists of columns and rows.
![customer](../Resources/mysql-customer.png)


## Database Queries(using standard SQL)
+ Before we learn PHP + MySQL, we need to learn some basic SQL queries.
+ Learn and practice queries at [w3schools.com](https://www.w3schools.com/MySQL/default.asp)

### SQL
SQL is a standard language for accessing and manipulating databases.
+ SQL stands for Structured Query Language
+ SQL lets you access and manipulate databases
+ SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987

### What Can SQL do?
+ SQL can execute queries against a database
+ SQL can retrieve data from a database
+ SQL can insert records in a database
+ SQL can update records in a database
+ SQL can delete records from a database
+ SQL can create new databases
+ SQL can create new tables in a database
+ SQL can create stored procedures in a database
+ SQL can create views in a database
+ SQL can set permissions on tables, procedures, and views


### RDBMS
+ RDBMS stands for Relational Database Management System.

+ RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

+ The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.







### SQL SELECT Statement
+ syntax
~~~~
SELECT column1, column2, ...
FROM table_name;
~~~~

+ select columns named CustomerName and City from database Customers
~~~~
SELECT CustomerName, City FROM Customers;
~~~~

+ select all the columns from database Customers
~~~~
SELECT * FROM Customers;
~~~~

### SQL SELECT DISTINCT Statement
The SELECT DISTINCT statement is used to return only distinct (different) values.
+ syntax
~~~~
SELECT DISTINCT column1, column2, ...
FROM table_name;
~~~~







# References
+ [PHP+ MySQL](https://www.w3schools.com/php/php_mysql_intro.asp)
+ [MySQL](https://www.w3schools.com/MySQL/default.asp)





