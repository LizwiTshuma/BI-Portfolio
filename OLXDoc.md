# OLX Car Sales Data Project

### Problem Statement

A used car sales dealer wants to understand the figures around his business. What type of cars provide the most revenue? Which locations should he focus his business on?

### Proposed Solution

We are going to build three dashboards that drill down on used car sales by price, car details, and location.

### User Requirements

- Role: Owner

Request: Dashboard overview of overall sales.

User value: Able to follow up on cars sold and which ones are most popular amongst customers.

- Acceptance Criteria:

A dashboard that updates sales once a month.


- Role: Owner

Request: A dashboard that shows the car details of all the cars the business has sold.

User value: Able to analyze which makes and models of the cars we have make us the most money and what we can do to market them to more customers.

- Acceptance Criteria:

A dashboard that allows us to drill into each car make and get a view of sales.


- Role: Owner

Request: A dashboard that shows sales by location.

User value: Can follow up on locations with the highest spending customers and curate a strategy to get more customers in those locations.

- Acceptance Criteria:

A dashboard that allows us to filter data for each location.

#### Key focus

a.	Which car brand provides the highest revenue?

b.	Are local or imported cars more popular?

c.	The Average price for each brand of car.

d.	Popularity by brand and year model.


### Data ETL and Cleaning Steps Followed

- Step 1: Data came in Excel format from a Kaggle dataset.

- Step 2: Loaded data into Power Query Editor for cleaning.

- Step 3: Created a parameter for the data source.

- Step 4: Duplicated the file and converted the currency to rands to create a use case based in South Africa.

- Step 5: Removed columns that weren’t necessary for our analysis project. 

- Step 6: Removed all errors.

- Step 7: Created a table for car makes.

- Step 8: Created a primary and foreign key for each table to join the ‘Car Makes’ and Sales table.

###	Key metrics

•	Total revenue

        Total Revenue = SUM(olx_data[Price])

•	Total cars sold

        Total Cars Sold = COUNT(olx_data[Ad ID])

•	Average car price

        Average Car Price = AVERAGE(olx_data[Price])

•	Number of makes

        Number Of Make = COUNT(car_type[Make])

•	Number of models

        Number Of Model = DISTINCTCOUNT(olx_data[Model])

###	Insights
- Sales Overview

![p3](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/257551db-a58d-480f-a3c3-06a0fedb2a2e)

 
•	Toyota is the brand/make with the highest revenue with a total revenue of R71,117,686.

![M#2](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/5ed0547d-37e6-4427-a58d-0186fe759490)



•	Manual cars are more popular with 61.35% of them accounting for our sales.

•	Honda and Suzuki are among the top 3 selling cars with R65M and R63M is sales respectively.

- Car details Analysis
 
![M#1](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/191b11e8-b648-40cb-9e23-e2ca34ff33b2)



•	Local cars have higher sales as they account for 65.35% of our total sales.

•	Mercedes has the highest-priced car price average at R48,730.

•	Cars that use Petrol are popular among drivers with 8,979 of the cars the business has sold being those that use fuel. This is out of  9,174 total cars sold.

•	Cars produced in 2018 and 2021 have the highest sales. R22,889,649 and R22,396,010 respectively.

•	The City IVTEC and Corolla GLI are the highest-selling models. The City IVTEC with R27,906,380 and the Corolla GLI with R20,867,699.

•	Lahore is the most popular city for sales with R97M.

