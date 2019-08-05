<p> CODE Creating Your Own Tables </p>

`CREATE TABLE tablename
  (
    column_name data_type,
    column_name data_type
  );`
  
`CREATE TABLE cats
  (
    name VARCHAR(100),
    age INT
  );`
  
<hr>

<p> CODE How Do We Know It Worked </p>

`SHOW TABLES;`

`SHOW COLUMNS FROM tablename;`

`DESC tablename;`

**`SHOW COLUMNS FROM cats;`**

**`DESC cats;`**

<hr>

<p> Inserting Data </p>
  
`INSERT INTO table_name(column_name) VALUES (data); ` 
  
**` INSERT INTO cats(name, age) VALUES ('Jetson', 7); `**
  
  <hr>
  
  <p> Super Quick Intro To SELECT </p>

`SELECT * FROM cats;` 

  <hr>
  
  <p> CODE Multiple Insert </p>

`INSERT INTO table_name 
            (column_name, column_name) 
VALUES      (value, value), 
            (value, value), 
            (value, value);`

**`INSERT INTO cats (name, age) VALUES ('zeena', 12), ('google', 10), ('cofee', 58);`**


  <hr>
  
NULL and NOT NULL Code
Try inserting a cat without an age:

`INSERT INTO cats(name) VALUES('Alabama');` 

`SELECT * FROM cats;` 

Try inserting a nameless and ageless cat:

`INSERT INTO cats() VALUES();` 


Define a new cats2 table with NOT NULL constraints:

`CREATE TABLE cats2
  (
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL
  );`
  
`DESC cats2;` 

Now try inserting an ageless cat:

`INSERT INTO cats2(name) VALUES('Texas');` 

View the new warnings:

SHOW WARNINGS; 

`SELECT * FROM cats2;` 

Do the same for a nameless cat:

`INSERT INTO cats2(age) VALUES(7);` 

SHOW WARNINGS; 









