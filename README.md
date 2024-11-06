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

A. MICROSOFT EXCEL:

Average subscription duration per customer. Where "I" is for column with duration in days

```
=AVERAGE(I2:I33788)
```

B. Structured Query Language (SQL):

The following queries were written to analyse the Customer data
