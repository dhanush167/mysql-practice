```

mysql -u root -p

How to import sql file in MySQL on Linux and Windows

upload sql file to linux server 

source /var/www/html/vpsfinall/db/brestolddb.sql


```


## Creating Databases Code

Start the CLI:

mysql-ctl cli; 

List available databases:

show databases; 

The general command for creating a database:

`CREATE DATABASE database_name; `

A specific example:

`CREATE DATABASE soap_store; `


<hr>

## To drop a database:

`DROP DATABASE database_name; `

**For Example:**

`DROP DATABASE hello_world_db; `

Remember to be careful with this command! Once you drop a database, it's gone!

<hr>


## CODE Using Databases

`USE <database name>;`

**-- example:**

USE dog_walking_app;

SELECT database();

<hr>

## CODE Creating Your Own Tables


`CREATE TABLE tablename
  (
    column_name data_type,
    column_name data_type
  );
`

`CREATE TABLE cats
  (
    name VARCHAR(100),
    age INT
  );`

> 1050 - Table 'cats' already exists
> Time: 0.001s

<hr>

## How Do We Know It Worked

`SHOW TABLES;`

> OK
> Time: 0.001s
>
>cats
>
>cats2
>
>users_image


`SHOW COLUMNS FROM tablename;`

> OK
> Time: 0.001s
>
>name
 age
>
>varchar(100)
 int(11)
>



`DESC tablename;`

> 1146 - Table 'test.tablename' doesn't exist
> Time: 0.001s


<hr>

## Dropping Tables


`DROP TABLE <tablename>; `

A specific example:

`DROP TABLE cats; `

Be careful with this command!











