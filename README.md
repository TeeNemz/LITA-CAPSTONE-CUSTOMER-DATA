# LITA-CAPSTONE-CUSTOMER-DATA

## PROJECT TITLE: CUSTOMER DATA
---

## TABLE OF CONTENT
---

[PROJECT OVERVIEW](#Project-overview)

[PROJECT OBJECTIVES](#Product-Objectives)

[DATA SOURCE](#Data-source)

[DATA DESCRIPTION](#Data-description)

[TOOLS USED](#Tools-used)

[DATA CLEANING AND PREPARATIONS](#Data-cleaning-and-preparations)

[EXPLORATORY DATA ANALYSIS](#Exploratory-data-analysis)

[DATA ANALYSIS](#Data-analysis)

[DATA VISUALIZATION](#Data-visualization)

[KEY INSIGHTS AND INFERENCE](#Key-insights-and-inference)

[RECOMMENDATIONS](#Recommendations)

[CONCLUSION](#Conclusion)


### PROJECT OVERVIEW
---

This Data Analysis project involves analyzing customer data for a subscription service to identify segments and trends. By analyzing the various parameters in the data received we seek to understand customer behavior, track subscription types, and identify key trends in cancellations and renewals.

### PROJECT OBJECTIVES

The primary aim of this project is to 
- Understand customer behaviour.
- Track Subscription types.
- Identify key trends in cancellation and renewals


### DATA SOURCE
---

The primary source of Data used here is Customer data.xlsx, it was provided by the instructors of Incubator hub for the Ladies In Tech program



### DATA DESCRIPTION
---

The dataset includes the following:

- Customer ID: distinct code given to each customers used for each subscription

- Customer Name: Name unique to each customers used for multiple subsccription

- Region: Location of Subscription (East, West, South and North)

- Subscription Type: Specific subscription choice

- Subscription Start: Date when subscription begins

- Subscription End: Date when subscriptin finishes

- Cancellation: No longer subscribes

- Revenue: Amount generated from subscription

- Duration of subscription: Length period of subscription


### TOOLS USED
---

- Microsoft Excel

a. For Data Cleaning

b. For Analysis

c. For Visualization

- SQL - Structured Query Language for querying of Data

- Microsoft Power Business Intelligence ( POWER BI) for Visualizations and creation of compelling insights

- Github for Portfolio Building

  
### DATA CLEANING AND PREPARATIONS
---

a. Data Cleaning

Using Microsoft Excel, all duplicated data were removed by going to the Data tab > Data tools > Remove duplicates

b. Data Importation

- A copy of the cleaned data was converted to CSV flat and imported into SQL Server Management Studio 20
  
- A copy of the cleaned data was also imported into Power BI, the data was transformed and appropriate data types were chosen and applied

c. Data Visualization

- In Microsoft Excel, Pivot tables were used to summarize the data and Bar charts were created to visually represent key insights.

- In SQL Server Management Studio, codes were written to provide answers to research questions and screenshots of the output was taken.

- In Power BI, several visualizations were made using Bar charts, tables, cards, Pie charts, Slicers, etc.


### EXPLORATORY DATA ANALYSIS:
---

EDA involved the exploring of Data to answer some questions about the Data, These questions include;

A. MICROSOFT EXCEL:

Pivot table was used analyze customer data to find

- subscription patterns:

- Determine Average subscription duration

- Determine most popular subscription type
  
- Total revenue generated.

B. Structured Query Language (SQL)

Codes were written to validate these queries

- retrieve the total number of customers from each region.
  
- find the most popular subscription type by the number of customers.
  
- find customers who canceled their subscription within 6 months.
  
- calculate the average subscription duration for all customers.

- find customers with subscriptions longer than 12 months.

- calculate total revenue by subscription type.

- find the top 3 regions by subscription cancellations.

- find the total number of active and canceled subscriptions.

C. POWER BI: Create a Dashboard that visualizes the insights found in Excel and SQL, the dashboard should visualize key customer segments, 
cancellations, and subscription trends. 
  

### DATA ANALYSIS
---

A. MICROSOFT EXCEL:

Average subscription duration per customer. Where "I" is for column with duration in days

```
=AVERAGE(I2:I33788)
```

B. Structured Query Language (SQL):

The following queries were written to analyse the Customer data

``` SQL

SELECT * FROM [dbo].[Capstone customer main]

```
a. Retrieve the total number of customers from each region
```
SELECT Region, Count(distinct CustomerID) AS Total_customers
FROM [dbo].[Capstone customer main]
GROUP BY Region
```

b. Find the most popular subscription type by the number of customers.
```
SELECT Top 1 subscriptiontype, count(distinct customerID) AS Total_customers
FROM [dbo].[Capstone customer main]
GROUP BY Subscriptiontype
ORDER BY Total_customers DESC

```
c. Find customers who canceled their subscription within 6 months.
```
SELECT CustomerID
FROM [dbo].[Capstone customer main]
WHERE Datediff(Month, Subscriptionstart, subscriptionend) <= 6

```
d. Calculate the average subscription duration for all customers
```

SELECT avg( Datediff(day, Subscriptionstart, subscriptionend))  AS Avg_subscription_duration
FROM [dbo].[Capstone customer main]

```
e. Find customers with subscriptions longer than 12 months.
```

SELECT CustomerID
FROM [dbo].[Capstone customer main]
WHERE Datediff(Month, Subscriptionstart, subscriptionend) > 12

```
f. Calculate total revenue by subscription type
```

SELECT Subscriptiontype, sum(revenue) AS Total_revenue
FROM [dbo].[Capstone customer main]
GROUP BY Subscriptiontype

```
g. Find the total number of active and canceled subscriptions
```
SELECT 
  SUM(CASE WHEN Canceled = 0 THEN 1 ELSE 0 END) AS ActiveSubscriptions,
  SUM(CASE WHEN Canceled = 1 THEN 1 ELSE 0 END) AS CanceledSubscriptions
FROM [dbo].[Capstone customer main]

```
h. Find the top 3 regions by subscription cancellations

```

SELECT TOP 3 Region, COUNT(CustomerID) AS CancellationCount
FROM [dbo].[Capstone customer main]
WHERE Canceled = 1
GROUP BY Region
ORDER BY CancellationCount DESC
```

### DATA VISUALIZATION
---

MICROSOFT EXCEL INSIGHTS AND VISUALIZATIONS


![Customer data pivot table](https://github.com/user-attachments/assets/bd515e3b-ffff-4d9c-9d7b-97290e7dacf3)


![Customer pivot chart](https://github.com/user-attachments/assets/8bc8d124-9e6d-4f35-aad5-8aeb43addf8e)



POWER BI INSIGHTS AND VISUALIZATIONS



![Customer data BI 1](https://github.com/user-attachments/assets/8ebd0cd7-78e9-4e1b-bbf9-2e5b436c7393)


![Customer Bi 2023](https://github.com/user-attachments/assets/f66fbdc4-cee4-46a2-a261-ff2c8d67c1e2)



### KEY INSIGHTS AND INFERENCE:
---

- Subscription Pattern:
  
From the analysis an  impressive total of $68M of Revenue was generated, with the 'Basic' subscription type having the highest number of subscribers and total revenue, thus making it the most popular Subscription plan. 'Premium' plan was the second with 'Standard' plan being the least.


The 'Basic' plan's popularity can be attributed to its attractive pricing, suitable features, or effective marketing strategies.


- Regional Perfomance:
  
The 'East' region is observed to have the highest number of subscribers, active subscription and total revenue. However, there is lack of subscription type diversification among the subscribers. For instance: Premium subscription is popular in the South, Standard subscription is popular in the West and Basic subscription type in both East and North region. This might be due to factors like income levels, awareness campaigns, or regional marketing initiatives.

- Subscription period:

Most of subscription are active for an average period of 365 days (1 year), rarely is it below or beyond that duration. This indicates a high level of satisfaction and trust. 

- Cancellation pattern:

A total of 15,175 customers cancelled their subscription with 18,612 retaining their active subscription.  It was also worthy to note that each Cancellation was done on the same day as when the customer first subscribed as seen in the  Power Bi Visualization. 

This can be attributed to dissatisfaction with services or features, Cost or pricing concerns, Changes in personal or business needs, Competitor offerings or alternatives, Lack of engagement or communication. 

Thus effort should be made during the year and intensified towards the end of each subscription year to enhance customer support and feedback mechanisms, Review pricing strategies and consider tiered plans, Develop targeted retention campaigns, Monitor competitor activity and market trends, Foster stronger customer relationships through regular communication.





### RECOMMENDATIONS:
---

I. Optimize Subscription Strategy:

- Simplify and Highlight Affordability of the Basic Subscription: Continue emphasizing the simplicity and affordability of the popular Basic subscription in marketing efforts.
  
- Emphasize the benefits of other subscription plans : Highlight the added benefits of subscribing to the Standard and Premium plans.

- Customizable Add-Ons:: Introduce optional upgrades to enhance the Basic plan, allowing customers to tailor their experience without added complexity.

  
II. Nurture Customer Loyalty:

- Reward Long-Term Commitment: Develop a loyalty program that incentivizes continued subscription, offering benefits such as: Renewal discounts,  Exclusive content for loyal subscribers (e.g., after one year)

- Authentic Endorsements_: Showcase testimonials from satisfied customers, particularly from the East region, in marketing materials to Build trust and attract new subscribers
  
III. Regional marketing strategies: 

- Exclusive East Region Offers_: Develop targeted promotions and incentives to further leverage the East region's strong commitment, driving additional growth.

- Community Connection: Design and implement community-focused initiatives and events in the East and in other regions. This is with the aim of Fostering a sense of community, Strengthening customer bonds and Building brand loyalty.
  
IV. Enhance Customer Experience:

- Streamline Onboarding:  Optimize the new subscriber onboarding process for a seamless and informative introduction, highlighting subscription value from day one.

- Proactive Communication: Maintain regular updates and engagement with subscribers, informing them of  New features, Enhancements, Exclusive benefits

V. Minimize Cancellations and Boost Re-engagement:

- Understand Cancellation Motivations: Gather insights through surveys or interviews with cancelled subscribers to identify key reasons and address underlying issues.
  
- Win-Back Initiatives_: Launch targeted re-engagement campaigns focusing on former subscribers, highlighting Personalized offers, New features and enhancements, Exclusive benefits
  
VI. Time-Limited Offers: Launch seasonal promotions, Holiday-themed promotions, Limited-time discounts, Bundled packages to  Drive new subscriptions, Increase renewals and Capitalize on peak demand periods


### CONCLUSION:

By implementing these recommendations, the company can enhance customer loyalty, reduce cancellations, and ultimately drive revenue growth while maintaining a strong foundation built on subscriber satisfaction.
