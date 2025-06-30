# DSA-Data-Analysis-Capstone-Project
Capstone Project Documentation with the Incubator's Hub.

#### Kultra Mega Stores Inventory Sales Analysis


- [Project Overview](project-overview)
- [Objectives](obectives)
- [Expected Outcomes](expected-outcomes)
- [Data Source](data-source)
- [Exploratory Data Analysis](exploratory-data-analysis)
- [Tools Used](tools-used)
- [Analysis](analysis)
- [Business Task and Dashboard Component](business-task-dashboard-component)
- [Key Strategies and Recommendations](key-strategies-and-recommendation)
- [Conclusion](conclusion)

### Project Overview

This project involves performing data-driven analysis on the KMS Superstore dataset using SQL to generate actionable business insights. The goal is to evaluate customer behavior, product performance, regional trends, and operational efficiency through a series of questions categorized into two case scenarios.
By examining this data, we aim to support strategic decision-making around inventory, pricing, and marketing efforts to drive growth and improve profitability.
The analysis focuses on helping the KMS management team understand where the business is thriving, what areas need improvement, and how strategic decisions can be supported through data.

### Objectives

- Identify which product categories and regions contribute most to revenue

👉 This involves analyzing the total sales across different product categories (e.g., Technology, Furniture) and geographical regions (e.g., West, Ontario).
🔍 Purpose: To find out where most of the company’s revenue comes from, so that management can focus marketing and inventory efforts on the strongest-performing areas.

- Evaluate customer profitability, loyalty, and purchasing behavior

👉 This includes identifying high-value customers based on sales, profit contribution, and purchase frequency, and understanding what products they typically buy.
🔍 Purpose: To better understand customer behavior, prioritize relationship-building with loyal and profitable customers, and use their profiles to attract similar customers.

- Understand shipping cost distribution relative to order priorities

👉 Analyze how much shipping cost is incurred for different shipping methods and whether it aligns with the urgency of order priority (e.g., High vs Low Priority).
🔍 Purpose: To determine if shipping resources are being used efficiently, or if fast and expensive shipping methods are being overused for non-urgent orders.

- Make strategic recommendations based on revenue trends, product demand, and customer value

👉 After all analyses are done, the findings will be used to make specific business suggestions, such as:

   Which product categories to promote, Which regions to invest more in, Which customers to retain or target.

🔍 Purpose: To turn raw data into actionable insights that support strategic planning, marketing, inventory management, and profitability.


### Expected Outcome

Through this analysis, the project seeks to deliver actionable insights that will help:

- Ranked list of product categories and regions by total sales

👉 A clear report showing which categories and regions perform best in terms of revenue.
🔍 Benefit: Helps the company focus on its strongest products and markets.

- Identification of the most and least valuable customers

👉 A breakdown of the top 10 and bottom 10 customers based on sales and profit, and insight into their behavior (what they buy, how often, etc.).
🔍 Benefit: Enables targeted marketing, customer retention strategies, and sales focus.

- Insight into shipping cost efficiency by shipping method and order priority

👉 Evaluation of whether fast and costly shipping (like Express Air) is being used appropriately for urgent orders, and whether cheaper options (like Delivery Truck) are underutilized.
🔍 Benefit: Helps reduce unnecessary shipping expenses and improve operational efficiency.

- Clear recommendations for improving profitability, customer targeting, and operational efficiency

Which product lines to invest more in

Which customers to build relationships with

How to adjust shipping strategy to save costs
🔍 Benefit: Provides the company with practical, data-backed actions to grow revenue and reduce waste.

### Data Source
The primary source of data used here is Data Sale.csv and this is an open source data that can be freely downloaded from an open source online such as Kaggle or FRED or any other data repository site.

Dataset Name: KMS Superstore Data

#### Exploratory Data Analysis

EDA involved the exploration of the data using SQL to answer some questions about the Data such as:
   1. Which product category had the highest sales? 
   2. What are the Top 3 and Bottom 3 regions in terms of sales? 
   3. What were the total sales of appliances in Ontario?  
   4. KMS incurred the most shipping cost using which shipping method?
 
#### Tools Used

