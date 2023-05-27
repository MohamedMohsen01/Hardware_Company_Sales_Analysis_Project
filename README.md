# Software_Company_Sales_Analysis

# Data Analysis Using SQL

--looking for customer details
SELECT * FROM customers;

--looking for transaction details
SELECT * FROM transactions;

--looking for product details
SELECT * FROM products;

--looking for market details
SELECT * FROM markets;

--looking for time details
SELECT * FROM date;

--total number of transactions taken place
SELECT count(*) FROM transactions;

--looking for transactions with particular currency
SELECT * FROM transactions WHERE currency = 'USD';

--looking for transactions from specific market code
SELECT * FROM transactions WHERE market_code = 'Mark001';
SELECT count(*) FROM transactions WHERE market_code = 'Mark001';

--looking for transactions that took place in particular year or month
SELECT * FROM date;

SELECT transactions.*, date.* 
FROM transactions 
	INNER JOIN date 
		ON transactions.order_date = date.date

SELECT transactions.*, date.* 
FROM transactions 
	INNER JOIN date 
		ON transactions.order_date = date.date WHERE date.year = 2020;

SELECT SUM(transactions.sales_amount) 
FROM transactions 
	INNER JOIN date 
		ON transactions.order_date = date.date 
		WHERE (date.year=2020) AND (date.month_name = 'January');

--total revenue earned in a particular year
SELECT SUM(sales_amount) 
FROM transactions 
	INNER JOIN date 
		ON transactions.order_date = date.date 
			WHERE date.year = 2020;
			

--finding the average of profit_margin
SELECT AVG(profit_margin) FROM transactions;

--total revenue earned in a particular year and in particular market
SELECT SUM(transactions.sales_amount)
FROM transactions 
	INNER JOIN date 
		ON transactions.order_date = Date.date 
			WHERE date.year = 2020 AND transactions.market_code = 'Mark001'; 

--distinct product sold in particular market
SELECT DISTINCT product_code FROM transactions WHERE market_code = 'Mark001';
