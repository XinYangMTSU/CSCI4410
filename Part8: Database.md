# CSCI 330 Fall 2021
# Part 8: Database

## Basic Definitions
+ Database:
  - A collection of related data.
+ Data:
  - Known facts that can be recorded and have an implicit meaning.
+ Mini-world:
  - Some part of the real world about which data is stored in a database. For example, student grades and transcripts at a university.
+ **Database Management System (DBMS)**:
  - A software package/ system to facilitate the creation and maintenance of a computerized database.
+ Database System:
  - The DBMS software together with the data itself.  Sometimes, the applications are also included.
  
  
### Simplified database system environment

![](http://secure.tutorsglobe.com/CMSImages/82_simplified%20database%20system.jpg)

### Typical DBMS Functionality
+ Define a particular database in terms of its data types, structures, and constraints
+ Construct or Load the initial database contents on a secondary storage medium
+ Manipulating the database:
  - Retrieval: Querying, generating reports
  - Modification: Insertions, deletions and updates to its content
  - Accessing the database through Web applications
+ Processing and Sharing by a set of concurrent users and application programs – yet, keeping all data valid and consistent

### Database Schema:
+ The description of a database.
+ Includes descriptions of the database structure, data types, and the constraints on the database.
### Schema Diagram:
+ An illustrative display of (most aspects of) a database schema.
### Schema Construct:
+ A component of the schema or an object within the schema, e.g., STUDENT, COURSE.

### Database State:
+ The actual data stored in a database at a particular moment in time. This includes the collection of all the data in the database.
+ Also called database instance (or occurrence or snapshot).
  - The term instance  is also applied to individual database components, e.g. record instance, table instance, entity instance
  
+ Database State:  Refers to the content of a database at a moment in time.
  - Initial Database State: Refers to the database state when it is initially loaded into the system.
  - Valid State: A state that satisfies the structure and constraints of the database.
+ Distinction
  - The database schema changes very infrequently. 
  - The database state changes every time the database is updated. 

+ Schema is also called intension.
+ State is also called extension.

#### Example of a Database Schema

![](../Resources/db-schema.png)

#### Example of a Database state

![](../Resources/db-state.png)

## Relational Model
### Concept
+ A Relation is a mathematical concept based on the ideas of sets
+ The model was first proposed by Dr. E.F. Codd of IBM Research in 1970 in the following paper:
  - “A Relational Model for Large Shared Data Banks,” Communications of the ACM, June 1970
+ The above paper caused a major revolution in the field of database management and earned Dr. Codd the coveted ACM Turing Award

![](../Resources/db-relation.png)

#### Informal Definition: Relation

+ Informally, a relation looks like a table of values. A relation typically contains a set of rows.
+ The data elements in each row represent certain facts that correspond to a real-world entity or relationship.
+ In the formal model, rows are called tuples.

#### Informal Definition: Attribute
+ Each column in a relation has a column header that gives an indication of the meaning of the data items in that column.
  - In the formal model, the column header is called an attribute name or just attribute)
+ Each attribute of a relation has a name
+ Name, Ssn, Home_phone, Address, Office_phone, Age, and Gpa are attributes of the relation STUDENT.

#### Informal Definition: Attribute Values
+ Each attribute has a set of values that can be assigned to the attribute.
  - In the formal model, the sets of allowed values are called Domains.
+ For example:
  - The values assigned to SSN is the set of valid nine-digit numbers
  - The values assigned to Name is the set of character strings representing names of persons
  - The values assigned to Age is the possible ages of employees of a company; each must be a value between 15 and 80.
+ Attribute values are (normally) required to be indivisible:
  - attribute cannot be multi-valued attribute
  - For example: the value of an attribute can be an account number, but cannot be a set of account numbers.
  - attribute cannot be composite attribute
  - In the formal model, the indivisible property is called to be **atomic**.
