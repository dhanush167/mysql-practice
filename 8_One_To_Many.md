## Working With Foreign Keys

<p> -- Creating the customers and orders tables  </p>




`CREATE TABLE customers(
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(100),
    last_name VARCHAR(100),
    email VARCHAR(100)
);`


`CREATE TABLE orders(
    id INT AUTO_INCREMENT PRIMARY KEY,
    order_date DATE,
    amount DECIMAL(8,2),
    customer_id INT,
    FOREIGN KEY(customer_id) REFERENCES customers(id)
);`


<p> -- Inserting some customers and orders  </p>


`INSERT INTO customers (first_name, last_name, email) 
VALUES ('Boy', 'George', 'george@gmail.com'),
       ('George', 'Michael', 'gm@gmail.com'),
       ('David', 'Bowie', 'david@gmail.com'),
       ('Blue', 'Steele', 'blue@gmail.com'),
       ('Bette', 'Davis', 'bette@aol.com');`
       
       
      
       
`INSERT INTO orders (order_date, amount, customer_id)
VALUES ('2016/02/10', 99.99, 1),
       ('2017/11/11', 35.50, 1),
       ('2014/12/12', 800.67, 2),
       ('2015/01/03', 12.50, 2),
       ('1999/04/11', 450.25, 5);`
       

<p>  -- This INSERT fails because of our fk constraint.  No user with id: 98  </p>


`INSERT INTO orders (order_date, amount, customer_id)
VALUES ('2016/06/06', 33.67, 98);`


<hr>

## Cross Joins

<p>  -- Finding Orders Placed By George: 2 Step Process </p>



`SELECT id FROM customers WHERE last_name='George';
SELECT * FROM orders WHERE customer_id = 1;`

<p> -- Finding Orders Placed By George: Using a subquery   </p>


`SELECT * FROM orders WHERE customer_id =
    (
        SELECT id FROM customers
        WHERE last_name='George'
    );`
    
<p>  -- Cross Join Craziness  </p>    


`SELECT * FROM customers, orders;` 



<hr>


## Inner Joins

<p>  -- IMPLICIT INNER JOIN  </p>

`SELECT * FROM customers, orders 
WHERE customers.id = orders.customer_id;`

<p>-- IMPLICIT INNER JOIN   </p>


`SELECT first_name, last_name, order_date, amount
FROM customers, orders 
    WHERE customers.id = orders.customer_id;`
    
<p> -- EXPLICIT INNER JOINS  </p>



`SELECT * FROM customers
JOIN orders
    ON customers.id = orders.customer_id;`
    
    
    
    
`SELECT first_name, last_name, order_date, amount 
FROM customers
JOIN orders
    ON customers.id = orders.customer_id;`
    
    
    
    
    
`SELECT *
FROM orders
JOIN customers
    ON customers.id = orders.customer_id;`
    
    
   

<p> -- ARBITRARY JOIN - meaningless, but still possible   </p>


`SELECT * FROM customers
JOIN orders ON customers.id = orders.id;`


<hr>
















