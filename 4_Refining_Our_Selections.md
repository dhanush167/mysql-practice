
## Seed Data Adding A Couple New Books


`INSERT INTO books
    (title, author_fname, author_lname, released_year, stock_quantity, pages)
    VALUES ('10% Happier', 'Dan', 'Harris', 2014, 29, 256), 
           ('fake_book', 'Freida', 'Harris', 2001, 287, 428),
           ('Lincoln In The Bardo', 'George', 'Saunders', 2017, 1000, 367);`


`SELECT title FROM books;`

<hr>

## Using DISTINCT

`SELECT author_lname FROM books;`

`SELECT DISTINCT author_lname FROM books;`

`SELECT author_fname, author_lname FROM books;`

`SELECT DISTINCT CONCAT(author_fname,' ', author_lname) FROM books;`

`SELECT DISTINCT author_fname, author_lname FROM books;`


<hr>



## Sorting Data with ORDER BY

`SELECT author_lname FROM books;`

`SELECT author_lname FROM books ORDER BY author_lname;`

`SELECT title FROM books;`

`SELECT title FROM books ORDER BY title;`

`SELECT author_lname FROM books ORDER BY author_lname DESC;`

`SELECT released_year FROM books;`

`SELECT released_year FROM books ORDER BY released_year;`

`SELECT released_year FROM books ORDER BY released_year DESC;`

`SELECT released_year FROM books ORDER BY released_year ASC;`

`SELECT title, released_year, pages FROM books ORDER BY released_year;`




`SELECT title, pages FROM books ORDER BY released_year;`



`SELECT title, author_fname, author_lname` 


`FROM books ORDER BY 2;`

`SELECT title, author_fname, author_lname` 


`FROM books ORDER BY 3;`


`SELECT title, author_fname, author_lname` 


`FROM books ORDER BY 1;`


`SELECT title, author_fname, author_lname` 


`FROM books ORDER BY 1 DESC;`

`SELECT author_lname, title`


`FROM books ORDER BY 2;`


`SELECT author_fname, author_lname FROM books` 


`ORDER BY author_lname, author_fname;`

<hr>

## Using LIMIT


`SELECT title FROM books LIMIT 3;`

`SELECT title FROM books LIMIT 1;`

`SELECT title FROM books LIMIT 10;`

`SELECT * FROM books LIMIT 1;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 5;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 1;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 14;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 0,5;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 0,3;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 1,3;`

`SELECT title, released_year FROM books 
ORDER BY released_year DESC LIMIT 10,1;`

`SELECT * FROM tbl LIMIT 95,18446744073709551615;`

`SELECT title FROM books LIMIT 5;`

`SELECT title FROM books LIMIT 5, 123219476457;`

`SELECT title FROM books LIMIT 5, 50;`


<hr>


## Better Searches with LIKE



`SELECT title, author_fname FROM books WHERE author_fname LIKE '%da%';`

`SELECT title, author_fname FROM books WHERE author_fname LIKE 'da%';`

`SELECT title FROM books WHERE  title LIKE 'the';`

`SELECT title FROM books WHERE  title LIKE '%the';`

`SELECT title FROM books WHERE title LIKE '%the%';`


<hr>


## LIKE Part 2 More Wildcards

`SELECT title, stock_quantity FROM books;`

`SELECT title, stock_quantity FROM books WHERE stock_quantity LIKE '____';`

`SELECT title, stock_quantity FROM books WHERE stock_quantity LIKE '__';`

`(235)234-0987 LIKE '(___)___-____'`

`SELECT title FROM books;`

`SELECT title FROM books WHERE title LIKE '%\%%'`

`SELECT title FROM books WHERE title LIKE '%\_%'`

<hr>


<hr>

## How To Find Duplicate Values in MySQL


**Setting up a sample table**

`CREATE TABLE contacts (
    id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(255) NOT NULL
);`


`INSERT INTO contacts (first_name,last_name,email) 
VALUES ('Carine ','Schmitt','carine.schmitt@verizon.net'),
       ('Jean','King','jean.king@me.com'),
       ('Peter','Ferguson','peter.ferguson@google.com'),
       ('Janine ','Labrune','janine.labrune@aol.com'),
       ('Jonas ','Bergulfsen','jonas.bergulfsen@mac.com'),
       ('Janine ','Labrune','janine.labrune@aol.com'),
       ('Susan','Nelson','susan.nelson@comcast.net'),
       ('Zbyszek ','Piestrzeniewicz','zbyszek.piestrzeniewicz@att.net'),
       ('Roland','Keitel','roland.keitel@yahoo.com'),
       ('Julie','Murphy','julie.murphy@yahoo.com'),
       ('Kwai','Lee','kwai.lee@google.com'),
       ('Jean','King','jean.king@me.com'),
       ('Susan','Nelson','susan.nelson@comcast.net'),
       ('Roland','Keitel','roland.keitel@yahoo.com');`

<p>  Third, query data from the contacts table: </p>

`SELECT * FROM contacts ORDER BY email;`

<p>  Find duplicate values in one column  </p>



`SELECT 
    col, 
    COUNT(col)
FROM
    table_name
GROUP BY col
HAVING COUNT(col) > 1;`


<p> By using this query template, you can to find rows that have duplicate emails in the contacts table as follows:  </p>


`SELECT 
    email, 
    COUNT(email)
FROM
    contacts
GROUP BY email
HAVING COUNT(email) > 1;`
























