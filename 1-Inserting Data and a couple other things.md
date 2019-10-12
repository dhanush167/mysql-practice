
## Inserting Data

The "formula":

`INSERT INTO table_name(column_name) VALUES (data);`

For example:

`INSERT INTO cats(name, age) VALUES ('Jetson', 7);`

 Super Quick Intro To SELECT

`SELECT * FROM cats; `

<hr>

## Multiple Insert

`INSERT INTO table_name 
            (column_name, column_name) 
VALUES      (value, value), 
            (value, value), 
            (value, value);`

<hr>

## INSERT Challenge  Code

`CREATE TABLE people
  (
    first_name VARCHAR(20),
    last_name VARCHAR(20),
    age INT
  );`
  
  
`INSERT INTO people(first_name, last_name, age)`

`VALUES ('Tina', 'Belcher', 13);`

`INSERT INTO people(age, last_name, first_name)`

`VALUES (42, 'Belcher', 'Bob');`

`INSERT INTO people(first_name, last_name, age)`

`VALUES('Linda', 'Belcher', 45)
  ,('Phillip', 'Frond', 38)
  ,('Calvin', 'Fischoeder', 70);
DROP TABLE people; `

`SELECT * FROM people; `

`show tables; `

## MySQL Warnings Code

`DESC cats;`

<p> Try Inserting a cat with a super long name:  </p>


`INSERT INTO cats(name, age)
VALUES('This is some text blah blah blah blah blah text text text something about cats lalalalal meowwwwwwwwwww', 10);`
<p>  Then view the warning:  </p>

`SHOW WARNINGS;` 

<p>  Try inserting a cat with incorrect data types: </p>

`INSERT INTO cats(name, age) VALUES('Lima', 'dsfasdfdas');`

Then view the warning:

`SHOW WARNINGS;` 

<hr>

## NULL and NOT NULL Code

<p> Try inserting a cat without an age:  </p>


`INSERT INTO cats(name) VALUES('Alabama');`

`SELECT * FROM cats;` 

<p>   
Try inserting a nameless and ageless cat:
</p>


`INSERT INTO cats() VALUES(); `

<p> 
  Define a new cats2 table with NOT NULL constraints:
</p>


`CREATE TABLE cats2
  (
    name VARCHAR(100) NOT NULL,
    age INT NOT NULL
  );`
  
  
`DESC cats2;` 

<p>  Now try inserting an ageless cat:  </p>


`INSERT INTO cats2(name) VALUES('Texas');`

<p> 
   View the new warnings:
</p>

`SHOW WARNINGS;` 

`SELECT * FROM cats2;` 

<p>  
 Do the same for a nameless cat:
</p>


`INSERT INTO cats2(age) VALUES(7);` 

`SHOW WARNINGS;` 

<hr>


## Setting Default Values

<p>  Define a table with a DEFAULT name specified: </p>


`CREATE TABLE cats3
    (
      name VARCHAR(20) DEFAULT 'no name provided',
      age INT DEFAULT 99
    );`
    
  
  <p> Notice the change when you describe the table:  </p>


`DESC cats3;` 

<p>  Insert a cat without a name: </p>


`INSERT INTO cats3(age) VALUES(13); `


<p>  Or a nameless, ageless cat: </p>


`INSERT INTO cats3() VALUES();` 

<p> Combine NOT NULL and DEFAULT:  </p>

`CREATE TABLE cats4
  (
    name VARCHAR(20) NOT NULL DEFAULT ‘unnamed’,
    age INT NOT NULL DEFAULT 99
  );`
  
<p> Notice The Difference:  </p>

`INSERT INTO cats() VALUES();`

`SELECT * FROM cats;`

`INSERT INTO cats3() VALUES();`

`SELECT * FROM cats3;`

`INSERT INTO cats3(name, age) VALUES('Montana', NULL);`

`SELECT * FROM cats3;`

`INSERT INTO cats4(name, age) VALUES('Cali', NULL);`

<hr>

## Primary Keys
 
 <p>   Define a table with a PRIMARY KEY constraint: </p>


`CREATE TABLE unique_cats
  (
    cat_id INT NOT NULL,
    name VARCHAR(100),
    age INT,
    PRIMARY KEY (cat_id)
  );`
  
  
`DESC unique_cats;` 

<p> Insert some new cats:  </p>


`INSERT INTO unique_cats(cat_id, name, age) VALUES(1, 'Fred', 23);`

`INSERT INTO unique_cats(cat_id, name, age) VALUES(2, 'Louise', 3);`

`INSERT INTO unique_cats(cat_id, name, age) VALUES(1, 'James', 3);`

<p> Notice what happens:  </p>

`SELECT * FROM unique_cats;` 

<p>  Adding in AUTO_INCREMENT:  </p>


`CREATE TABLE unique_cats2 (
    cat_id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    PRIMARY KEY (cat_id)
);`

<p> INSERT a couple new cats:  </p>

`INSERT INTO unique_cats2(name, age) VALUES('Skippy', 4);`

`INSERT INTO unique_cats2(name, age) VALUES('Jiff', 3);`

`INSERT INTO unique_cats2(name, age) VALUES('Jiff', 3);`

`INSERT INTO unique_cats2(name, age) VALUES('Jiff', 3);`

`INSERT INTO unique_cats2(name, age) VALUES('Skippy', 4);`

<p> Notice the difference:  </p>


`SELECT * FROM unique_cats2;`









