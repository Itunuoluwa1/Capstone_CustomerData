# Capstone Customer Data
### This is where I documented the Customer Segmentation for a Subscription Service
### Project Title: Customer Segmentation for a Subscription Service
**Summary:** This project involves analyzing customer data for a subscription service to identify segments and trends. Your goal is to understand customer behavior, track subscription types, and identify key trends in cancellations and renewals. The final deliverable is a Power BI dashboard that presents your analysis.

**Parts in the documentation**\
[EXCEL](#excel)

## EXCEL
- Analyze customer data using pivot tables to find subscription patterns.
- Calculate the average subscription duration and identify the most popular subscription types.
- Create any other interesting reports.

[Remove Duplicate](#remove-duplicate)\
[Add Column](#add-column)\
[Pivot Table](#pivot-table)\
[Excel Functions](excel-functions)

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






