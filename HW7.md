# CSCI 330 Fall 2021
# Homework 7 for PHP, MySQL and Database
# 
# due: 11:59 pm Friday 12/03/2021


# Step 1: On phpMyAdmin webpage, create a database named "csci330" and a table/relation named "students" as follows and add enough rows/tuples for step 2.
**Note**: 
+ at least one student without phone number(when you are creating the table in the database, make sure check the Null checkbox, otherwise the default phone number is an empty string, not a null)
+ make sure John Doe (the first row) is in the table.

|ID|Name|BeeCard|Major|Class Level|Email|Gender|Age|Phone|
|----|----|----|----|----|----|----|----|----|
|1|John Doe|01234567|Computer Science|Freshman|DoeJohn@sau.edu|Male|19|123-456-7890|
|2|Jane Doe|07654321|Mathematics|Senior|DoeJane@sau.edu|Female|22||

# Step 2(100 points): Create a php, in which you need to
+ create a connection to the database you just created in step 1
+ write and make the following SQL queries:
  - select all the male students
  - select all the students older than 21
  - select all the students without phone information(hint: NULL value)
  - find out how many differenct majors
  - find the minimum, maximum, and average age of all the students
  - insert a new row/tuple, then write a query to check if the insert is succussful or not.
  - delete the tuple you just inserted, then write a query to check if the delete is succussful or not.
  - update John Doe's phone number as 321-654-0987, then write a query to check if the update is succussful or not.
+ close the connection

# Step 3: Submit your php file in step 2 to [blackboard](https://blackboard.sau.edu/webapps/login/)
Please name the php file as "CSCI330_Homework7_JohnDoe(01234567).php" and submit it to [blackboard](https://blackboard.sau.edu/webapps/login/).
