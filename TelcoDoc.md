# Telco Customer Churn Data Project

###	Problem Statement

Telco, a telecommunications company, seeks to analyze customer attrition metrics. These insights will drive the development and implementation of targeted marketing strategies aimed at achieving the lowest possible churn rate among its customer base.

###	Proposed Solution

Develop two comprehensive dashboards designed to visually represent churn analytics across the business's demographic segments, service categories, and contract types.

### User Requirements

### 1. 
- Role: General Manager	

Request: A dashboard that shows customer demographics overview.	

User value: Able to follow up on the types of customers we are losing the most. That way we can see how to improve our products to continue retaining the customers we do have. 

- Acceptance Criteria:

A dashboard that shows the percentage of customers churned.

### 2.
- Role: General Manager	

Request: An overview of services offered analysis and how customers repond to them.	

User value: Able to see the services offered and how many customers we can retain by services offered.

- Acceptance Criteria:

A dashboard that shows data on service information.

### 3.
- Role: General Manager	

Request: Detailed overview of churn by customer.

User value: Able to see the customers we are losing by the products we offer.

- Acceptance Criteria:

A dashboard that allows us to filter data for each customer.

#### Key Focus:

a.	Customer Churn by Demographics.


b.	Customer retention rate.


c.	Churn rate by customer account.


d.	Churn by services offered.


###  Data ETL and Cleaning

- Step 1: Data came in a .csv file format from a Kaggle dataset.

- Step 2: Loaded data into Power Query for cleaning and transformation where I realized that we had null values in in the Total Charges column. These null values had 0 in the Tenure column, so I filtered them out.

- Step 3: The total rows of data for analysis dropped from 7043 to 7032 records.

- Step 4: Created a conditional column for tenure in months to group the data in the tenure column as follows:

        New customers- less than 12 months

        Existing customers- more than 12 but less than 36 months

        Old customers- more than 36 months

- Step 5: The Age range is as follows for the Senior Citizen Column:

        If value = 1 then “Yes”(Is a senior citizen)

        If value = 0 then “No”(Is not a senior citizen)


- Based on the Project requirements. I built two dashboards:

        Demographics Information

        Customer Account Information

###	Key metrics

i.	The key metrics I built for this data model were as follows:

-	Total Number of Customers

        Total No. Of Customers = COUNT('Telco Churn Data'[Customer ID])

-	Total Number of Churned Customers

        Total Churned Customers = 
        CALCULATE(
            [Total No. Of Customers],
            'Telco Churn Data'[Churn] = "Churned"
                )

-	Churn Rate %

        Churn Rate = DIVIDE([Total Churned Customers],[Total No. Of Customers])

![churn_rate](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/30fedd2f-599b-46ec-b657-31779c0a7968)


-	Average Monthly Charges

![avg_month_charge](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/a429fe21-a321-4552-86b7-35048f4fd368)


- Total Charges

![total_charge](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/e4e9c3af-d1d7-42d3-8f42-d780e52c9b69)






### Insights

 
- Demographics Analysis

![Telco 1 revised](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/2157f789-8932-420b-83e8-432694728f5d)



• There were 7032 customers this month. Of that value, 1869 churned. The churn rate was 26.58%. This means the retention rate is at 73.42%.

• The total revenue the business made was $16.06M and the revenue lost due to the churn rate was $2.86M.

• 50.24% of people who left the company were women and 49.76% were men.

• 64.21% of customers who churned don’t have a partner and 74.53% are not senior citizens. This indicates that the majority of customers who churn are younger, most likely single people.

• 82.56% of people who left have no dependents. This further highlights that younger people (youth) are churning more.

• 78.17% of customers who churn don’t have the online security package in their contract/subscription. This shows that our pricing models for this service might be too expensive/unattractive.

• New customers(who have been with the company for less than 12 months) churn the most.



 
- Customer Account Analysis


![Telco 2 revised](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/72b4dee3-311c-4ec9-b416-06e65dc0a424)


 
• Customers who have been with the company for less than a year have a churn rate of 55.48%. 

• The majority of people who were on a month-to-month contract had an 88.55% churn rate, which was the highest.

• 74.91% of customer churn were customers who had subscribed to paperless billing.

• Of the customers who churned, 45.29% used electronic check as a payment method. 19.20% used mailed checks, 16.73% automatic bank transfers, and 15.25% used credit cards.

• The average monthly charges were highest for customers on the month-to-month contract plan, but their total charges overall were low. On the other hand, customers who were on the two-year contract had the lost monthly average charges, however, their total charges were the highest.

• 69.4% of customers who used fiber optic left the company. This may suggest that Fiber Optic has an issue and any customers using it are more likely to churn.




### Recommendations

• Implement a focused strategy towards new clients with a tenure of less than 10 months. Offer them tailored services and incentives designed to foster long-term commitment to the company.

• Enhance the attractiveness of our one or two-year contract options, emphasizing their benefits over month-to-month contracts. This strategic approach aims to discourage premature terminations of contracts, thereby increasing customer retention and tenure.

• Drive customer confidence and trust by leveraging innovative solutions for online security measures. Investing in cutting-edge security technologies and practices bolsters customer assurance in our systems and strengthens overall trust in the company.

• Broaden our range of internet services to include diverse options beyond fiber optic and DSL. Offering customers a variety of service alternatives caters to different preferences and needs, promoting customer satisfaction and loyalty through personalized service offerings.
