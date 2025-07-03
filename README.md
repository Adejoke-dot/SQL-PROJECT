# SQL-PROJECT
This is the solution to case study Two: DSA Project.
## Project Topic: Kultra Mega Store Inventory

### Project overview
This SQL project focuses on cleaning, implementing, and querying a relational database to store, manage and analyze structured data efficiently. 
The Data Analysis aim to present key insights and findings to support the Abuja division of Kultra Mega Store Inventory.
The database includes multiple related tables with primary and foreign keys to ensure data integrity and support complex relationships.

### Data Sources

The primary source of Data used here is Data Sale.csv and this is an open source data that can be freely downloaded from an open source online such as kaggle.

### Tools Used

- Ms Excel.
  1. For Data collection.
  2. For Data Cleaning.
- SQL Server.
  1. For Querying.
  2. For Data Analysis.
     
### Data Cleaning and Preparation

In the initial phase of the Data cleaning and preparations, we perform the following action; 

Data loading, inspection, handling missing variables, data cleaning and formatting.

### Exploratory Data Analysis

EDA involved the exploring of the data to answer some questions about the data such as;
  1. Which product category had the highest sales?
  2. What are the Top 3 and Bottom 3 regions in terms of sales?
  3. What were the total sales of appliances in Ontario?
     
### Data Analysis

This is where we include some basic line of codes or used during analysis.

 - E.G
1. Which product category had the highest sales?
   ``` SQL
   SELECT PRODUCT_CATEGORY,SUM([SALES]) AS [TOTAL SALES]
    FROM [dbo].[KMS Sql Case Study (1)]
    GROUP BY PRODUCT_CATEGORY
    ORDER BY [TOTAL SALES] DESC
   
  ANSWER: The product category that have the highest sales is Technology.

2. What are the Top 3 and Bottom 3 regions in terms of sales?
``` sql
 SELECT TOP 3 REGION, SUM(SALES) AS [TOTAL SALES]
   FROM [dbo].[KMS Sql Case Study (1)]
   GROUP BY REGION
   ORDER BY [TOTAL SALES] DESC

ANSWER: 1. The top 3 regions in terms of sales are; WEST,ONTARIO AND PRARIE
 2. the Bottom 3 are NUNAVUT, NORTHWEST TERITORIES AND YUKON.


3. What were the total sales of appliances in Ontario?
``` sql
SELECT PRODUCT_SUB_CATEGORY,SUM(SALES) AS [TOTAL SALES]
   FROM [dbo].[KMS Sql Case Study (1)]
WHERE REGION = 'ONTARIO'
GROUP BY PRODUCT_SUB_CATEGORY

ANSWER: Total sales of appliances in ONTARIO is 202346.8400000000.

4. Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers.

``` sql
SELECT TOP 10 CUSTOMER_NAME,Profit,Product_Category,Product_Container, SUM(SALES) AS [TOTAL SALES]
   FROM [dbo].[KMS Sql Case Study]
GROUP BY CUSTOMER_NAME,Profit,Product_Category,Product_Container,
ORDER BY [TOTAL SALES] ASC

ANSWER: To incease the revenue for the bottom 10 customers;
1. They should buy in large quatities/bulk so that they can make more profit.
2. Shipping cost is too high, they should use cheaper shipping oprions.
3. Avoid offering high discounts on low-quantity or low-value orders.

5. KMS incurred the most shipping cost using which shipping method?

``` sql
SELECT Ship_Mode,SUM(SHIPPING_COST) AS [TOTAL SHIPPING_COST]
   FROM [dbo].[KMS Sql Case Study (1)]
GROUP BY Ship_Mode
ORDER BY [TOTAL SHIPPING_COST] DESC

ANSWER: KMS incure the most shipping cost using Delivery Truck.

6. Who are the most valuable customers, and what products or services do they typically purchase?
``` sql
SELECT Customer_Segment,Product_Sub_Category,Customer_Name,SUM(Sales) AS [TOTAL SALES]
   FROM [dbo].[KMS Sql Case Study (1)]
GROUP BY Customer_Segment,Product_Sub_Category,Customer_Name
ORDER BY [TOTAL SALES] DESC
ANSWER: Emily phan and the product they buy is office machines.

7. Which small business customer had the highest sales?
``` sql
SELECT TOP 1 *
   FROM [dbo].[KMS Sql Case Study (1)]
WHERE Customer_Segment = 'SMALL BUSINESS'
ORDER BY SALES DESC

ANSWER: Dennis kane
8. Which Corporate Customer placed the most number of orders in 2009 – 2012?
``` sql
SELECT TOP 1 *
   FROM [dbo].[KMS Sql Case Study (1)]
WHERE Customer_Segment = 'CORPORATE'
ORDER BY Order_Quantity DESC
ANSWER: Barry weirich

9. Which consumer customer was the most profi table one?
``` sql
SELECT TOP 1 *
   FROM [dbo].[KMS Sql Case Study (1)]
WHERE Customer_Segment = 'CONSUMER'
ORDER BY Profit DESC

ANSWER;Emily phan

10. Which customer returned items, and what segment do they belong to?
``` sql
SELECT Customer_Name,Customer_Segment,Product_Category,Product_Sub_Category
   FROM [dbo].[KMS Sql Case Study (1)]
join [dbo].[Order_Status]
on [dbo].[KMS Sql Case Study (1)].Order_ID = [dbo].[Order_Status].Order_ID

ANSWER:
1. Tamara Dahlen	Corporate
2. Jonathan Doherty Corporate
3. Jonathan Doherty Corporate
4. Michael Dominguez	Home Office	
5. Anne Pryor Consumer
6. Erin Creighton	Corporate
7. Erin Creighton	Corporate	
8. Frank Gastineau	Small Business	
9. Cari Sayre	Corporate	
10. Sheri Gordon	Corporate

11. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer.
ANSWER: yes

### Report


