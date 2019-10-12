## Introduction to CRUD

`INSERT INTO cats(name, age) VALUES(‘Taco’, 14); `

<hr>

##Preparing Our Data
 
<p> Let's drop the existing cats table:  </p>

`DROP TABLE cats;` 

<p> Recreate a new cats table:  </p>


`CREATE TABLE cats 
  ( 
     cat_id INT NOT NULL AUTO_INCREMENT, 
     name   VARCHAR(100), 
     breed  VARCHAR(100), 
     age    INT, 
     PRIMARY KEY (cat_id) 
  ); `
  
  
`DESC cats;` 



<p> And finally insert some new cats:  </p>

`INSERT INTO cats(name, breed, age) 
VALUES ('Ringo', 'Tabby', 4),
       ('Cindy', 'Maine Coon', 10),
       ('Dumbledore', 'Maine Coon', 11),
       ('Egg', 'Persian', 4),
       ('Misty', 'Tabby', 13),
       ('George Michael', 'Ragdoll', 9),
       ('Jackson', 'Sphynx', 7);`
       
       
<hr>       
       
## Various Simple SELECT statements

`SELECT * FROM cats;` 

`SELECT name FROM cats;` 

`SELECT age FROM cats;` 

`SELECT cat_id FROM cats;` 

`SELECT name, age FROM cats;` 

`SELECT cat_id, name, age FROM cats;` 

`SELECT age, breed, name, cat_id FROM cats;` 

`SELECT cat_id, name, age, breed FROM cats;`        
       
 <hr>      
       
## Introduction to WHERE

<p>   Select by age:  </p>

`SELECT * FROM cats WHERE age=4;` 
 
 <p>  Select by name:  </p>

`SELECT * FROM cats WHERE name='Egg';` 
 
 <p>  Notice how it deals with case: </p>
 
`SELECT * FROM cats WHERE name='egG';`       
       
<hr>       
       
## Introduction to Aliases

`SELECT cat_id AS id, name FROM cats;`

`SELECT name AS 'cat name', breed AS 'kitty breed' FROM cats;`

`DESC cats;`

<hr>

## Updating Data

<p> Change shorthair cats to tabby:   </p>

`UPDATE cats SET breed='Shorthair' WHERE breed='Tabby';` 

<p> Another update:   </p>

`UPDATE cats SET age=14 WHERE name='Misty';` 

<hr>

## DELETING DATA
 
`DELETE FROM cats WHERE name='Egg';`

`SELECT * FROM cats;`

`SELECT * FROM cats WHERE name='egg';`

`DELETE FROM cats WHERE name='egg';`

`SELECT * FROM cats;`

`DELETE FROM cats;`

<hr>




