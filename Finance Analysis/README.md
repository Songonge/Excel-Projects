# Project: Finance Analytics Case Study
----

## Project Overview
This project, completed in **Excel**, analyzes customer income and spending behaviors using a dataset containing demographic information (dim_customers) and financial transactions (fact_spends). The entire workflow, from data cleaning to insight generation and dashboard creation, was completed in **Microsoft Excel**.

The goal was to analyze how spending patterns differ among customers from various income brackets. Then, answer key business questions about customer demographics, income, and spending patterns across categories, payment methods, cities, and occupations.

## Dataset Description
The dataset contains two tables as described below:  


### The Dimension Table
This table contained `4000` rows and `10` columns described as follows:  
* **dim_customers**
  * _CustomerID_: Unique ID assigned to each customer. This is the Primary Key of this table.
  * _AgeInterval_: Age interval category (21-24, 25-34, 35-45, 45+).
  * _Gender_: Gender of the customer (Male, Female).
  * _City_: Customer’s city in the USA.
  * _State_: Customer’s state in the USA.
  * _PostalCode_: Customer’s postal code in the USA.
  * _Region_: Customer’s Region in the USA.
  * _MaritalStatus_: Marital status (Single, Married).
  * _occupation_: Customer’s profession (IT, Business Owner, Freelancer, etc.).
  * _MonthlyIncome_: monthly income (in USD).

### The Fact Table
* **fact_spends**
This table contained `86400` rows and `5` columns described as follows:  
  * _CustomerID_: Unique ID of each customer, linking to the dim_customers table
  * _Month_: Month of spend (May–October).
  * _Category_: Spend category (Electronics, Apparel, Entertainment, Food, etc.).
  * _PaymentType_: Mode of payment (Debit Card, Credit Card, UPI, Net Banking).
  * _Spend_: Total amount spent.


## Methodology in Excel

### Part 1: Data Cleaning
The data cleaning tasks were completed in **Power Query**. The following tasks were completed:  
* Handled inconsistent naming.
* Assigned the correct data type to columns where necessary.
* Added a conditional column called _CustomAge_ as follows:
```
if  AgeInterval equals 21-24 then 23
if  AgeInterval equals 25-34 then 30
if  AgeInterval equals 35-45 then 40
else 50
```
* Created the AgeGroup column using the AgeInterval column as follows:
```
21-24: Young Adult
25-34: Adult
35-45: Middle-Age
45+: Senior
```
* Created the MonthNo column using the Month column. This was used later to sort the Month column.
* Transformed the month column entries to only keep the first three characters of the month name. This will allow aesthetic the name on the trend chart.
* Checked for missing values and duplicates. No missing or duplicate values were found.

### Part 2: Data Modeling
* Created a _One-to-Many_ relationship between dim_customers and fact_spends using the CustomerID column in both tables
* Sorted the month column by the MonthNo column 


### Part 3: Data Analysis


### Part 4: Data Visualization and Dashboarding
Designed slicers for filtering Age Group and Marital Status