- Structured Query Language- SQL for querying and analysis.
- SSMS (as SQL editor).
- Github for Portfolio building.


#### Analysis

The analysis was conducted usingStructured Query Language -SQL and it was used for Querying, joins, aggregations, subqueries, analytics, following a series of steps outlined below:

1. Uploading the Dataset into SQL Database: The KMS Superstore dataset was imported into a relational database system (e.g., Microsoft SQL Server).

A new table (e.g., KMS_Superstore_Data) was created.

Data types were defined for each column (e.g., Sales as FLOAT, Order_Date as DATE).

Any import errors (e.g., due to NULL values or formatting issues) were resolved before proceeding.

2. Verifying the Structure and Contents of the Table.

3. Exploring the Dataset (Exploratory SQL Checks).

4. Cleaning or Handling Missing Values: Replaced NULL values with appropriate placeholders (e.g., 0 for numeric fields, or excluded them from calculations).

5. Writing SQL Queries to Answer Each Business Question

6. Interpreting Query Results: Query outputs were analyzed to extract meaningful insights.

Numeric results (like total sales, shipping cost, number of orders) were compared across groups.

Patterns and anomalies (e.g., extremely low sales in certain regions) were noted.

7. Documenting and Communicating the Insights: Each result was translated into a business insight (e.g., “Technology is the top-selling category”).

Recommendations were generated based on patterns observed.

These insights were grouped under each case scenario to align with business objectives.


### SQL QUERIES

### Case Scenario I 
1. Which product category had the highest sales?

   ```sql
   Select Product_Category, SUM(distinct Row_ID) as TotalSale
   from [dbo].[KMS Sql Case Study]
   group by Product_categor
   order by TotalSales desc
   ```
   <img width="378" alt="SQ a" src="https://github.com/user-attachments/assets/af086735-1954-4276-bd38-8c27f10d833f" />

2. What are the Top 3 and Bottom 3 regions in terms of sales?
  
   - Top 3 regions

   ```sql
   Select top 3 Region, SUM(Distinct Sales) AS TotalSales
   from [dbo].[KMS Sql Case Study]
   group by Regio
   order by TotalSales desc
   ```  
   <img width="322" alt="SQ bi" src="https://github.com/user-attachments/assets/84797b20-7226-4283-a371-a29b45085364" />

   - Bottom 3 regions
    
   ```sql
   Select top 3  Region, SUM(Distinct Sales) AS TotalSales
   from [dbo].[KMS Sql Case Study]
   group by Region
   order by TotalSales asc
   ```
   <img width="322" alt="SQ bii" src="https://github.com/user-attachments/assets/913f75f7-d737-4324-a5f8-4df32d77013d" />

3. What were the total sales of appliances in Ontario?

   ```sql
   SELECT Region,  Product_Sub_Category, SUM(Sales) AS TotalSales
   FROM [dbo].[KMS Sql Case Study]
   WHERE Region = 'Ontario'
   AND Product_Sub_Category = 'Appliances'
   GROUP BY Region,  Product_Sub_Category
   ORDER BY TotalSales desc
   ```
   <img width="405" alt="SQ c" src="https://github.com/user-attachments/assets/544c5c6d-920d-49e0-9762-a2bb59844899" />

4. Advise the management of KMS on what to do to increase the revenue from the bottom 
   10 customers

   ```sql
   Select top 10 Customer_Name, SUM(Sales) AS TotalSales
   from [dbo].[KMS Sql Case Study]
   group by Customer_Name
   order by TotalSales asc
   ```
   <img width="456" alt="SQL d" src="https://github.com/user-attachments/assets/91708232-af5a-4e6d-92cf-2b6f58eb5a37" />

5. KMS incurred the most shipping cost using which shipping method?

   ```sql
   Select top 5 Ship_Mode, SUM(Shipping_Cost) AS TotalShipping_Cost
   from [dbo].[KMS Sql Case Study]
   group by Ship_Mode
   order by TotalShipping_Cost desc
   ```
   <img width="511" alt="SQL e" src="https://github.com/user-attachments/assets/09b99099-4eba-4a10-883c-0df1d6aa7549" />

### Case Scenario II 

