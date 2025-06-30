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




      
   
    






      



