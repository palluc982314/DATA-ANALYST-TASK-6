# DATA-ANALYST-TASK-6
Sales Trend Analysis Using Aggregations
Sales Trend Analysis Using SQLite
This project demonstrates how to analyze monthly revenue and order volume from an online sales dataset using SQLite. The dataset contains orders with order_id, order_date, amount, and product_id fields.

Project Overview
The objective is to:

Analyze monthly revenue and order volume.

Use SQL aggregate functions such as SUM() and COUNT().

Group the results by year and month.

Use SQLite for database management and querying.

Dataset
The dataset used in this project consists of the following columns:

order_id: Unique identifier for each order.

order_date: Date when the order was placed.

amount: Total amount for the order.

product_id: ID of the product purchased.

Sample Data:

order_id	order_date	amount	product_id
1	2024-01-05	200.00	1
2	2024-01-10	300.00	2
3	2024-02-15	450.00	1
4	2024-02-20	600.00	3
5	2024-03-10	400.00	2
6	2024-03-20	500.00	3
7	2024-04-05	750.00	4
8	2024-04-10	850.00	2
9	2024-05-15	950.00	1
10	2024-06-01	1200.00	5
Project Setup
Requirements
SQLite: SQLite is used to manage and query the database.

CSV file: The dataset is in CSV format, ready to be imported into SQLite.

Steps to Run the Project
Create a new SQLite database:

Open sqliteonline.com or any SQLite client of your choice.

Import the CSV file:

Click the Import button and upload the online_sales.csv file.

Create the table:

Ensure the table online_sales is created with the following columns:

order_id: INTEGER

order_date: TEXT

amount: REAL

product_id: INTEGER

Run the Sales Trend Analysis Query:

Once the table is imported, run the following SQL query to analyze monthly revenue and order volume:

sql
Copy
Edit
SELECT 
    strftime('%Y', order_date) AS year,
    strftime('%m', order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_order_volume
FROM 
    online_sales
GROUP BY 
    year,
    month
ORDER BY 
    year ASC,
    month ASC;
Output
The output will provide the total revenue and total order volume for each month and year.

Example:


year	month	total_revenue	total_order_volume
2024	01	500.00	2
2024	02	1050.00	2
2024	03	900.00	2
2024	04	1600.00	2
2024	05	950.00	1
2024	06	1200.00	1