6. Who are the most valuable customers, and what products or services do they typically 
   purchase?

   i. Who are the most valuable customers?

   ```sql
   SELECT top 5 Row_ID, Customer_Name, SUM(Sales) AS TotalSpent
   FROM [dbo].[KMS Sql Case Study]
   GROUP BY Row_ID, Customer_Name
   ORDER BY TotalSpent DESC
   ```
  <img width="394" alt="SQ fii" src="https://github.com/user-attachments/assets/7b6f0655-1bcf-4d68-a0e0-a18d355c319b" />

   ii. what products or services do they typically purchase? 

   ```sql
  SELECT TOP 5 [Customer_Name], [Product_Name],
  SUM(Sales) AS Total_Sales
  FROM [dbo].[KMS Sql Case Study]
  GROUP BY [Customer_Name], [Product_Name]
  ORDER BY Total_Sales DESC;
  ```
  <img width="392" alt="SQ fi" src="https://github.com/user-attachments/assets/9ca44457-466c-455f-b334-3891debb0b33" />

7. Which small business customer had the highest sales?

   ```sql
   SELECT TOP 1 Customer_Segment, Customer_Name, SUM(Sales) AS TotalSales
   FROM [dbo].[KMS Sql Case Study]
   WHERE Customer_Segment = 'Small Business'
   GROUP BY Customer_Segment, Customer_Name
   ORDER BY TotalSales desc
   ```
  <img width="409" alt="SQL g" src="https://github.com/user-attachments/assets/2e3f2cf8-5d52-48ef-b47c-281b3c8b25a3" />

8. Which Corporate Customer placed the most number of orders in 2009 – 2012?
   ```sql
   SELECT TOP 1 Customer_Name, COUNT(DISTINCT Order_ID) AS Number_of_Orders
   FROM [dbo].[KMS Sql Case Study]
   WHERE customer_Segment = 'Corporate'
   AND Order_Date BETWEEN '2009-01-01' AND '2012-12-31'
   GROUP BY Customer_Name
   ORDER BY Number_of_Orders DESC;
   ```
   <img width="544" alt="SQL h" src="https://github.com/user-attachments/assets/08a7f250-9e25-4cab-8164-37ce4dbee5c9" />

9. Which consumer customer was the most profitable one?
   ```sql
   SELECT TOP 1 [Customer_Name], SUM(Profit) AS Total_Profit
   FROM [dbo].[KMS Sql Case Study]
   WHERE [Customer_Segment] = 'Consumer'
   GROUP BY [Customer_Name]
   ORDER BY Total_Profit DESC;
   ```
   <img width="429" alt="SQL I" src="https://github.com/user-attachments/assets/61d0a714-7c43-4253-a70a-b7f7ed1be0e6" />

10. Which customer returned items, and what segment do they belong to?

    ```sql
    SELECT DISTINCT o.[Order_ID], o.[Customer_Name], o.[Customer_Segment]
    FROM [dbo].[KMS Sql Case Study] o
    JOIN [dbo].[OrderStatus] r
    ON o.[Order_ID] = r.[Order_ID]
    WHERE r.Status = 'Returned';
    ```
    <img width="467" alt="SQ j" src="https://github.com/user-attachments/assets/f630e8e0-1b73-414b-9300-c3de15bf1911" />

11. If the delivery truck is the most economical but the slowest shipping method and 
    Express Air is the fastest but the most expensive one, do you think the company 
    appropriately spent shipping costs based on the Order Priority? Explain your answer.

     ```sql
     SELECT [Order_Priority], [Ship_Mode],
     COUNT([Order_ID]) AS OrderCount,
     ROUND(SUM(Sales - Profit), 2) AS EstimatedShippingCost,
     AVG(DATEDIFF(day, [Order_Date], [Ship_Date])) AS AvgShipDays
     FROM [dbo].[KMS Sql Case Study]
     GROUP BY [Order_Priority], [Ship_Mode]
     ORDER BY [Order_Priority], [Ship_Mode] DESC;
     ```
     <img width="408" alt="SQ k" src="https://github.com/user-attachments/assets/bdea7a97-0ba2-47c1-8a10-66b7aaf76f27" />



      



