# What is Triggers in mysql with an example?

Triggers are special stored procedures that are executed when certain events occur in the database. They are used to enforce business rules, maintain data integrity, and automatically react to changes in the database.

For example, a trigger can be used to automatically update the balance of an account when a deposit or withdrawal is made. When a row is inserted into the ‘transactions’ table, the trigger will execute and update the balance field in the ‘accounts’ table.

``
CREATE TRIGGER update_balance 
AFTER INSERT ON transactions
FOR EACH ROW
BEGIN
UPDATE accounts
SET balance = balance + NEW.amount
WHERE account_id = NEW.account_id;
END;
``
