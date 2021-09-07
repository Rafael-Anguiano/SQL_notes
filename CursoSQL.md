# SQL 

## Databases
```sql
CREATE DATABASE database_name;	##Create a database
USE database_name;	## Selecting a database
SHOW DATABASES;		## Show databases
DROP database_name;	## Removing a database
SELECT database();	## Check selected databases
```
---

## Tables (names in plural)
```sql
CREATE TABLE table_name
 (
	column_name data_type,
 	column_name data_type
 );

SHOW TABLES;
SHOW COLUMNS FROM table_name;	## Similar to...
DESCRIBE table_name;	## DESC table_name;
DROP TABLE table_name;	## Deleting tables
```

### Bakery Challenge
```sql
CREATE DATABASE bakery;
USE pastries;
CREATE TABLE pastries (name varchar(50), quantity int);
DESC pastries;
DROP TABLE pastries;
```

---

## Adding Data to Tables

### Simple Insert
```sql
INSERT INTO table_name ( column_name1, column_name2) 
VALUES("Value1", "Value2");	## Adding data		
```
> + Value 1 match with column_name1, Value2 match with column_name2
> + Values must be allowed by the datatype of the column

```sql
SELECT * FROM table_name;	## Visualizing information from a table
```
### Multiple Insert 

```sql
INSERT INTO table_name ( column_name1, column_name2) 
VALUES("Value1.1", "Value1.2"), ("Value2.1","Value2.2"), ("Value3.1","Value3.2");	## Adding multiple data		
```
### Insert Challenge
```sql
CREATE DATABASE InsertData;
USE InsertData;
CREATE TABLE people (first_name varchar(50), last_name varchar(50), age int);
INSERT INTO people (first_name, last_name, age) VALUES ("Tina", "Belcher", 13);
INSERT INTO people (last_name, age, first_name) VALUES ("Belcher", 42, "Bob");
INSERT INTO people (first_name, last_name, age) VALUES("Linda", "Belcher", 45), ("Philip","Frond", 38), ("Calvin", "Fischoeder", 70);
DROP TABLE people;
```

### Warnings
```sql
SHOW WARNINGS; 
```

### NULL or NOT NULL
If NULL is defined as "NO", the column is required and can´t be null.
```sql
CREATE TABLE table_name
 (
	column_name data_type NOT NULL,
 	column_name data_type NOT NULL
 ); 
```

### Default Values

```sql
CREATE TABLE table_name
(
	column_name data_type DEFAULT 'Value',
 	column_name data_type DEFAULT 10
);
```

```sql
CREATE TABLE table_name
(
	column_name data_type NOT NULL DEFAULT 'Value',
 	column_name data_type DEFAULT 10
);
```

### Primary Key
```sql
CREATE TABLE table_name
(
	column_id INT NOT NULL, 
	column_name data_type NOT NULL DEFAULT 'Value',
 	column_name data_type DEFAULT 10,
	PRIMARY KEY (column_id)
);
```
```sql
CREATE TABLE table_name
(
	column_id INT NOT NULL AUTO_INCREMENT, 
	column_name data_type NOT NULL DEFAULT 'Value',
 	column_name data_type DEFAULT 10,
	PRIMARY KEY (column_id)
);
```
---

## CRUD
### Create

```sql
CREATE DATABASE database_name;	##Create a database
USE database_name;	## Selecting a database
CREATE TABLE table_name
(
	column_id INT NOT NULL AUTO_INCREMENT, 
	column_name data_type NOT NULL DEFAULT 'Value',
 	column_name data_type DEFAULT 10,
	PRIMARY KEY (column_id)
);
```

### Read
```sql
SELECT * FROM table_name; ## Asking for ALL columns in the table
SELECT name FROM table_name; ## Asking for column name in the table
SELECT name, age FROM table_name; ## Asking for columns name and age
## It will be showed in the same order you are asking 
```
#### Where
```sql
SELECT * FROM table_name WHERE age=4; 
```
> Asking for ALL columns in the table where age is equal to 4, you can also use name='VALUE', does not matter capital letters

#### Aliases
```sql
SELECT first_name AS name, last_name FROM table_name; 
```

### Update
> Always try to select before to try updating data.
```sql
UPDATE table_name SET column_name='New Value' WHERE searched_field='Searched Value';
```

### Delete
> Always try to select before to try deleting data.
```sql
DELETE FROM table_name WHERE age=4; 
DELETE FROM table_name; ## Delete the entries of a table without deleting the table
```







