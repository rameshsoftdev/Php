# What is stored procedure in mysql with an example?

A stored procedure is a pre-defined set of SQL statements that can be called to perform specific tasks. It can accept input parameters and return multiple values. For example, a stored procedure may be used to insert, update, or delete data from a database table.

Example:

CREATE PROCEDURE update_customer_address
(
IN customer_id INT,
IN new_address VARCHAR(100)
)
BEGIN
UPDATE customers SET address = new_address WHERE customer_id = customer_id;
END;

example for Out Parameter

CREATE PROCEDURE get_customer_info
(
IN customer_id INT,
OUT customer_name VARCHAR(50)
)
BEGIN
SELECT name INTO customer_name FROM customers WHERE customer_id = customer_id;
END;
