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

ANSWER: The top 3 regions in terms of sales are; WEST,ONTARIO AND PRARIE while the Bottom 3 are NUNAVUT, NORTHWEST TERITORIES AND YUKON.

3. What were the total sales of appliances in Ontario?
``` SQL
SELECT PRODUCT_SUB_CATEGORY,SUM(SALES) AS [TOTAL SALES]
   FROM [dbo].[KMS Sql Case Study (1)]
WHERE REGION = 'ONTARIO'
GROUP BY PRODUCT_SUB_CATEGORY

6. Advise the management of KMS on what to do to increase the revenue from the bottom 10 customers
7. KMS incurred the most shipping cost using which shipping method?
8. Who are the most valuable customers, and what products or services do they typically purchase?
9. Which small business customer had the highest sales?
10. Which Corporate Customer placed the most number of orders in 2009 – 2012?
11. Which consumer customer was the most profi table one?
12. Which customer returned items, and what segment do they belong to?
13. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer
### Report
