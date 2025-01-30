# Project: Analyzing Sales from Different States in the United States

## Table of Content
1. [Introduction](#introduction)
2. [Project Description](#project-description)
3. [Project Aim](#project-aim)
4. [About the Dataset](#About-the-dataset)
5. [Importing the Dataset to Excel](#Importing-the-Dataset-to-Excel)
6. [Preparation of the Dataset: Cleaning and Transforming](#Preparation-of-the-Dataset-Cleaning-and-Transforming)
   * [Removed Duplicates](#Removed-Duplicates)
   * [Assigned the Correct Data Type to Columns](#Assigned-the-Correct-Data-Type-to-Columns)
   * [Added a New Column to the Table](#Added-a-New-Column-to-the-Table)
7. [Data Modeling in Excel](#Data-Modeling-in-Excel)
8. [Data Analysis in Excel](#Data-Analysis-in-Excel)
   * [Created DAX Measures for Analysis](#Created-DAX-Measures-for-Analysis)
   * [Created a Calculated Column](#Created-a-Calculated-Column)
9. [Data Visualization in Power BI](#Data-Visualization-in-Power-BI)
10. [Insights from the Data Analysis](#Insights-from-the-Data-Analysis)
11. [Recommendations from the Data Analysis](#Recommendations-from-the-Data-Analysis)
12. [Conclusion](#Conclusion)

## Introduction
The purpose of this report is to provide an in-depth analysis of the Superstore dataset, downloaded from Kaggle, using Excel. The dataset contained entries from different states and different cities in the United States. The project involved data cleaning, exploratory data analysis, visualization, and deriving insights to aid decision-making. 

## Project Description
This project focused on analyzing sales performance, customer segmentation, and product trends for a Superstore business. The dataset contained sales transactions across various regions, customer segments, product categories, and subcategories.

## Project Aim
The main objectives of this project were to:  
* Identify products generating the highest revenues.  
* Determine revenue distribution across regions.
* Identify the top five customers by revenue.
* Determine the most sought-after products.
* Identify the customer segment with the largest number of customers.
* Analyze sales and profit trends over time.

## About the Dataset
The dataset was downloaded from Kaggle. It contains 9995 rows and 21 columns containing information from customers, products, locations, and orders.   
[Link to the dataset](https://www.kaggle.com/code/danishmubashar/superstore-sales-profit-discount-predict?select=Sample+-+Superstore.csv)

The columns in the dataset are described as follows:  
* *Row ID*: Unique ID for each row
* *Order ID*: Unique Order ID for each Customer
* *Order Date*: Order Date of the product 
* *Ship Date*: Shipping Date of the Product
* *Ship Mode*: Shipping Mode specified by the Customer
* *Customer ID*: Unique ID to identify each Customer
* *Customer Name*: Name of the Customer
* *Segment*: The segment where the Customer belongs
* *Country*: Country of residence of the Customer
* *City*: City of residence of the Customer
* *State*: State of residence of the Customer
* *Postal Code*: Postal Code of every Customer
* *Region*: Region where the Customer belongs
* *Product ID*: Unique ID of the Product
* *Category*: Category of the product ordered
* *Sub-Category*: Sub-Category of the product ordered
* *Product Name*: Name of the Product
* *Sales*: Sales of the Product
* *Quantity*: Quantity of the Product
* *Discount*: Discount provided
* *Profit*: Profit/Loss incurred

## Importing the Dataset to Excel
To import the dataset in Excel, the following steps were completed:  
* Downloaded the dataset from Kaggle as a **.csv** file.
* Launched an empty Excel workbook.
* Clicked on **Data** -> **Get Data** -> selected **From File** -> **From Text/CSV**.
* Located the dataset on my computer and clicked on **Open**.
* After previewing the data, I clicked on **Transform Data**.

## Preparation of the Dataset: Cleaning and Transforming
In Power Query, the following tasks were completed to clean and transform the data.

### Removed Duplicates
To remove duplicates in Power Query,  
* I right-clicked on the little table in the top right corner next to the first column in the dataset.
* Selected **Remove Duplicates** from the menu.

### Assigned the Correct Data Type to Columns
After downloading the data and importing it to Excel, I realized that some columns did not have the correct data type.  
* The Order Date and the Ship Date columns were showing text as data type. So, these two columns were assigned the `DATE` data type. For more details and explanations, watch this YouTube [video](https://www.youtube.com/watch?v=80VimLqID9U&t=17s) that was created by me for that purpose.
* Changed the data type of the **Postal Code** column from `Whole Number` to `Text`.
* Changed the data type of the **Sales** column from `Decimal Number` to `Currency`.
* Changed the data type of the **Discount** column from `Decimal Number` to `Percentage`.
* Changed the data type of the **Profit** column from `Decimal Number` to `Currency`.

### Added a New Column to the Table
A new column named **Ship Duration** was created using the following in the formula bar.
```
=Duration.Days([Ship Date] - [Order Date])
```
This column was necessary to determine the duration of each customer's order.

## Data Modeling in Excel


## Data Analysis in Excel


2. **Created a Calculated Column**  
* Risk Classification based on Credit Amount
```
Risk Category =  IF(Project1[CreditAmount] > 5000, "High Risk", "Low Risk")
```

## Data Visualization in Power BI
* Created Bar charts to showcase the credit amount by purpose and by checking and saving accounts.
* Created Line charts to showcase the credit amount by duration, age and risk category, and age and sex.
* Created donut charts to showcase the credit amount by risk category and housing.
* Created donut charts to showcase the percentage of good vs. bad credit risk.
* Used cards to show the total credit amount, average credit amount, total number of people who applied for credit, the average age, and the average credit duration. 
* Used slicers for sex, housing, credit risk, and risk categories to make the dashboard interactive.

<figure>
  <img src="https://github.com/Songonge/Data-Analytics-Projects/blob/main/All%20Projects/Credit%20Scoring/Dashboard.png" width=100% height=100% alt="alt text">
  <figcaption>Figure: Credit Scoring Analysis Dashboard</figcaption>
</figure>
<br/><br/>

Here is the [Link to the Interactive Dashboard](https://app.powerbi.com/groups/me/reports/25b71013-82ea-423e-b684-e57c5b89c366?ctid=92454335-564e-4ccf-b0b0-24445b8c03f7&pbi_source=linkShare).
 
## Insights from the Data Analysis
1. **Total Credit Distribution by Purpose**  
   * *Observation*: The majority of credit was issued for cars ($1.05M), followed by radio/TV ($609K) and furniture/equipment ($541K). 
   * *Insight*: These top three loan purposes make up a significant share of the total credit portfolio. Education loans and repairs contribute very little comparatively. The least credit was for domestic appliances.

2. **Credit Risk Analysis**  
   * *Observation*:
     * Good Risk accounts for 60.8%, while Bad Risk makes up 39.2% of the credit issued.
     * High Risk (55.1%) slightly outweighs Low Risk (44.9%), indicating moderate portfolio risk.
   * *Insight*: Despite a majority of "good risk" borrowers, a significant proportion of loans are in the "bad risk" category, requiring further risk management strategies.

3. **Savings and Checking Accounts vs. Credit Amount**  
   * *Observation*:
     * Borrowers with little savings accounts took the highest credit amount ($2.03M), followed by those with moderate savings ($543K).
     * Similarly, borrowers with little checking accounts account for the largest credit amount ($1.42M).
   * *Insight*: Borrowers with minimal financial reserves (savings or checking) are receiving the majority of the loans, which could lead to a higher default risk.
4. **Credit by Age and Duration**  
   * *Observation*:
     * Credit amounts are concentrated among borrowers aged 20–40 years.
     * Loan durations vary widely, with peaks around 20-40 months.
   * *Insight*: The age group 20–40 is highly active in borrowing. Longer durations could lead to repayment challenges for certain risk categories.
5. **Housing Status and Credit Distribution**  
   * *Observation*:
     * Borrowers who own housing account for the largest share of the credit ($1.94M), followed by those renting ($494K) and those with free housing ($452K).
   * *Insight*: Housing ownership correlates with a higher credit share, which may indicate a lower default likelihood compared to renters.

## Recommendations from the Data Analysis
1. **Strengthen Risk Management for High-Risk Borrowers**    
   * Implement stricter risk evaluation criteria for borrowers with little savings and checking accounts, as they dominate the loan portfolio but may struggle with repayments.  
2. **Focus on Diversifying Loan Purpose**  
   * Reduce overreliance on car loans by incentivizing loans for purposes like education or business that offer long-term societal and economic benefits.
3.	**Segment by Age and Duration**  
   * For the 20-40 age group, offer shorter-duration loan products to reduce repayment risks.  
   * Monitor repayment patterns on loans exceeding 40 months.
4.	**Encourage Savings Accounts**  
   * Promote savings-linked loans, where borrowers must demonstrate financial reserves before taking loans. This will improve borrower resilience and motivate the repayment within delays.
5.	**Housing and Credit Policy**  
   * For renters and those with "free housing," introduce additional collateral requirements or pre-approval processes to mitigate risk.
6.	**Enhanced Monitoring of 'Bad Risk' Loans**  
   * Use predictive analytics to identify early warning signals for borrowers categorized as "bad risk" and implement intervention strategies (e.g., repayment reminders, and restructuring options).

## Conclusion
The dashboard reveals that a large portion of loans are issued to younger borrowers (20–40 years old) with minimal financial reserves and are concentrated in car-related purposes. While most borrowers fall under the "good risk" category, a significant proportion are still high-risk borrowers.
To improve credit portfolio stability:  
* Diversify loan purposes,
* Implement risk-based loan policies,
* Encourage savings-linked borrowing practices.  
By addressing these areas, the organization can better manage credit risk and optimize loan performance for long-term sustainability.





<!-- The project involved the analysis of a sales dataset from different states in the United States. Excel was used as the Tool and the following tasks were completed throughout the project:

📌 Downloading the dataset from Kaggle

📌 Data Cleaning using Power Query 
-> Removed duplicates and blanks
-> Assigned the correct data type to each column
-> Created new columns where necessary, etc.

📌 Data Modeling
-> Created fact and dimension tables
-> Built relationships between tables to form the STAR schema. 

📌 Data Analysis
-> Created Pivot tables to get the most out of the data and summarize information in the tables.

📌 Data Visualization
-> Created charts from Pivot tables to convey numbers into visuals to communicate insights from the analysis.
-> Created slicers to filter data contained in Pivot tables.
-> Built an interactive dashboard to show all information in one place (See the attached video).


From the analysis and building of the dashboard, the following were addressed:

📌 Identifying products with the highest revenues 
-> Canon ImageCLASS 2200 Advanced Copier

📌 Determining revenue by regions
-> The Western region of the US was the one with the maximum revenues

📌 Identifying the top 5 customers by revenue
-> Sean Miller, Tamara Chand, Raymond Buch, Tom Ashbrook, and Adrian Barton

📌 Determining the most sorted products
-> Technology as a Category and Phones as a Subcategory

📌 Identifying the segment with the largest number of customers 
-> Consumer

📌 Explaining the trend by sales and profit
-> Sales: November had more sales while February had fewer sales. 
-> Profit: January had less profit while December had more profit.

📌 KPIs
-> Total revenue: $2,261,537
-> Total Profit: $278,979
-> Total products: 37143
-> Total customers: 9800
-> Profit Margin: 12.34%  -->

<br/>
   
**Thank you for taking the time to read this report!**

**Please reach out for any updates.**

### Author
[Edwige Songong](https://github.com/Songonge)

