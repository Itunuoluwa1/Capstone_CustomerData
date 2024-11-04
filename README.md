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

[Remove Duplicate](#remove-duplicate)

#### Remove Duplicate
First and foremost, in my dataset I removed duplicate to impact the quality, accuracy nad reliability of my data. After removing duplicates in my data, the data of 75,000 rows was reduced to 33,787 rows removing 41,213 rows, therefore, making the data more accurate.

#### Add Column
Knowing that I would be needing subscription duration and there is no column of subscription duration in my table, I created a new column naming it Subscription Duration and then I defined it's values as the difference between SubscriptionStart and SubscriptionEnd column
```EXCEL
F2 - E2
```

#### Pivot Table
I used pivot table and excel functions ton uncover key insight from the Customer data in the Capstone project. Pivot table is used for summarization of data in the project in order to uncover insights for reporting.\
From the question I'm supposed to use Pivot Table to find subscription pattern.