#### Informal Definition: Attribute Data Type
+ A data type or format is also specified for allowed values of an attribute(i.e. domain).
+ For example:
  - The data type of Name is string 
  - The data type of Ssn is string 
  - The data type of Age is integer
  - The data type of Gpa is real
  
+ Different attributes can have the same data type. 
  - Name and Ssn have the same data type – string
  
  
#### Informal Definition: NULL Value
+ The special value **NULL** can be a value of any attribute
+ The NULL value can have several meanings 
  - value unknown
  - For example: The home phone of a student is NULL
+ value value exists but is not available
  - For example: The age of student John is NULL
+ attributes does not apply to this tuple 
  - For example, Visa_Status attribute can only be applied to international students.
+ The null value causes complications in the definition of many operations.
  - For example: how to compare two NULL values?
  - We shall ignore the effect of null values in our main presentation and consider their effect later
  
#### Informal Definition: Key
+ **Key**: a set of attributes such that their values can uniquely identify rows in the table.
+ In the STUDENT table, SSN is the key.
+ Sometimes row-ids or sequential numbers are assigned as keys to identify the rows in a table.
  - Called **artificial key** or **surrogate key**'
#### Formal Definition: Relation Schema
+ Relation Schema is denoted by **R(A1,A2,...,An)**, 
  - where R is the name of the relation
  - A1, A2, ..., An are attributes of the relation
+ Example: STUDENT(Name, Ssn, Home_phone, Address, Office_phone, Age, Gpa) where
  - STUDENT is the relation name
  - Defined over 7 attributes: Name, Ssn, ..., Age, Gpa
+ Each attribute has a domain or a set of valid values. 
  - For example, the domain of Home_phone is 10 digit numbers
  
#### Formal Definition: Domain
+ A domain has a logical definition
  - Example: “USA_phone_numbers” are the set of 10 digit phone numbers valid in the U.S.
+ A domain also has a data-type or a format defined for it.
  - The USA_phone_numbers may have a format: (ddd)ddd-dddd where each d is a decimal digit.
  - Dates have various formats such as year, month, date formatted as yyyy-mm-dd, or as dd mm,yyyy etc.
+ The attribute name designates the role played by a domain in a relation:
  - Used to interpret the meaning of the data elements corresponding to that attribute
  - Example: The domain Date may be used to define two attributes named “Invoice-date” and “Payment-date” with different meanings

#### Formal Definition: Tuple
+ A tuple is an ordered set of values (enclosed in angled brackets ‘< ... >’)
+ Each value is derived from an appropriate domain.
+ A row in the STUDENT relation is a 7-tuple and would consist of 7 values, for example:
  - <“Benjamin Bayer”, 305-61-2435, 373-1616, “2918 Bluebonnet Lane”, NULL, 19, 3.21>
  - This is called a 7-tuple as it has 7 values A tuple(row) in the STUDENT relation
  - A relation is a set of such tuples(rows)
+ We refer to component values of a tuple t by: t[Ai] or t.Ai
  - This is the value vi of attribute Ai for tuple t
+ Similarly, t[Au, Av, ..., Aw] refers to the subtuple of t containing the values of attributes Au, Av, ..., Aw, respectively in t

#### Formal Definition: State
+ Relation(or Relation state): a subset of the Cartesian product of the domains of its attributes
  - denoted by r(R) = {t1, t2, ..., tm} where each ti is an n-tuple
  - ti ={v1,v2,...,vn} where each vi is an element of domain (Ai) or NULL
  
  
#### Formal Definition: Example
+ Let R(A1, A2) be a relation schema:
  - Let dom(A1) = {0,1}
  - Let dom(A2) = {a,b,c}
