# AtliQ Hardware Sales Insights

## AtliQ Hardware
A company that supplies computer hardware and peripherals to many clients across India.\
The company has a head office in Delhi and regional offices throughout India.

---

## Business Issue
The sales director is currently encountering numerous challenges due to the rapid growth of the marketing department, making it difficult for him to effectively monitor and manage sales. To address this, he requires more precise insights regarding the company's sales performance in order to make informed decisions.

---

## Solution
- Create a simple and informative dashboard about the company sales.
- I used **`SQL`** queries in **`Microsoft SQL Server Management Studio`** to look into the data and **`Power BI`** for **`ETL`** and **`Visualizations`** to create the insights dashboard.

---


	
# 
#### `# Insights`


After a quick data exploration in MS SQL Server, here are some initial findings:
- The database comprises five tables: customers, date, markets, products, and transactions.
- The dataset includes 17 markets, 279 products, and 38 customers.
- The recorded data spans from October 2017 to June 2020.
-  In 2020, the total revenue amounted to ₹142.22 million, indicating a significant decrease of 57.7% compared to the previous year's revenue of ₹336.02 million.
- Currency Discrepancy: While the majority of transactions are denoted in Indian Rupees (₹), two records are in US Dollars ($).
- The sales amount and market columns contain some erroneous values that will be addressed during the ETL (Extract, Transform, Load) process.

---

## ETL(Extract, Transform, Load)
Once I knew the basic features of the data I had to work with, I Imported the SQL database into Power BI to do the necessary transformations and make a simple, reliable, and helpful dashboard.

# 

#### # Data Modeling Step
We have one main table and four other tables having one shared column with the main table. So we will connect the other tables to the main table using the shared columns.
<img align="right" alt="Coding" width="573" src= "https://github.com/Laxman-Lakhan/AtliQ-Hardware-Sales-Insights/blob/acba4322c422a8dac8b24a450ca1b6a35384617a/Data/Screenshots/ETL_.png" >

- Main Table: transactions

|Table|Column|Main Table Column|   
|---|---|---|
|customers|Customer_Code|Customer_Code|
|date|date|Order_Date|
|products|Market_Code|Market_Code|
|markets|Product_Code|Product_Code|


# 

#### # Filtering, Cleaning and Adding New Columns
- The company is serving only in India, So “Paris” and “New York” in the market table are garbage values, so filtering them out.
- The “currency” column (in transactions table) have 2 USD currency values, So created a new column called “Sales”, where all the sales_amount is in INR Currency.

---

#### # Conclusions
- Sales were rapidly decreasing in 2020 compared to 2019 by around 57.7%.
- Highest revenue generated from Markets such as Delhi NCR, Mumbai, Ahmedabad, Bhopal, Nagpur, and so on.
- Highest quantities sold in the Market such as Delhi NCR, Mumbai, Nagpur, Kochi, Ahmedabad, and so on.
- Majority of the sales were takes place in the month of January followed by November and March.

#### # Recommendation
- Make a new sales strategy for lucknow since its showing lowest revenue and negative profit margin and if possible so as for Surat and Bhubhaneshwar also.
- try to increase sales quantity in Patna, Surat and Kanpur since they have lowest sales quantity.
- start target campagin for Prod047 and Prod061 since they two are the most profitable and most selling products.
- try to give special benefits to Electronics and Excel stores as they are most profitable customers.
- make campgain strategy for mid year as they are showing high sales among other months.


