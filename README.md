# Capstone Customer Data
### This is where I documented the Customer Segmentation for a Subscription Service
### Project Title: Customer Segmentation for a Subscription Service
**Summary:** This project involves analyzing customer data for a subscription service to identify segments and trends. Your goal is to understand customer behavior, track subscription types, and identify key trends in cancellations and renewals. The final deliverable is a Power BI dashboard that presents your analysis.

**Parts in the documentation**\
[EXCEL](#excel)\
[SQL](#sql)\
[Power BI](#power-bi)

## EXCEL
- Analyze customer data using pivot tables to find subscription patterns.
- Calculate the average subscription duration and identify the most popular subscription types.
- Create any other interesting reports.

[Remove Duplicate](#remove-duplicate)\
[Add Column](#add-column)\
[Pivot Table](#pivot-table)\
[Excel Functions](#excel-functions)\
[Interesting Report](#interesting-report)

#### Remove Duplicate
First and foremost, in my dataset I removed duplicate to impact the quality, accuracy and reliability of my data. After removing duplicates in my data, the data of 75,000 rows was reduced to 33,787 rows removing 41,213 rows, therefore, making the data more accurate.

#### Add Column
Knowing that I would be needing subscription duration and there is no column of subscription duration in my table, I created a new column naming it Subscription Duration and then I defined it's values as the difference between SubscriptionStart and SubscriptionEnd column.
```EXCEL
= F2 - E2
```

#### Pivot Table
I used pivot table and excel functions ton uncover key insight from the Customer data in the Capstone project. Pivot table is used for summarization of data in the project in order to uncover insights for reporting.\
From the question I'm supposed to use Pivot Table to find subscription pattern.

1. **Subscription Type By Average Subscription Duration:**
A pivot table of subscription type by average subscription duration with pivot chart included.\
![Cus Data Sub type by avg sub duration](https://github.com/user-attachments/assets/3c96d359-2c20-49a8-a63b-b31862b8839f)

2. **Subscription Type By Sum Of Revenue:**
A pivot table of subscription type by sum of revenue with pivot chart included.\
![Cus Data sub type by sum of rev](https://github.com/user-attachments/assets/294157e5-7878-47c6-a3b5-e319efa77b89)

3. **Subscription Type and Region By Sum of Revenue:**
A pivot table of subscription type and region by sum of revenue with pivot chart and slicer included. The slicer is used to filter the data in the pivot table and chart to only the selected data.\
![Cus Data Sub type, region and rev](https://github.com/user-attachments/assets/bc977feb-8359-4b85-88b6-45f5909675a8)\
Now the report after using the region slicer.\
![Cus Data East](https://github.com/user-attachments/assets/af89af92-5f47-4214-9fc5-2580cc6cc2bf)
![Cus Data North](https://github.com/user-attachments/assets/4c9c8b1c-2984-44e5-8e78-7f5586564394)
![Cus Data South](https://github.com/user-attachments/assets/67320051-4a30-4744-9d3a-6447f1be17b2)
![Cus Data West](https://github.com/user-attachments/assets/b50a72ea-32b5-4f93-9335-dc05707f9964)

4. **Subsciption Type, Cancelled Or Not By Sum Of Revenue:**
A pivot table of subscription type, cancelled or not by sum of revenue with pivot chart and slicer included. The slicer is used to filter the data in the pivot table and chart to only the selected data. I added a subscription duration slicer.\
![Cus data, canceled by sum of rev](https://github.com/user-attachments/assets/04b02da7-ea12-4e7d-8fb1-88fedd4c93bb)\
Now the report after using the subscription duration slicer.\
![Cus Data 365](https://github.com/user-attachments/assets/69d04175-53b0-4263-a4e0-63ee456bd181)
![Cus Data 366](https://github.com/user-attachments/assets/ed163157-6863-49b7-9464-60cd52abf300)

5. **Subscription Type By Number Of Customers:**
This pivot table shows the subcription type by the number of customers that used the subscription type. Pivot chart included.\
![Cus Data sub type by cus count](https://github.com/user-attachments/assets/bfc9380d-616e-487b-ae0a-191ef50bbff9)

#### Excel Functions
I used excel functions to make certain calculations and summarization in the dataset to attain insights from the project.

1. **Average Subscription Duration:** I used the subscription duration column that I created with AVERAGE excel function to get the average subscription duration.
```EXCEL
= AVERAGE(I2:I33788)
```
![Cus Data Avg sub duration](https://github.com/user-attachments/assets/aef83405-2ff1-4a11-9f27-2dbfbb4c2fcb)\
This shows that the avearge subscription duration of the data is 365.3498387.

2. **Most Popular Subsription Types:** I used excel functions to get the most popular subscription type from the dataset.
```EXCEL
= INDEX(D2:D33788, MODE(MATCH(D2:D33788, D2:D33788, 0)))
```
![Cus Data Most sub type](https://github.com/user-attachments/assets/74db1f6c-e87e-4af9-acd0-3e7593d0b1f5)

#### Interesting Report
My personal report was a pivot table on subscription type, canceled by canceled count with pivot chart included.\
This pivot table shows the number of people that canceled or not in each of the subscription types.\
![Sub type canceled by canceled count report](https://github.com/user-attachments/assets/3351b0d1-fd59-4176-b192-bbc3d77ebb24)


## SQL
- Total number of customers from each region.
- Most popular subscription type by the number of customers.
- Customers who canceled their subscription within 6 months.
- Average subscription duration for all customers.
- Customers with subscriptions longer than 12 months.
- Total revenue by subscription type.
- Top 3 regions by subscription cancellations.
- Total number of active and canceled subscriptions.

[Data Import](#data-import)\
[Create Database](#create-database)\
[Select Statement](#select-statement)\
[Actual Tasks](#actual-tasks)

#### Data Import
The raw Capstone Data is an excel file that has two tables in two different worksheet and cannot be imported into sql ordinarily. Firstly, I opened the file in excel and removed duplicate from the data to impact quality and accuracy of my data. Then, I saved each of the worksheet as a CSV(Comma Delimited) file and was eventually having two files; one for Sales Data and the other for Customer Data. This way is would be possible to insert the data. Now I inserted the data by clicking import flat file and ensured to change the datatype where necessary and was able to insert the data successfully.

#### Create Database
A database is an organized collection of data that is stored and managed in a structured way to allow for easy access, retrieval and manipulation. I created a database for my capstone data. Also note that SQL is not case-sensitive so I didn't neccesarily use one casing.
```SQL
CREATE DATABASE CAPSTONE_DB
```

#### Select Statement
A select statement is a type of Data Query Language(DQL). A DQL is used to fetch the data from the database. I selected the Customer Data table in order to preview it.
```SQL
select * from [dbo].[CustomerData]
```
![sql cus data table](https://github.com/user-attachments/assets/b06b4256-558c-4cf3-a47b-cadb29f39029)

#### Actual Tasks
1. **Total number of customers from each region:** This displays the number of customers in each of regions.\
The Query:
```SQL
select COUNT(*) as TotalCustomers, Region from [dbo].[CustomerData]
group by region
```
The Table:\
![sql cus data 1](https://github.com/user-attachments/assets/3ab7d8af-b941-43e3-abf4-4b2d5567db5d)

2. **Most popular subscription type by the number of customers**\
The Query:
```SQL
select top 1 COUNT(subscriptiontype) as TotalCustomers, SubscriptionType from customerdata
group by subscriptiontype
```
The Table:\
![sql cus data 2](https://github.com/user-attachments/assets/aae6337a-661e-47f6-b3d5-9204c910875e)

3. **Customers who canceled their subscription within 6 months:** Firstly, I created a view of Subscription Duration that was called while finding the customers who canceled their subscription. This view contains two columns of customerID and SubscriptionDuration grouped by month.\
The view query:
```SQL
create view vw_SubscriptionDuration
as
select CustomerId, DATEDIFF(MONTH, subscriptionstart, subscriptionend) as SubscriptionDuration from customerdata
```
![cus data sql view](https://github.com/user-attachments/assets/16d13607-971d-457c-b902-af6529355fdb)\
Now after creating the view, to get customers who canceled their subscription within 6 months. The Query:\
```SQL
select * from vw_SubscriptionDuration
where SubscriptionDuration <= 6
```
The Table:\
![sql cus data 3](https://github.com/user-attachments/assets/df9543e8-d812-459d-aa96-0e5350838298)\
We can see that there is no value in the table which means no customer canceled their subscription within 6 months.

4. **Average subscription duration for all customers:** I did this in two forms, I found average subscription days duration and also found average subscription month duration.\
The Query for days:
```SQL
select
  AVG(DATEDIFF(DAY,subscriptionstart,subscriptionend))
  as AverageDuration
from CustomerData
```
![sql cus data 4a days](https://github.com/user-attachments/assets/a81bfaa8-aeb7-4b25-9def-bb38257a7c55)\
I used the view that was created in question 3. The Query for month:
```SQL
select
  AVG(subscriptionduration)
  as AverageDuration
from vw_SubscriptionDuration
```
![sql cus data 4b month](https://github.com/user-attachments/assets/65e1d4d2-0c00-44a3-b714-e97ace99220a)

5. **Customers with subscriptions longer than 12 months:** I used the view that I created in question 3.\
The Query:
```SQL
select * from vw_SubscriptionDuration
where SubscriptionDuration > 12
```
The Table:\
![sql cus data 5](https://github.com/user-attachments/assets/03d3ae74-e0ea-4a77-b400-b95333770938)\
There is no value in the table showing that there was no customer whose subscription lasted longer than 12 months.

6. **Total revenue by subscription type:**\
The Query:
```SQL
select SUM(revenue) as TotalRevenue, SubscriptionType from CustomerData
group by SubscriptionType
```
The Table:\
![sql cus data 6](https://github.com/user-attachments/assets/17110b10-f18b-464c-8615-02941f072aec)

7. **Top 3 regions by subscription cancellations**
The Query:
```SQL
select top 3 Region, canceled from CustomerData 
```
In my CANCELED column, just as in logic circuits, my TRUE is the same as 1 and FALSE is the same as 0 and this is because I saved the datatype of the canceled column as bit and not a string i.e varchar or nvarchar. 
The Table:\
![sql cus data 7](https://github.com/user-attachments/assets/12dd4a35-08c8-4931-9193-9f2e34fd1a9d)

8. **Total number of active and canceled subscriptions**
The Query:
```SQL
select COUNT(canceled) as TotalCustomers, Canceled from customerdata
group by canceled
```
The Table:\
![sql cus data 8](https://github.com/user-attachments/assets/1ffb831a-28de-460f-a7a9-ea7874b80e9a)

## Power BI
Build a Power BI dashboard that visualizes key customer segments, cancellations, and subscription trends. Include slicers for interactive analysis.

Power BI is a data visualization tool that converts data from different sources to make an interactive dashboard and BI reports.

#### Data Import
I imported my capstone data into my Power BI desktop and clicked transform data. In the transform state I removed duplicates from my data to make it more accurate. \
I also added a custom column of Subsription Duration because I know that I would be needing it in my report.
```
= Duration.Days([SubscriptionEnd]) - ([SunscriptionStart])
```
 After doing this I loaded my data.

#### Measures 
I created measures within my Customer Data.\
Total Customers
```
COUNT(CustomerData[CustomerID])
```
Total Sales Revenue
```
SUM(CustomerData[Revenue])
```

#### Excel Insights
I created a dashboard to visualize all that I did in my excel on this capstone customer data.\
![BI Cus Excel](https://github.com/user-attachments/assets/edbbef9e-9281-4bb2-aa77-69b29cd1f43c)

#### SQL Insights
To visualize all that I did in SQL on this my capstone customer data, I made all my question queries into views and then imported the views into my PowerBI and then visualized. \
![BI Cus SQL](https://github.com/user-attachments/assets/b43a8068-7f63-4e00-801c-77d0f5a9798a)

#### Customer Segments
This is a dashboard that visualizes interactions in the customer data. In this dashboard, I included slicers: The Region Slicer, Cancellation Slicer and Subscription Type Slicer. I also used filters majorly the Top N filter to visualize Top 10 and Top 1 vivisuals even Bottom values.\
![BI Cus Dash](https://github.com/user-attachments/assets/9dc6a53e-40d1-442e-8b8e-e5c4b4979e78)

#### Cancellation And Subscription Trend
This is the dashboard that show the trend ofg cancellation and subscription in the capstone Customer data set.\
![BI Cus Trend](https://github.com/user-attachments/assets/efe8304c-b6b5-494e-b8cc-1105e38baa08)






