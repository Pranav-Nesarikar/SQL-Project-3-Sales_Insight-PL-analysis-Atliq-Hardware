# SQL-Project-3-Sales_Insight-PL-analysis-Atliq-Hardware
LIVE DASHBOARD LINK --
https://www.novypro.com/project/sales-insights-dashboard-for-atliq-hardware-[retail]--power-bi

The sales insights dashboard was built using the dataset provided Codebasics Youtube channel. It contained the sales data of Atliq hardware from 2017 to 2020. It consisted of 1 fact table and 4 dimension tables. The data source was in MySQL database. 

The color scheme of the dashboard is inspired from the AtliQ logo. It measures the 2 main KPIs for hardware sales namely the Revenue and Sales Quantity across various dimensions.
### Data Analysis Using SQL

1. Show all customer records

    SELECT * FROM customers;


2. Show total number of customers

    SELECT count(*) FROM customers;


3. Show transactions for Chennai market (market code for chennai is Mark001

    SELECT * FROM transactions where market_code='Mark001';


4. Show distinct product codes that were sold in chennai

    SELECT distinct product_code FROM transactions where market_code='Mark001';


5. Show transactions where currency is US dollars

    SELECT * from transactions where currency="USD"


6. Show transactions in 2020 join by date table

    SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;


7. Show total revenue in year 2020,

SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";

	
8. Show total revenue in year 2020, January Month,

SELECT SUM(transactions.sales_amount) FROM transactions 
INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

9. Show total revenue in year 2020 in Chennai

    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";

