# HR Analytics Project

###	Problem Statement

The HR manager of a company wants to track the production levels of employees in the company. Using these insights, she wants to develop better practices and boost morale in the workplace.

###	Proposed Solution

We are going to build a dashboard that shows the employee activity over three months.


### Dashboard Features

####	User Requirements

### 1.
- Role: HR Manager

Request: Dashboard overview of the working preferences of employees.

User value: Will be able to structure work practices more efficiently. Know how to set up meetings and team-building schedules properly based on employee presence.	

- Acceptance Criteria:

A dashboard that shows work presence in the office and work-from-home preference.

### 2. 
- Role: HR Manager

Request: Sick leave of employees by week over three months.	

User value: Able to see how many employees are off sick by period. This will also allow the manager the ability to investigate any bugs, pandemics, etc.

- Acceptance Criteria:

A chart that shows sick leave percentage that updates every week.




###	 Data ETL and Cleaning Steps Followed

- Step 1: We got our data from a GitHub repository in Excel format.

- Step 2: We need to append our tables but the Excel sheets we’re getting our data from have columns with different headings.

- Step 3: Create a template to configure transformations once, then apply changes across all sheets.

- Step 4: Remove other columns except the data column.

- Step 5: Filter only one table to work with (April).

- Step 6: Expand the table to see all our columns and rows.

- Step 7: Now we must transform the table and those transformations will be carried across all other tables.

- Step 8: Delete the change type step because when we apply transformations to our April table, it will reference column names which is something we don’t want to do.

- Step 9: Use the first row as headers.

- Step 10: Remove the top row.

- Step 11: Change some column names to the correct names.

- Step 12: Unpivot other columns to get one date column.

- Step 13: We have non-data values in our unpivoted table, so we can filter those out. However, when we add a new sheet, we will have to go back to power query and repeat these steps. Instead, what we want to do is automate the entire system, therefore, we can change the data type which will give us errors. When we remove those errors, the same steps will be applied to any new data loaded.

- Step 14: Next, we create a parameter that will reference the current sheet we’re working with. In this case “Apr 2022”.

- Step 15: Our parameter name is Worksheet.

- Step 16: After creating all these steps, we need to create a function that will enable the reusability of our code. This way we can apply transformations across our other sheets without repeating the same steps.


###	Key metrics

-	Total Working Days. (Present-day - nonworkdays)

        Total Working Days = 

        var totaldays = COUNT('Final Data'[Value])
        var nonworkdays = 
        CALCULATE(
        COUNT('Final Data'[Value]), 
        'Final Data'[Value] IN {"WO", "HO"}
        )

        RETURN
        totaldays - nonworkdays

-	Present Days.

        Present Days = 

        var presentdays = 
        CALCULATE(
            COUNT('Final Data'[Value]),
            'Final Data'[Value] = "P"
                )

        RETURN
        presentdays + [WFH Count]

-	Presence %.

![Presence %](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/b4637882-7fe0-49b5-b2e4-c3a2a292ac94)


-	WFH calculated column.

        WFH Count = SUM('Final Data'[WFH Count])

-	Month- Year calculated column.

        Month-Year = FORMAT(STARTOFMONTH('Final Data'[Date]), "mmm-yy")

-	WFH % 

![WFH %](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/0b089c70-b34a-4bcb-aa98-f6eecae5f395)


-	Create a Sick Leave column and measure to show values like the WFH measure.

![SL %](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/72e9748a-9579-46ae-a8ea-142b9378cd38)


-	Create an alert to show if the threshold goes below 70%.

-	Configure a scheduled refresh.


### Insights


![HR](https://github.com/LizwiTshuma/BI-Portfolio/assets/170952348/2c4e1d88-d426-445e-b0de-1661b89a5a0f)



• The presence percentage of employees is high over three months at 92%. The work-from-home percentage is at 10.2% and the sick leave percentage is at 1.87%.

• It does, however, seem to be declining from April to June. This may be an indication that people are becoming more accustomed to working from their homes.

• The percentage of employees working from home increased over the three months, going from 9.59% to 18.06%.

• Sick leave days also seem to be increasing over 3 months going from 0% to 2.78%.  There is a change of season during this period, hence people might fall sick a lot more.

• Monday has the most employees present at work with 93.39%. If the business is implementing a hybrid work model to better utilize office space and enable better capacity planning. Mondays can be a day when office space is booked for use. 

• The business can also better manage rent and utility costs by having accurate numbers that influence the amount of space they need for their employees.

• Employees choose to work from home on Friday more than any other day with 13.17% of them working from home.

• The most sick leaves are taken on Mondays with 2.48%.


 


