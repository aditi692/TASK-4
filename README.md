# TASK-4
# Aggregate Functions and Grouping

## 🎯 Objective
Learn how to use SQL to **summarize and analyze** data using functions like:
- `SUM()` → total
- `AVG()` → average
- `COUNT()` → number of rows
- `GROUP BY` → to group data
- `HAVING` → to filter grouped data

## 🛒 Sample Table: Orders

This is the table we used:

| order_id | customer_id | order_date | total_amount | status     |
|----------|-------------|------------|--------------|------------|
| 101      | 1           | 2025-06-01 | 1200.50      | Delivered  |
| 102      | 2           | 2025-06-05 | 0.00         | Pending    |
| 103      | 3           | 2025-06-08 | 700.00       | Delivered  |
| 104      | 1           | 2025-06-10 | 500.00       | Cancelled  |


## 🧪 SQL Queries Used

```sql
SELECT SUM(total_amount) AS total_sales FROM Orders;

SELECT AVG(total_amount) AS avg_order_value FROM Orders;

SELECT COUNT(*) AS total_orders FROM Orders;

SELECT status, COUNT(*) AS order_count
FROM Orders
GROUP BY status;

SELECT customer_id, AVG(total_amount) AS avg_spent
FROM Orders
GROUP BY customer_id;

SELECT customer_id, SUM(total_amount) AS total_spent
FROM Orders
GROUP BY customer_id
HAVING total_spent > 1000;

SELECT customer_id, MAX(total_amount) AS highest_order
FROM Orders
GROUP BY customer_id;

SELECT COUNT(DISTINCT customer_id) AS unique_customers FROM Orders;

SELECT ROUND(AVG(total_amount), 2) AS rounded_avg FROM Orders;
