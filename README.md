# LITA_SALES-DATA

### PROJECT TITLE: Sales Performance Analysis for A Retail Store

### PROJECT OVERVIEW

This project aims to analyze sales data for retail store to identify trends, patterns, and areas for improvement. The analysis will provide insights into sales performance, customer behavior, and product preferences, enabling data-driven decisions to drive business growth.

### DATA SOURCE

The primary source of data used is Data Sale.csv and this is an open source data that can be freely downloaded from an open source online such ad Kaggle or any other data repository site.

## TOOLS USED
- Microsoft Excel [Download here](https://www.microsoft.com)
1. For Data Cleaning.
2. For Data Analysis.
3. Data Visualization.
   
- SQL (Structured Query Language) for query of Data
  
- PowerBi
1. For Data VIsualization.
2. Data Modelling.
3. Data Analysis.
4. Data Reporting.
5. Business Intelligence.

- GitHub for Potfolio Building

## DATA CLEANING AND PREPARATION
In the inital phase of the Data Cleaning and Preparation, we perform the following action.

1. Data loading and inspection.
2. Handling missing values.
3. Removing duplicates.
4. Data Transformation.
5. Data Quality checks.
6. Data Cleaning and formatting.

## EXPLORATORY DATA ANALYSIS
EDA involved the exploring of the data to answer some questions about the Data such as

1. Retrieve the total sales for each category.
2. Find the number of sales transactions in each region.
3. FInd the highest selling product by total sales value.
4. Calculate total revenue per product.
5. Calculate monthly sales totals for the current year.
6. Find the top 5 customers by total purchase amount.
7. To calculate the percentage of total sales contributed by each region.
8. Identify products with no sales in the last quarter.

## DATA ANALYSIS
```SQL
1. SELECT * FROM [dbo].[RD SALES DATA]

2. ---- NO 1. To retrieve the total sales for each category

SELECT product, sum([Total_Sales]) AS Total_Sales
FROM [dbo].[RD SALES DATA]
GROUP BY product
ORDER BY SUM([Total_Sales]) DESC;

3. -----  No 2. find the number of sales transactions in each region

SELECT Region , COUNT([Quantity]) AS Count_Sales
FROM  [dbo].[RD SALES DATA]
GROUP BY Region
ORDER BY COUNT([Quantity])

4. ----  NO 3. fInd the highest selling product by total sales value

SELECT TOP 1 PRODUCT, SUM(quantity*[UnitPrice]) AS Total_Revenue
FROM [dbo].[RD SALES DATA]
GROUP BY product

5. ---- NO 4. Calculate total revenue per product
 
 SELECT Product, SUM([Total_Sales]) AS Revenue
 FROM  [dbo].[RD SALES DATA]
 GROUP BY  product
 ORDER BY Sum([Total_Sales]) ASC;

6.  ---NO 5. calculate monthly sales totals for the current year.

     Select month(OrderDate) as month,
  sum(quantity*unitprice) as MonthlySales
From [dbo].[RD SALES DATA]
Where year(OrderDate) = year(GetDate())
Group by month(OrderDate)
Order by Month;

7. --- NO 6. Find the top 5 customers by total purchase amount.

SELECT TOP 5 [Customer_Id], SUM([Total_Sales]) AS total_purchase_amount
FROM [dbo].[RD SALES DATA]
GROUP BY [Customer_Id]
ORDER BY SUM([Total_Sales]) DESC;

8. SELECT 
    Region, 
    SUM(Quantity * UnitPrice) AS Regional_Sales,
    (SUM(Quantity * UnitPrice) * 1.0 / (SELECT SUM(Quantity * UnitPrice) 
	FROM [dbo].[RD SALES DATA])) * 100 AS Percentage_of_Total_Sales
FROM 
    [dbo].[RD SALES DATA]
GROUP BY 
    Region
ORDER BY 
    Regional_Sales DESC;

9. SELECT Product FROM [dbo].[RD SALES DATA]
GROUP BY Product
HAVING SUM(CASE 
WHEN OrderDate BETWEEN '2024-06-01' AND '2024-08-31' 
THEN 1 ELSE 0 END) = 0
```
## DATA VISUALIZATION

- EXCEL

- ![EXCELTOTALSALESBYPRDT](https://github.com/user-attachments/assets/3345d08e-2c5c-46c1-a1e8-549ba18dee53)

- ![EXCELTOTALSALESBYREG](https://github.com/user-attachments/assets/12acbfdd-4dae-402f-854f-ca71c255b694)

- ![%OFTOTALSSALESBYPRDTBYREG](https://github.com/user-attachments/assets/dddf6819-859a-4747-82d7-85b69d69b538)

- ![EXCELAVESALESBYPRDT](https://github.com/user-attachments/assets/40d1fb56-3262-46a0-acf1-99e2168682c0)

- ![EXCELTOTALSALESBYPRDT](https://github.com/user-attachments/assets/c70ac61c-37df-4107-9f2a-e3460d88643d)

- ![EXCELREVENUEBYREG](https://github.com/user-attachments/assets/4c8f53df-92b6-4e59-b177-b9118541a458)

- ![EXCELREGBYSOQBYCOP](https://github.com/user-attachments/assets/48f60f02-5e01-4a38-97d0-b8b4fe556d7d)


  - SQL
 
    - ![SALESDATA](https://github.com/user-attachments/assets/cafc3644-0b99-4f13-b093-30e506432510)
   
    - ![SD%TOTALSALES](https://github.com/user-attachments/assets/9f3f8419-8f55-4eee-9bdd-724cc54c2d04)
   
    - ![SDAVEDUR](https://github.com/user-attachments/assets/5f6ce198-a2ed-42e6-a28b-985f394dda58)
   
    - ![SDCOUNTSALESBYREGION](https://github.com/user-attachments/assets/93b7e1c9-b4fa-40a5-a9f7-9efd8ebc97d6)
   
    - ![SDCUSBYTPA](https://github.com/user-attachments/assets/99e0f4f2-ecd4-4d0b-8fcc-7632766d6bec)
   
    - ![SDMONTHLYSALES](https://github.com/user-attachments/assets/3db24dca-b665-48f5-8c52-143c6d47088f)
   
    - ![SDNOSALESPRODUCT](https://github.com/user-attachments/assets/8ece7919-2c6e-444b-a9f0-65abf31ba289)
   
    - ![SDTOTALREVENUEBYPRODUCT](https://github.com/user-attachments/assets/172eb162-8657-4116-8018-b2d3dc5b85e6)

    -![SDTOPPRODUCT](https://github.com/user-attachments/assets/67ccaf84-514a-4569-8c4d-b2bea3757015)

    -![SDTOTALREVENUEBYPRODUCT](https://github.com/user-attachments/assets/b71e422c-28f2-4558-b1f2-2665e48b3083)
    
    - ![SDTOTALSALESBYPRODUCT](https://github.com/user-attachments/assets/c506f127-4aa6-4f2d-afa6-4679b3ef6ed4)

    -![SUMOFTOTALSALESBYMTH](https://github.com/user-attachments/assets/d022a7ad-976c-4b68-af21-c31744389258)


- POWERBI

- ![SALESDATAPOWERBI](https://github.com/user-attachments/assets/fd4ca2ed-c93f-4d52-953c-290c338c3ced)

  
















































