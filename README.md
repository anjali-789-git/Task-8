

Stored Procedure

A stored procedure is a precompiled block of SQL statements stored in the database that can be executed by calling its name.
It can accept parameters (input, output, or both).
It performs one or more tasks (e.g., insert, update, select).
It does not necessarily return a value, but can return multiple result sets.
Useful for reusing logic, reducing code repetition, and improving performance.


Example usage:

CALL ProcedureName(parameter_values);


---

Stored Function

A stored function is a database object that performs a calculation or operation and always returns a single value.
It accepts input parameters only.
Must contain a RETURN statement to give back a value.
Often used in SELECT statements, WHERE clauses, or other SQL expressions.


Example usage:

SELECT FunctionName(parameter_values);


---

Key Difference:

Procedure: Performs an action, may return data, but not necessarily a single value.

Function: Always returns exactly one value, usually used within SQL queries.



---

1. Stored Procedure – GetOrdersByCustomer

Purpose:
To retrieve all orders placed by a specific customer.

How it works:

Accepts a Customer ID as an input parameter (cust_id).

Uses a SELECT query to fetch all matching orders from the Orders table.

Returns OrderID, OrderDate, and TotalAmount for that customer.


When to use:
If you want to quickly see all orders for a customer without writing the same SELECT query repeatedly.

Example:
CALL GetOrdersByCustomer(1); → Shows all orders by the customer with ID 1.



---

2. Stored Function – GetOrderTotal

Purpose:
To calculate the total value of a specific order.

How it works:

Accepts an Order ID as input (order_id).

Uses SUM(Quantity * Price) on the OrderDetails table to find the total cost.

Returns the calculated total as a decimal value.


When to use:
If you want to get the value of an order in calculations, reports, or invoices without manually summing prices.

Example:
SELECT GetOrderTotal(1); → Returns the total cost of order with ID 1.



 
