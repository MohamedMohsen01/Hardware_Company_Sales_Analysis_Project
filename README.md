# AtliQ Hardware Sales Insights

## AtliQ Hardware
A company that supplies computer hardware and peripherals to many clients across India.\
The company has a head office in Delhi and regional offices throughout India.

---

## Business Issue
The sales director is currently encountering numerous challenges due to the rapid growth of the marketing department, making it difficult for him to effectively monitor and manage sales. To address this, he requires more precise insights regarding the company's sales performance in order to make informed decisions.

---

## Methodology
I created an interactive and informative sales dashboard for the company using SQL queries in Microsoft SQL Server Management Studio for data analysis and Power BI for ETL and visualizations.

By leveraging SQL queries in Microsoft SQL Server Management Studio, I gathered and examined relevant data from various sources, gaining valuable insights into the company's sales performance. 

Using Power BI's ETL capabilities, I transformed and loaded the extracted data into a suitable format for the sales dashboard.
Utilizing Power BI's extensive visualizations, I designed an intuitive and user-friendly dashboard that presents sales data in an interactive manner. This allows stakeholders to effortlessly explore and analyze key metrics, trends, and patterns.

---


	
# 
## Insights


After a quick data exploration in MS SQL Server, here are some initial findings:
- The database comprises five tables: customers, date, markets, products, and transactions.
- The dataset includes 17 markets, 279 products, and 38 customers.
- The recorded data spans from October 2017 to June 2020.
- In 2020, the total revenue amounted to ₹142.22 million, indicating a significant decrease of 57.7% compared to the previous year's revenue of ₹336.02 million.
- Currency Discrepancy: While the majority of transactions are denoted in Indian Rupees (₹), two records are in US Dollars ($).
- The sales amount and market columns contain some erroneous values that will be addressed during the ETL (Extract, Transform, Load) process.

---

# 

#### # Data Modeling Steps
We have a main table and four additional tables that share a common column with the main table. To establish connections between these tables, we will link the other tables to the main table using the shared columns.



<img align="right" alt="Coding" width="573" src= "https://github.com/Laxman-Lakhan/AtliQ-Hardware-Sales-insights/blob/acba4322c422a8dac8b24a450ca1b6a35384617a/Data/Screenshots/ETL_.png" >

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

## Conclusions
- Sales were rapidly decreasing in 2020 compared to 2019 by around 57.7%.
- Highest revenue generated from Markets such as Delhi NCR, Mumbai, Ahmedabad, Bhopal, Nagpur, and so on.
- Highest quantities sold in the Market such as Delhi NCR, Mumbai, Nagpur, Kochi, Ahmedabad, and so on.
- Majority of the sales were takes place in the month of January followed by November and March.

---

## Recommendation
#### Proposed sales strategy:

Identify low-performing markets:
 1. Analyze the performance of Lucknow, Surat, and Bhubhaneshwar.
 2. Focus on improving revenue and profit margins in these cities.

Improve sales quantity in low-performing cities:
 1. Concentrate efforts on increasing sales in Patna, Surat, and Kanpur, which have the lowest sales quantity.
 2. Explore potential reasons for the low sales and address them accordingly (e.g., market research, targeted advertising, competitive pricing).

Target campaign for high-performing products:
 1. Launch a targeted campaign for Prod047 and Prod061, as they are the most profitable and top-selling products.
 2. Allocate additional marketing resources to promote these products effectively.

Provide special benefits to Electronics and Excel stores:
 1. Identify the most profitable customers, specifically in the Electronics and Excel stores.
 2. Offer exclusive incentives such as discounts, loyalty programs, or personalized offers to enhance their loyalty and encourage repeat purchases.

Campaign strategy for mid-year sales:
 1. Leverage the high sales performance during the mid-year period.
 2. Design a compelling campaign to capitalize on this trend and further boost sales during this time.
 3. Utilize various marketing channels, including digital advertising, social media campaigns, and targeted promotions.

By implementing these strategies, we aim to improve revenue and profit margins in Lucknow, Surat, and Bhubhaneshwar, increase sales quantity in Patna, Surat, and Kanpur, and maximize sales during the mid-year period.

## Dashboard

For the Dashboard, please feel free to visit my power BI Dashboard: [Power BI Dashboard Link](https://app.powerbi.com/view?r=eyJrIjoiMjcwMDFiOTYtMzI3Zi00YjQ2LWFkMTMtNDFiMDViMDEwNzM0IiwidCI6IjMzODU0OWQ1LThiMDgtNDdlMS1iOGQyLWJlNTIwZTJiM2FkNSJ9)
