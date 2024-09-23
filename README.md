## Description

Exercising subqeury factoring which allows to nest SQL queries within a new one to reduce repetition and simplify complex SQL statements.

This syntax is the following:

```sql
WITH TemporaryTableName AS (
    -- PUT HERE A VALID QUERY LIKE:
    SELECT
      OrderID,
      ProductID,
      UnitPrice * Quantity ProductAmount
    FROM OrderDetails
)
SELECT
  OrderID,
  ProductID,
  ProductAmount
FROM TemporaryTableName

```
## Data
Using `ecommerce.sqlite` file in `data` directory. 

### Average per customer

- Implemented `get_average_purchase` to get the average amount spent per order for each customer, ordered by `CustomerID`.
- This function returns list of tuples like (`CustomerID`, `AverageOrderedAmount`).

### General average

- Implemented `get_general_avg_order` to get the average amount spent per order
- This function returns a simple `float`.

### Best customers

Finding the customers who spent more than the average - that is, their average amount spent per order is greater than the general average amount spent per order.

- Implementing `best_customers` to get the customers who have an average order greater than the general average order, sorted by descending average ordered amount.
- This function returns a list of tuples like (`CustomerID`, `AverageOrderedAmount`).

### Top ordered products

- Implementing `top_ordered_product_per_customer` to get the list of the top ordered product (in terms of amount of money not quantity) by each customer, based on the total ordered amount in **USD** and sorted decreasingly.
- This function returns a list of tuples like (`CustomerID`, `ProductID`, `OrderedAmount`).

### Average number of days between orders

- Implementing `average_number_of_days_between_orders` to get the average number of days between two consecutive orders of the same customer.
- This function returns a simple `int`.
