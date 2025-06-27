# 📚 Bookstore Sales Analysis (SQL Project)

## Overview

This SQL project simulates a **bookstore management system**, including customers, books, and orders. It focuses on data modeling, importing data, and performing various SQL queries to derive insights such as customer activity, inventory status, and genre-based sales.

## Database Structure

Three primary tables are created:

### 📘 `Books`
Stores book-related data.

- `Book_ID` (Primary Key)
- `Title`
- `Author`
- `Genre`
- `Published_Year`
- `Price`
- `Stock`

### 👥 `Customers`
Stores customer information.

- `Customer_ID` (Primary Key)
- `Name`
- `Email`
- `Phone`
- `City`
- `Country`

### 🛒 `Orders`
Stores order transaction details.

- `Order_ID` (Primary Key)
- `Customer_ID` (Foreign Key → Customers)
- `Book_ID` (Foreign Key → Books)
- `Order_Date`
- `Quantity`
- `Total_Amount`

## Data Import

Data is imported using the `COPY` command from CSV files:

```sql
COPY Books(...) FROM '.../Books.csv' CSV HEADER;
COPY Customers(...) FROM '.../Customers.csv' CSV HEADER;
COPY Orders(...) FROM '.../Orders.csv' CSV HEADER;
```

## Key Queries & Insights

- 📚 **Book Filtering**:
  - Books in the `Fiction` genre
  - Books published after 1958
  - Books with the highest and lowest (non-zero) stock
  - Top 3 most expensive books in `Fantasy` genre

- 🌍 **Customer Insights**:
  - Customers from `Canada`
  - Customers who placed more than 1 order
  - Top spending customer by total purchase value
  - Cities where individual order totals exceeded $30

- 📦 **Order Analytics**:
  - Orders between specific dates
  - Orders with `Quantity > 1` and `Total_Amount > $20`
  - Total revenue from all orders
  - Most frequently ordered book
  - Quantity of books sold per author and per genre

- 📊 **Inventory Tracking**:
  - Total stock available across all books
  - Remaining quantity after subtracting ordered amounts (computed using `LEFT JOIN` and `COALESCE`)

## Advanced Concepts Used

- `GROUP BY` and `HAVING`
- Subqueries (e.g., max price, min stock)
- Aggregate functions: `SUM`, `AVG`, `COUNT`, `ROUND`
- Joins: `INNER JOIN`, `LEFT JOIN`
- `DISTINCT`, `ORDER BY`, `LIMIT`
- Data type conversions and validations

## How to Use

1. Execute the `CREATE TABLE` statements to build your schema.
2. Use the `COPY` commands to load your data from CSV files.
3. Run the provided SQL queries in your PostgreSQL environment.
4. Modify or extend queries to explore deeper insights.

## Conclusion

This project demonstrates how to use SQL effectively for data modeling, cleaning, and analytical reporting in a real-world retail/bookstore scenario. It includes inventory tracking, customer behavior analysis, and sales performance measurement using only SQL queries.