+ Then: dom(A1) X dom(A2) is all possible combinations: {<0,a> , <0,b> , <0,c>, <1,a>, <1,b>, <1,c> }
+ The relation state r(R) X dom(A1) X dom(A2)
+ For example: r(R) could be {<0,a> , <0,b> , <1,c> }
  - this is one possible state (or “population” or “extension”) r of the relation R, defined over A1 and A2.
  - It has three 2-tuples: <0,a> , <0,b> , <1,c>

### Relational Database Schema

+ Relational Database Schema S = {R1, R2, ..., Rn}, where 
  - S: the name of the whole database schema
  - R1, R2, ..., Rn are the names of the individual relation schemas within the database S
  - a set of relation schemas that belong to the same database
+ That is, a relational database schema is a set of relation schemas that belong to the same database


##  Characteristics
### Relation Characteristics
+ Ordering of tuples in a relation r(R):
  - The tuples are not considered to be ordered, even though they appear to be in the tabular form
+ Ordering of attributes in a relation schema R (and of values within each tuple):
  - We will consider the attributes in R(A1, A2, ..., An) and the values in t =< v 1, v 2, ..., vn > to be ordered .
  - However, a more general alternative definition of relation does not require this ordering

+ Values in a tuple
  - All values are considered atomic (indivisible).
  - Each value in a tuple must be from the domain of the attribute for that column
    + If tuple t = <v1, v2, ..., vn> is a tuple (row) in the relation state r of R(A1, A2, ..., An)
    + Then each vi must be a value from dom(Ai)
+ A special null value is used to represent values that are unknown or inapplicable to certain tuples

### Relational Integrity Constraints
+ Constraints: are conditions that must hold on all valid relation states
+ Three main types of constraints in the relational model:
  - Key constraints
  - Entity integrity constraints 
  + Referential integrity constraints
+ Another implicit constraint is the domain constraint
  - Every value in a tuple must be from the domain of its attribute (or it could be null, if allowed for that attribute)
#### Key Constraints
+ **Superkey** of R: a set of attributes SK of R with the following condition
  - No two tuples in any valid relation state r(R) will have the same value for SK
  - That is, for any distinct tuples t1 and t2 in r(R), t1[SK] ≠ t2[SK] 
  - This condition must hold in any valid state r(R)
+ Example: 
  - Consider the CAR relation schema: **CAR(State, Reg , SerialNo, Make, Model, Year)**
  - CAR has two keys:
    + Key1 = {State, Reg } Key2 = {SerialNo}
  - Both are also superkeys of CAR
  - {SerialNo, Make} is a superkey but not a key
  - In general:
    + Any key is a superkey (but not vice versa)
    + Any set of attributes that includes a key is a superkey 
    + A minimal superkey is also a key
    
#### Primary Key
+ If a relation has several candidate keys, one is chosen arbitrarily to be the primary key
  - The primary key attributes are underlined
+ For the CAR relation schema:
  - **CAR(State, Reg ,SerialNo, Make, Model, Year)**
  - Here, SerialNo is chosen as the primary key
+ The primary key provides the tuple identity, i.e. uniquely identify each tuple in a relation
+ Primary key can be used to reference the tuple from another tuple
  - **General rule**: Choose as primary key the smallest of the candidate keys (in terms of size)
  - Not always applicable - choice is sometimes subjective
  
  ![](../Resources/db-primarykey.png)
  
### Entity Integrity
+ Entity Integrity: The primary key attributes PK of each relation schema R in S cannot have null values in any tuple of r(R).
  - This is because primary key values are used to identify the individual tuples.
  - t[PK] ≠ null for any tuple t in r(R)
  - If PK has several attributes, null is not allowed in any of these attributes
+ Note
  - Other attributes of R may be constrained to disallow null values, even though they are not members of the primary key.

### Referential Integrity
+ Referential Integrity
  - A constraint involving two relations
  - Used to specify a relationship among tuples in two relations 
    + The referencing relation and the referenced relation.
+ Entity integrity constraints involve a single relation

