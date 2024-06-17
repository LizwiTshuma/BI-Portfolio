# Gear-Up Cycling Sales Data Project

###	Problem Statement

The manager of Gear-Up Cycling(an e-commerce cycle company) wants to improve their internet sales reports by moving from static reports to more dynamic visual dashboards. He wants the dashboard to focus on the total price of products sold over time, and which clients are his biggest source of business.

###	Proposed Solution
The solution is to build three dashboards. 

- Dashboard 1: 

Will provide an analysis of the sales overview of the company, and company performance measured against the budget. 

- Dashboard 2: 

Will provide an overview of the top-selling products over three years, sales by product category and subcategory, and total orders by product.

- Dashboard 3: 

This dashboard will provide a customer overview analysis with the top 10 customers by their spending, and gender analysis.

### User Requirements

### 1.
#### Role: Sales Manager	

Request: Dashboard overview of overall internet sales.

User value: Able to follow up on products sold and which ones are most popular amongst customers.

#### Acceptance Criteria:

A dashboard that refreshes twice a day.

### 2.
#### Role: Sales Manager

Request: Dashboard overview of overall internet sales.

User value: Able to compare actual company sales vs target sales set by the business.

#### Acceptance Criteria:

A dashboard with a KPI showing the actual sales value vs the target sales.

### 3.
#### Role: Sales Rep

Request: Detailed overview of internet sales by customer.

User value: Can follow up on highest spending customers and curate a strategy to upsell them on more products. We can also see which customers we can target for more business.

#### Acceptance Criteria

A dashboard that allows us to filter data for each customer.

### 4. 
#### Role: Sales Rep

Request: Detailed overview of internet sales by product.

User value: Can follow up on the most popular products so we can market them to more customers. 

#### Acceptance Criteria

A dashboard that allows us to filter data for each product.



### Data ETL and Cleaning Steps

- Step 1: 
The Dataset came in Excel format with four tables including the Date, Product, Customers, and FactInternetsales tables. 

- Step 2:
A budget table in Excel was also provided. The budget table lacked some values, so I created my own.

- Step 3: 
Created a GearUpCycling database in SQL Server and loaded all tables associated with this project.

- Step 4: 
This project has one FactInternetSales table and three dimension tables for Customer, Product, and Date.

- Step 5: 
Upon loading the required database, I cleaned the tables to my specifications.

- Step 6: 
For all tables, I picked only the columns I would use in this project.

- Step 7: 
Based on the Project requirements. I built 3 dashboards:

#### Dashboard Features

- Dashboard 1

•	Actual vs Target visual

•	Sales and Budget by Month

•	Sales by Top 10 products

•	Top 20 cities by sales

![G1](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/58569f2c-5548-4337-9ff1-09ce070afb41)

 
- Dashboard 2

•	Top 10 Products by Orders

•	Sales by Product Category

•	Product Subcategory sales

•	Highest-selling product by product category
 
![G2](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/69749f5a-ef38-4333-8157-6995b16d5833)


- Dashboard 3

•	Top 10 Customers by Sales

•	Gender analysis by sales

•	Customers by product category
 
![G3](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/e0219173-3cde-4410-8f21-1534f45f5913)



###	Key metrics

•	Total Sales

    Total Sales = SUM(FactInternetSales[SalesAmount])

•	Total Orders

    Total Orders = COUNT(FactInternetSales[CustomerKey])

•	Highest-selling Product

    Highest-Selling Product = 
        MAXX(
            VALUES(DimProduct[ProductName]),
            [Total Sales]
            )

•	Budget Total

    Budget Total = SUM('FactBudget'[Budget])

###	Insights

- Sales Information

1.	The total sales amount from internet sales was $22,239,730 against a budgeted revenue of $39,450,000. This shows that the company is -43.6% of its three-year target budget. A quick filter on months shows the months in which revenue targets were not met and their variances. 

2.	Although the 3-year target budget was not met. The business made a revenue of $16,351,550 in 2020 against a budget of $15,300,000.

3.	 The best-selling product was the Mountain-200 Black, 46 with sales totaling $1,371,420. 

4.	London was the top-selling city with a revenue of $693,518.

5.	There is a total of  58,168 orders and 18,484 customers over three years. This indicates that we have only had repeat customers and no new ones during this period.

- Product Information

1.	On total sales per product category, Bikes brought in the most sales at $21,199,198. Accessories were second with total sales amounting to $700,760, and Total Clothing sales were $339,773.

2.	The Mountain-200 Black, 46 had the most orders with 619 total orders.

3.	Bikes had the highest-selling products by product category with $1,371,420. Followed by Accessories with $78,027, and Clothing with $25,406.

4.	Road bikes are the most popular product with sales of $8,750,977, second is Mountain bikes with $8,603,420, and Touring bikes with $3,844,801.

5.	For the year 2021, we only have data for January, therefore we can only show the sales of Accessories and Clothing.


- Customer Information

1.	Jordan Turner is our top customer with sales of $15,999, with Maurice Shaun in second with $12,910 and Janet Munoz with $12,489.

2.	We have slightly more female customers as they make up 50.49% of our customer base and males make up 49.51%.

3.	Accessories are the most ordered product category with 36,092 orders. Followed by Bikes with 12975 orders and finally Clothing with 9101 orders over the past three years.


- Recommendations

1. Investigate innovative marketing strategies aimed at attracting and acquiring new clients effectively.

2. Analyze the factors that contribute to London and Paris being preferred cities among customers and replicate successful strategies in other key customer locations.

3. Leverage insights from sales data indicating a strong preference for cycling within the company's sales regions. Enhance sales performance by expanding cycling product offerings and tailoring marketing initiatives to target this specific market segment.

4. Harness customer and product data to develop targeted marketing strategies focused on retaining high-value customers and enhancing overall customer loyalty.


