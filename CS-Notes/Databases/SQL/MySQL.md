
### Steps to use MySQL 
- Load Terminal
- Use command `mysql -u root -p` to connect to MySQL server

#### Commands
- `show databases;` to show the current databases in MySQL server

### SQL Questions 

##### What is SQL? 
- It stands for Structured Query Language. A programming language used for interaction with relational database management systems.
- This includes fetching, updating, inserting, and removing data from tables

##### What is the main application of SQL?
- create, delete, and update tables in a database
- access, manipulate, and modify data in a table
- retrieve and summarize the necessary information from a table or several tables
- add or remove certain rows or columns from a table

##### What is a Database?
- A structured storage space where the data is kept in many tables and organized so that the necessary information can be easily fetched, manipulated, and summarized

##### What are tables and fields in SQL? 
- A table is an organized set of related data stored in rows and columns
- A field is another term for a column of a table



##### What is a Primary Key? 
- A column in a table that uniquely identifies each row. 
- Enforces uniqueness so that no two rows have the same primary key values 
- The primary key uniquely identifies each record of the table. Each table should contain a primary key and can't contain more than one primary key.
Ex. 
```sql
CREATE TABLE Employees ( 
	EmployeeID INT NOT NULL, 
	FirstName VARCHAR(50), 
	LastName VARCHAR(50), 
	PRIMARY KEY (EmployeeID) 
);
```
`EmployeeID` is the primary key, which means every employee will have a unique `EmployeeID`

##### What is a Foreign Key? 
- A column (or set of columns) that create a relationship between two tables. 
- The purpose of foreign keys is to keep connected various tables of a database
- It refers to the **primary key** (or a unique key) in another table. 
- A foreign key ensures that the values in a column (or combination of columns) in one table correspond to the values in the primary key column of another table. 
Ex. 
```sql
CREATE TABLE Customers ( 
	CustomerID INT NOT NULL, 
	FirstName VARCHAR(50), 
	LastName VARCHAR(50), 
	PRIMARY KEY (CustomerID) 
); 

CREATE TABLE Orders ( 
	OrderID INT NOT NULL, 
	OrderDate DATE, 
	CustomerID INT, 
	PRIMARY KEY (OrderID), 
	FOREIGN KEY (CustomerID) 
	REFERENCES Customers(CustomerID) 
);
```

In this example, `CustomerID` in the `Orders` table is a foreign key that references the `CustomerID` column in the `Customers` table. This ensures that each order is associated with an existing customer.

##### What is a Unique Key?
- Constraint that ensures all the values in a column (or combination of columns) are unique across all tables. 
- A unique key can allow `NULL` values (but only one `NULL` per column in most database systems)
Ex. 

```sql
CREATE TABLE Employees ( 
	EmployeeID INT NOT NULL, 
	Email VARCHAR(100), 
	FirstName VARCHAR(50), 
	LastName VARCHAR(50), 
	PRIMARY KEY (EmployeeID), 
	UNIQUE (Email) 
);
```

In this example, the `Email` column is a unique key. This means no two employees can have the same email address, though the `Email` column could contain `NULL` if no email is provided, but only once.