+ Tuples in the **referencing relation R1** have attributes FK (called **foreign key** attributes) that reference the **primary key** attributes PK of the **referenced relation R2**.
  - A tuple t1 in R1 is said to reference a tuple t2 in R2 if t1[FK] = t2[PK].
  - Foreign key and corresponding primary key must have the same domain
+ A referential integrity constraint can be displayed in a relational database schema as a directed arc from R1.FK to R2.PK

#### Referential Integrity Constraint
+ Referential Integrity Constraint
  - The value in the foreign key column (or columns) FK of the the referencing relation R1 can be either:
    + 1. a value of an existing primary key value of a corresponding primary key PK in the referenced relation R2, or
    + 2. a **null**
+ In case (2), the FK in R1 should not be a part of its own primary key

### Semantic Integrity Constraint
+ Semantic Integrity Constraints
  - based on application semantics and cannot be expressed by the model per se
  - Example: “the max. no. of hours per employee for all projects he or she works on is 56 hrs per week”
+ A constraint specification language may have to be used to express these
+ SQL-99 allows triggers and ASSERTIONS to express for some of these


## Relational Schema Diagram
+ Each relation schema can be displayed as a row of attribute names
+ The name of the relation is written above the attribute names 
+ The primary key attribute (or attributes) will be underlined
+ A foreign key (referential integrity) constraints is displayed as a directed arc (arrow) from the foreign key attributes to the referenced table
  - Can also point the primary key of the referenced relation for clarity

![relationalschema](../Resources/db-relationalschema.png)


## Database State
+ Each relation will have many tuples in its current relation state
+ The relational database state is a union of all the individual relation states
+ Whenever the database is changed, a new state arises


## Operations on Relation
+ Basic operations for changing the database 
  - Retrieval operations
  - Update operations
    + **INSERT** a new tuple in a relation 
    + **DELETE** an existing tuple from a relation 
    + **MODIFY** an attribute of an existing tuple


+ Integrity constraints should not be violated by the update operations.
+ Several update operations may have to be grouped together.
+ Updates may propagate to cause other updates automatically. This may be necessary to maintain integrity constraints.


##  Constraint Violation
+ Update operation may violate constraints discussed previously
+ INSERT/UPDATE
  - Insert/change a tuple such that value of some attribute(s) is not of the specified attribute domain (**Domain Constraint Violation**)
  - Insert/change a tuple such that the primary key is not unique (**Key Constraint Violation**)
  - Insert/change a tuple such that the primary key is NULL (**Entity Integrity Violation**)
  - Insert/change a tuple such that values of foreign key do not exist at the referenced relation (**Referential Integrity Constraint Violation**)
  - Change a tuple such that the primary key is referenced by tuples of another relation (**Referential Integrity Constraint Violation**)
+ DELETE
  - Delete a tuple such that the primary key is referenced by tuples of another relation (**Referential Integrity Constraint**)
  
  
  
  
### Actions on Constraint Violation
+ In case of integrity violation, several actions can be taken
  - Cancel the operation that causes the violation (RESTRICT or REJECT option)
  - Perform the operation but inform the user of the violation
  - Trigger additional updates so the violation is corrected (CASCADE option, SET NULL option)
  - Execute a user-specified error-correction routine
#### Actions on INSERT
+ f a INSERT operation violates any of the constraints, it is **REJECTED**.
+ Give examples INSERT operations that violate different constraints


#### Actions on DELETE
+ DELETE operation may violate only referential integrity constraint
+ If the primary key value of the tuple being deleted is referenced from other tuples in the database, it can be remedied by the following actions:
  - **REJECT** the deletion
  - **CASCADE** – propagate the new primary key value into the foreign keys of the referencing tuples
  - **SET NULL** - set the foreign keys of the referencing tuples to NULL
+ One of the above options must be specified during database design for each foreign key constraint



#### Actions on UPDATE
+ The action to handle violations caused by UPDATE is similar to INSERT and DELETE operations.










