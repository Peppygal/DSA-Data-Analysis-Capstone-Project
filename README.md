# DSA-Data-Analysis-Capstone-Project

Capstone Project Documentation with the Incubator's Hub.

#### Kultra Mega Stores Inventory Sales Analysis

- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Expected Outcomes](#expected-outcomes)
- [Data Source](#data-source)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Tools Used](#tools-used)
- [Analysis](#analysis)
- [SQL Queries](#sql-queries)
- [Overall Conclusion](#overall-conclusion)

### Project Overview
---
This project involves performing data-driven analysis on the KMS Superstore dataset using SQL to generate actionable business insights. The goal is to evaluate customer behavior, product performance, regional trends, and operational efficiency through a series of questions categorized into two case scenarios.
By examining this data, we aim to support strategic decision-making around inventory, pricing, and marketing efforts to drive growth and improve profitability.
The analysis focuses on helping the KMS management team understand where the business is thriving, what areas need improvement, and how strategic decisions can be supported through data.

### Objectives
---
#### Identify which product categories and regions contribute most to revenue:

This involves analyzing the total sales across different product categories (e.g., Technology, Furniture) and geographical regions (e.g., West, Ontario).  
**Purpose:** To find out where most of the company’s revenue comes from, so that management can focus marketing and inventory efforts on the strongest-performing areas.

#### Evaluate customer profitability, loyalty, and purchasing behavior

This includes identifying high-value customers based on sales, profit contribution, and purchase frequency, and understanding what products they typically buy.  
**Purpose:** To better understand customer behavior, prioritize relationship-building with loyal and profitable customers, and use their profiles to attract similar customers.

#### Understand shipping cost distribution relative to order priorities

Analyze how much shipping cost is incurred for different shipping methods and whether it aligns with the urgency of order priority (e.g., High vs Low Priority).  
**Purpose:** To determine if shipping resources are being used efficiently, or if fast and expensive shipping methods are being overused for non-urgent orders.

#### Make strategic recommendations based on revenue trends, product demand, and customer value

After all analyses are done, the findings will be used to make specific business suggestions, such as:
- Which product categories to promote
- Which regions to invest more in
- Which customers to retain or target  
**Purpose:** To turn raw data into actionable insights that support strategic planning, marketing, inventory management, and profitability.


### Expected Outcomes
---
Through this analysis, the project seeks to deliver actionable insights that will help:

#### Ranked list of product categories and regions by total sales:

A clear report showing which categories and regions perform best in terms of revenue.  
**Benefit:** Helps the company focus on its strongest products and markets.

#### Identification of the most and least valuable customers:

A breakdown of the top 10 and bottom 10 customers based on sales and profit, and insight into their behavior (what they buy, how often, etc.).  
**Benefit:** Enables targeted marketing, customer retention strategies, and sales focus.

#### Insight into shipping cost efficiency by shipping method and order priority

Evaluation of whether fast and costly shipping (like Express Air) is being used appropriately for urgent orders, and whether cheaper options (like Delivery Truck) are underutilized.  
**Benefit:** Helps reduce unnecessary shipping expenses and improve operational efficiency.

#### Clear recommendations for improving profitability, customer targeting, and operational efficiency

- Which product lines to invest more in
- Which customers to build relationships with
- How to adjust shipping strategy to save costs  
**Benefit:** Provides the company with practical, data-backed actions to grow revenue and reduce waste.

### Data Source
---
The primary source of data used here is Data Sale.csv and this is an open source data that can be freely downloaded from an open source online such as Kaggle or FRED or any other data repository site.

Dataset Name: KMS Superstore Data

#### Exploratory Data Analysis
---

EDA involved the exploration of the data using SQL to answer some questions about the Data such as:
   1. Which product category had the highest sales? 
   2. What are the Top 3 and Bottom 3 regions in terms of sales? 
   3. What were the total sales of appliances in Ontario?  
   4. KMS incurred the most shipping cost using which shipping method?
 
#### Tools Used
---
- Structured Query Language- SQL for querying and analysis.
- SSMS (as SQL editor).
- Github for Portfolio building.

#### Analysis
---

The analysis was conducted using Structured Query Language - SQL and it was used for Querying, joins, aggregations, subqueries, analytics, following a series of steps outlined below:

- *Uploading the Dataset into SQL Database*:  
  The KMS Superstore dataset was imported into a relational database system (e.g., Microsoft SQL Server).  
  A new table (e.g., KMS_Superstore_Data) was created.

- *Data types were defined* for each column (e.g., Sales as FLOAT, Order_Date as DATE).

- *Any import errors* (e.g., due to NULL values or formatting issues) were resolved before proceeding.

- *Verifying the Structure and Contents of the Table*

- *Exploring the Dataset* (Exploratory SQL Checks)

- *Cleaning or Handling Missing Values*:  
  Replaced NULL values with appropriate placeholders (e.g., 0 for numeric fields, or excluded them from calculations).

- *Writing SQL Queries to Answer Each Business Question*

- *Interpreting Query Results*:  
  Query outputs were analyzed to extract meaningful insights.  
  Numeric results (like total sales, shipping cost, number of orders) were compared across groups.  
  Patterns and anomalies (e.g., extremely low sales in certain regions) were noted.

- *Documenting and Communicating the Insights*:  
  Each result was translated into a business insight (e.g., “Technology is the top-selling category”).  
  Recommendations were generated based on patterns observed.

- These insights were grouped under each case scenario to align with business objectives.

### SQL QUERIES

### Case Scenario I 
---
1. Which product category had the highest sales?

   ```sql
   Select Product_Category, SUM(distinct Row_ID) as TotalSale
   from [dbo].[KMS Sql Case Study]
   group by Product_categor
   order by TotalSales desc
   ```
   <img width="378" alt="SQ a" src="https://github.com/user-attachments/assets/af086735-1954-4276-bd38-8c27f10d833f" />

### Purpose of the Query:

This query is to identify the top-performing product category in terms of total sales. This helps uncover where the business generates the most revenue.

### Breakdown of the Query:

Grouped sales data by Product Category

Summed the Sales for each category

Ordered the results in descending order of total sales

### Insight Derived:

The output helps us understand the product category with the highest total sales, shows which area drives the most revenue. 

This is valuable for sales strategy, inventory planning, and marketing focus.

### Relevance to the Dataset and Project:

This query is highly relevant because it utilizes key fields in the dataset—Product Category and Sales—to reveal which category generates the most revenue.

Within the context of the project (analyzing business performance using the KMS Superstore dataset), identifying the top-selling product category helps:

Evaluate sales concentration, Understand customer purchasing behavior, Support strategic decisions on inventory, promotions, and supply chain focus.

It aligns with the overall project goal of using data to drive informed, actionable insights in business operations.

### Potential Next Steps:

Deep dive into sub-categories under that top category to find specific bestsellers.

Analyze customer segments buying from this category.

Consider promotional campaigns or stock prioritization for this high-performing category.

Investigate whether this is a seasonal trend or consistent over time.

---
2. What are the Top 3 and Bottom 3 regions in terms of sales?
  
   - Top 3 regions

   ```sql
   Select top 3 Region, SUM(Distinct Sales) AS TotalSales
   from [dbo].[KMS Sql Case Study]
   group by Region
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

### Purpose of the Query:

To identify which regions contribute the most and least to overall sales. This supports regional performance analysis and strategic business decisions.

Breakdown of the Queries:

Two SQL queries were used anaylsis Top 3 Regions by Sales and Bottom 3 Regions by Sales

### Insight Derived:

Top 3 Regions:
West, Ontario, and Prarie are the highest-performing regions. These are the strongest markets and contribute the most to revenue.

Bottom 3 Regions:
Nunavut, Northwest Territories, and Yukon recorded the lowest sales. These regions are underperforming compared to others.

This query suggests variations in customer demand, market size, or distribution reach across regions.

### Potential Next Steps:

- For Top Regions (West, Ontario, Prarie):

Investigate successful strategies and replicate them in underperforming regions.

Consider expanding product lines or services in these regions.

Continue investing in marketing and logistics to sustain growth.

- For Bottom Regions (Nunavut, Northwest Territories, Yukon):

Conduct a root-cause analysis: Are the issues logistical, demographic, or product-fit related?

Tailor marketing or outreach strategies to these regions.

Consider partnerships or incentives to boost visibility and access.

---

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

### Insights Derived:

Based on our analysis, Appliances generated over ₦202346.8639 in sales in Ontario alone.

This suggests a strong demand for home or office appliances within that region.

Appliances in Ontario could be one of the highest-performing product sub-categories by regional combination.

### Relevance to Dataset & Project:

Supports the project’s goal of identifying high-performing product-region pairs.

Helps the company prioritize resources and targeted campaigns in high-revenue areas.

Offers insight into regional consumer behaviour and product preference.

### Potential Next Steps / Recommendations

Invest in appliance marketing, specifically in Ontario (e.g., seasonal promos, email campaigns).

Ensure adequate inventory of popular appliances in Ontario-based warehouses.

Use the trend to identify similar high-opportunity regions.

Segment Ontario appliance buyers for loyalty rewards or cross-sell opportunities.

---
   
4. Advise the management of KMS on what to do to increase the revenue from the bottom 
   10 customers

   ```sql
   Select top 10 Customer_Name, SUM(Sales) AS TotalSales
   from [dbo].[KMS Sql Case Study]
   group by Customer_Name
   order by TotalSales asc
   ```
   <img width="456" alt="SQL d" src="https://github.com/user-attachments/assets/91708232-af5a-4e6d-92cf-2b6f58eb5a37" />

### Insight Dervied: 

Bottom 10 Customers by Revenue

An analysis of the customer base shows that the bottom 10 customers contribute the least revenue to the company. While these customers currently have minimal sales activity, they represent a potential growth opportunity if strategically nurtured.

### Recommendations to Increase Revenue from Bottom 10 Customers:

Understand Their Behavior: Conduct a customer profile analysis to understand their industry, purchase history, order frequency, and preferences.
Ask Why aren’t they buying more? — Is it pricing? Product fit? Awareness?

Personalized Engagement: Assign a sales rep or customer success contact to engage them directly. Tailor communication and recommendations based on their specific needs or sector.

Offer Targeted Promotions or Incentives: Design exclusive offers, discounts, or loyalty incentives to encourage repeat purchases and increase order size.

Cross-Selling and Upselling: Review the products they’ve purchased and suggest complementary or higher-value alternatives.

Improve Customer Experience: Make sure these customers are not facing service issues, delivery delays, or poor onboarding. Sometimes, low revenue is caused by friction in the customer journey.

Survey or Feedback Collection: Send a short survey to understand what’s holding them back from buying more — pricing, value, competition, etc.

Monitor and Measure Progress: Create a small dashboard or tracker to monitor how these bottom 10 customers respond to your interventions over time.

The bottom 10 customers currently contribute the least to KMS revenue. However, with focused engagement, tailored offers, and improved customer experience, these accounts can be transformed into active, higher-value customers. Unlocking even a modest increase in their spending could result in measurable revenue growth.

---
5. KMS incurred the most shipping cost using which shipping method?

   ```sql
   Select top 5 Ship_Mode, SUM(Shipping_Cost) AS TotalShipping_Cost
   from [dbo].[KMS Sql Case Study]
   group by Ship_Mode
   order by TotalShipping_Cost desc
   ```
   <img width="511" alt="SQL e" src="https://github.com/user-attachments/assets/09b99099-4eba-4a10-883c-0df1d6aa7549" />

### Insight Derived:

From our analysis, Delivery Truck is the shipping method that incures the highest total shipping cost, amounting to 51,971.94 (approx).
This suggests that delivery trucks are either:

Used more frequently, Cover longer distances, or Incure higher operational/logistical expenses compared to other methods.

 ### Potential Next Steps:

Break down shipping cost per order to see if delivery trucks are cost-efficient on a per-unit basis.

Compare costs across other shipping methods (e.g., First Class, Standard Class, Express).

Examine regions or order types relying heavily on delivery trucks—are there alternatives?

### Recommendations:

Optimize Delivery Routes: Use route optimization tools or software to reduce mileage and fuel costs.

Evaluate Alternative Methods: Consider shifting certain deliveries to lower-cost options where feasible.

Negotiate with Carriers: If trucks are third-party-operated, review and renegotiate contracts to reduce costs.

Bundle Shipments: Group orders going to similar locations to reduce the number of truck trips.

Monitor Performance: Continuously track shipping method efficiency to ensure cost-effectiveness over time.

---

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

  ### Insight on Analysis

The analysis identified Emily Phan, Jasper Cacioppo, Craig Carreira, Clytie Kelty and Dennis Kane as among the most valuable customers based on total sales and repeat purchases. These customers consistently purchase high-value items, including copiers and tech equipment such as Polycom ViewStation and Canon PC 940 Copiers.


### Relevance to Dataset & Project

This finding supports the project's objective to understand customer value and behaviour, helping KMS identify its top revenue contributors. 

It also shows which products drive loyalty and profitability.


### Potential Next Steps & Recommendation

- Build loyalty programs targeting these high-value customers.

- Offer exclusive deals or early product access to retain and reward them.

- Use customer profiles to find and target similar buyers.

- Ensure these high-performing products remain well-stocked and promoted.

---

7. Which small business customer had the highest sales?

   ```sql
   SELECT TOP 1 Customer_Segment, Customer_Name, SUM(Sales) AS TotalSales
   FROM [dbo].[KMS Sql Case Study]
   WHERE Customer_Segment = 'Small Business'
   GROUP BY Customer_Segment, Customer_Name
   ORDER BY TotalSales desc
   ```
  <img width="409" alt="SQL g" src="https://github.com/user-attachments/assets/2e3f2cf8-5d52-48ef-b47c-281b3c8b25a3" />

  ### Insight Derived:

The analysis revealed that Dennis Kane is the highest-grossing small business customer, contributing a total of ₦75,967.59 in sales. This was determined by filtering the dataset for the 'Small Business' customer segment, grouping by customer name, and summing total sales.

 ### Relevance to the Dataset and Project:

Dennis Kane stands out as a key revenue driver within the small business segment, indicating a high purchasing frequency or preference for higher-ticket items.

### Potential next steps /Recommendation:

Build a strong relationship with Dennis Kane through personalized offers or account management.

Analyze the products he purchases to tailor promotions to similar customers.

Explore opportunities to upsell or introduce related products to boost sales further.

---

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

 ### Insight on Analysis – Corporate Orders (2009–2012)

The analysis showed that Adam Hart, a corporate customer, placed the highest number of orders (18) between 2009 and 2012. This was determined by filtering order dates within the range, segmenting by 'Corporate', and counting orders per customer.

### Relevance to Dataset & Project

This insight helps identify highly engaged corporate clients, which aligns with the project’s goal of analyzing customer behaviour and order trends over time. It highlights corporate loyalty and potential long-term value.

### Potential Next Steps / Recommendation
- Recognize and retain Adam Hart as a high-engagement customer.

- Offer business-focused incentives such as discounts or account support.

- Study his order history to uncover product trends and replicate the pattern with similar clients.

---

9. Which consumer customer was the most profitable one?
   ```sql
   SELECT TOP 1 [Customer_Name], SUM(Profit) AS Total_Profit
   FROM [dbo].[KMS Sql Case Study]
   WHERE [Customer_Segment] = 'Consumer'
   GROUP BY [Customer_Name]
   ORDER BY Total_Profit DESC;
   ```
   <img width="429" alt="SQL I" src="https://github.com/user-attachments/assets/61d0a714-7c43-4253-a70a-b7f7ed1be0e6" />

   ### Breakdown on Analysis – Most Profitable Consumer Customer:

The analysis revealed that Emily Phan was the most profitable consumer customer, generating a total profit of ₦34,005.44. This was determined by filtering for the 'Consumer' segment, grouping by customer name, and summing the Profit column.

 ### Insights Derived:

Emily Phan stands out as a high-value individual buyer, contributing significantly to profitability—more than any other consumer. This suggests strong brand loyalty and preference for high-margin products.

### Relevance to Dataset & Project:

This aligns with the project’s goal to uncover customer profitability patterns and informs strategic decisions around targeted marketing and customer relationship management.

### Potential Next Steps / Recommendation:

Nurture Emily Phan with personalized communication or loyalty rewards.

Analyze her purchasing behaviour to identify profitable product categories.

Use her profile as a benchmark to find and retain similar high-profit customers.

---

10. Which customer returned items, and what segment do they belong to?

    ```sql
    SELECT DISTINCT o.[Order_ID], o.[Customer_Name], o.[Customer_Segment]
    FROM [dbo].[KMS Sql Case Study] o
    JOIN [dbo].[OrderStatus] r
    ON o.[Order_ID] = r.[Order_ID]
    WHERE r.Status = 'Returned';
    ```
    <img width="467" alt="SQ j" src="https://github.com/user-attachments/assets/f630e8e0-1b73-414b-9300-c3de15bf1911" />

    ### Beakdown: Customers Who Returned Items

The analysis identified the top 10 customers who returned items, along with the customer segments they belong to (e.g., Consumer, Small Business, Corporate). This was done by filtering the dataset for return indicators (e.g., a "Returned" status or flag), grouping by customer name, and segmenting by Customer Segment.


 ### Insights Derived:

Returns occurred across all segments but were more frequent among consumer customers.

Some high-value customers also had return records, suggesting returns are not limited to low spenders.

Product types or shipping issues may be contributing factors.


### Relevance to Dataset & Project:

This insight supports the project's aim to understand customer behaviour, particularly patterns that affect profitability and satisfaction. Returns can signal problems in product quality, expectation mismatch, or delivery reliability.


### Potential Next Steps / Recommendations:

Investigate reasons for returns among top customers to reduce future occurrences.

Review return policies and product categories with high return rates.

Implement post-purchase follow-ups or satisfaction surveys to preempt return cases.

For loyal returners, consider offering incentives or better alternatives to retain them.

---

11. If the delivery truck is the most economical but the slowest shipping method and 
    Express Air is the fastest but the most expensive one, do you think the company 
    appropriately spent shipping costs based on the Order Priority? Explain your answer.

Based on the analysis, the company does not consistently spend shipping costs appropriately according to order priority. While some critical orders use faster shipping methods like Express Air or Regular Air, others still rely on the slower Delivery Truck. Similarly, some low-priority orders are shipped using more expensive methods. This mismatch suggests inefficiencies in the shipping strategy, leading to possible delays for urgent orders and unnecessary cost for non-urgent ones. To improve, shipping methods should be better aligned with order priority to balance speed and cost.

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
     
### Breakdown on Analysis – Shipping Cost vs. Order Priority:

Your analysis reviewed 15 total order priority cases and matched them against the shipping modes used (Regular Air, Express Air, Delivery Truck). It showed that even high-priority orders were sometimes shipped using Delivery Truck (the slowest but cheapest), and low-priority orders occasionally used Express Air (the fastest but most expensive).

### Insights Derived:

There appears to be no consistent alignment between Order Priority and Shipping Method.

Some critical orders were sent via slow, economical methods, possibly affecting delivery speed.

Likewise, some low-priority orders incurred higher costs unnecessarily through Express Air.


### Relevance to Dataset & Project:

This insight directly supports the project’s goal of understanding operational efficiency and cost management. It highlights a gap in how shipping methods are assigned relative to business needs and customer expectations.


### Potential Next Steps / Recommendation:

Establish strict shipping rules: Match Express Air with critical orders and delivery trucks with Low-priority ones.

Review and optimize the shipping logic used in order fulfilment.

Conduct a cost-benefit analysis of past shipments to reduce overspending and improve delivery reliability.

Train fulfilment staff or update automation rules to prioritize efficiency and urgency appropriately.


---

### Overall Conclusion

The KMS Superstore data analysis provided valuable insights into the company's performance across product categories, customer segments, geographical regions, and shipping methods. The analysis revealed that Technology was the top-performing product category, while regions like West and Ontario generated the highest revenue. Additionally, identifying high-value customers and their buying behavior allowed the company to better understand customer profitability and loyalty.

Shipping cost analysis showed opportunities to optimize logistics by aligning order priority with appropriate shipping methods. Furthermore, the assessment of bottom-performing regions and customers highlighted areas where targeted marketing and engagement strategies could drive improved sales and retention.

In summary, this project has equipped KMS with data-backed insights to:

Focus on high-revenue products and regions,

Strengthen relationships with profitable customers,

Improve operational efficiency in shipping,

And make strategic decisions to drive future growth and profitability.    

### Files in this Repository
- Code Block Syntax — to make the quries copyable 
- SQL.png/SQ.png — Screenshot of the of the query results
- README.md — Project documentation (this file)

---

**Project by**

Nwaebichi Perpetual

Data Analyst | SQL & Business Intelligence Enthusiast 





