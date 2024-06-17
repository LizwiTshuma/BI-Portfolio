
# Bank Customer Churn 

###	Problem Statement

-	The General manager of ABC Bank wants to see customer attrition figures. These will be used to implement marketing strategies to gain the lowest churn rate from their customers.

###	Proposed Solution

-	Design and build two dashboards to analyze customer churn by demographics and account holder information.

#### Dashboard Features

a.	Total Customer details 

b.	Total Churned customer details

c.	Customers by gender, country, age group, and tenure.

d.	Target churn rate vs actual churn rate for that period.

###	User Story
1.	
#### Role: General Manager	

Request: Dashboard overview of Account Analysis.

User value: Able to follow up on products offered and which ones have the least churn.

Acceptance Criteria:

A dashboard that refreshes once a month. With a KPI that shows the company's target churn rate vs the actual rate.

2.	
#### Role: Marketing Manager	

Request: Dashboard overview bank customer demographics.

User value: Able to compare the actual churn rate vs the target rate set by the business.

Acceptance Criteria:

A dashboard with a KPI showing the actual churn rate vs the target rate.

3.	
#### Role: General Manager

Request: A chart that shows customer retention by account balance.	

User value: They can follow up on the customers they can retain and curate products that will make them stay with the bank longer.

Acceptance Criteria:

A chart that allows us to filter data by age group and account balance.

a.	Customer Churn rate

b.	Customer retention rate

c.	Target rate vs Actual Churn rate

d.	Churn Rate by Tenure

###	 Data ETL and Cleaning Steps Followed


- Step 1: The data came in a *.csv file format from a GitHub repository.

- Step 2: Deleted the Changed Type step and Promoted Headers in Power Query.

- Step 3: Removed the Estimated salary column because we have the current balance of the account holder.

- Step 4: Renamed the columns with more meaningful titles.

- Step 5: Substituted 1 and 0 in the churn column with meaningful values that can be used in our visuals.

- Step 6: Where we have the value of 0, we changed it to “Not Churned” and where we have 1, we changed it to “Churned”.

- Step 7: For the Product Number column, we substituted 1-4 with Prod 1, Prod 2, Prod 3, and Prod 4. 

- Step 8: Values changed were Activity, churn status, and Credit card possession from 1 and 0 to “Active” and “Inactive”, “Churned” and “Not churned” and “Owned” and “Not Owned” respectively.

- Step 9: Created a column for Age Groups.

- Step 10: Created an additional column for Credit Score Group.

- Step 11: Created an additional column for Account Balance Group.

- Step 12: Referenced our data table to create ID columns for the Age Group, Credit Score, and Balance Group columns that we used in our sort order for our visuals.

- Step 13: Created a custom column for the Minimum Churn Rate percentage = 0%

- Step 14: Created a custom column for the Maximum Churn Rate percentage = 100%

- Step 15: Created a custom column for the Target Churn Rate percentage = 12%




###	Key metrics

•	Total Customers 

    Total Customers = COUNT('Customer Data'[Customer ID])

•	Total Churned Customers 

    Total Churned Customers = 
    CALCULATE(
         COUNT('Customer Data'[Customer ID]),
                'Customer Data'[Churn] = "Churned"
            )

•	Churn rate

    Churn Rate = DIVIDE([Total Churned Customers],[Total Customers])


### Insights


 ![p5](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/6cdf841a-5a43-4630-bce0-b52c72d098b0)


- Demographic Analysis

•	Women have a higher churn rate than men at 25.1% and men at 16.5%.

•	Customers living in Germany leave the bank the most with a 32.4% churn whereas those living in France and Spain are at 16.2% and 16.7% respectively.

•	People aged 51-60 have the highest leaving rate at 56.2%. This indicates that older individuals are more likely to shop for better rates, services, and products different banks offer.

•	Customers who have been with the bank for less than two years tend to leave more than those who have been around for longer periods.


![Acc Information #2](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/56daf9ef-846e-451d-96ec-b7e42da5a9c3)
 

- Account Analysis

•	Whether or not a customer owns a credit card doesn’t seem to affect the churn rate as it stands at 20.8% and 20.2% for those who don’t own a credit card and those who do respectively.

•	Customers with an account balance between 1k-10k leave the bank more than others with a churn of 100%. There is a major problem with the products provided by the company to people with that balance in their accounts. This shows that customers are looking for better value elsewhere.

•	People with accounts greater than 200k are also looking elsewhere for better quality products offered with a churn rate of 55.9%.

•	Customers with a credit score of 400 or less have a 100% churn rate.

•	Of Prod 1, Prod 2, Prod 3, and Prod 4 offered by the bank, customers who have subscribed to Prod 4 have a 100% churn rate. Followed by Prod 3 at 82.7%, Prod 1 at 27.7% and Prod 2 at 7.6%. Product 2 is the best-selling one.


### Recommendations

•	The bank needs to understand why customers with account balances of 1k-10k are leaving them. This could be younger people who can’t seem to cope with bank fees imposed on their smaller accounts.

•	 Product 4 has a problem. The marketing team needs to restructure it and make it more attractive to customers.

•	Product 3 also needs to be revisited by the company and restructured to meet the needs of customers. They could reduce the cost or add more benefits to the product.

•	The bank needs to curate products that appeal to older customers, specifically between the ages of 51-60. These customers usually have larger account balances and make more money. This also shows that they are looking for better deals with other banks which we are failing to offer.



