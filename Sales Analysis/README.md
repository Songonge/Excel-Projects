# Project: Analyzing Sales from Different States in the United States

## Table of Contents
1. [Introduction](#introduction)
2. [Project Description](#project-description)
3. [Project Aim](#project-aim)
4. [About the Dataset](#About-the-dataset)
5. [Importing the Dataset to Excel](#Importing-the-Dataset-to-Excel)
6. [Preparation of the Dataset: Cleaning and Transforming](#Preparation-of-the-Dataset-Cleaning-and-Transforming)
   * [A. Removed Duplicates](#A-Removed-Duplicates)
   * [B. Assigned the Correct Data Type to Columns](#B-Assigned-the-Correct-Data-Type-to-Columns)
   * [C. Added a New Column to the Table](#C-Added-a-New-Column-to-the-Table)
7. [Data Modeling in Excel](#Data-Modeling-in-Excel)
   * [A. Created a Fact Table Named Orders](#A-Created-Dimension-Tables)
     * [1. The Product Table](#1-The-Product-Table)
     * [2. The Location Table](#2-The-location-Table)
     * [3. The Customer Table](#3-The-Customer-Table)
   * [B. Created a Fact Table Named Orders](#B-Created-a-Fact-Table)
   * [C. Adding Data to the Model](#C-Adding-Data-to-the-Model)
   * [D. Building Relationships Between Tables](#D-Building-Relationships-Between-Tables)
8. [Data Analysis in Excel](#Data-Analysis-in-Excel)
9. [Data Visualization in Excel](#Data-Visualization-in-Excel)
10. [Insights from the Data Analysis](#Insights-from-the-Data-Analysis)
11. [Recommendations from the Data Analysis](#Recommendations-from-the-Data-Analysis)
12. [Conclusion](#Conclusion)

## Introduction
The purpose of this report is to provide an in-depth analysis of the Superstore dataset, downloaded from Kaggle, using Excel. The dataset contained entries from different states and different cities in the United States. The project involved data cleaning, exploratory data analysis, data visualization, and deriving insights to support decision-making. 

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
To import the dataset into Excel, the following steps were completed:  
* Downloaded the dataset from Kaggle as a **.csv** file.
* Launched an empty Excel workbook.
* Clicked on **Data** -> **Get Data** -> selected **From File** -> **From Text/CSV**.
* Located the dataset on my computer and clicked on **Open**.
* After previewing the data, I clicked on **Transform Data**.

## Preparation of the Dataset: Cleaning and Transforming
In Power Query, the following tasks were completed to clean and transform the data.

### A. Removed Duplicates
To remove duplicates in Power Query,  
* I right-clicked on the little table in the top right corner next to the first column in the dataset.
* Selected **Remove Duplicates** from the menu.

### B. Assigned the Correct Data Type to Columns
After downloading the data and importing it into Excel, I realized that some columns did not have the correct data type.  
* The Order Date and the Ship Date columns were showing text as a data type. So, these two columns were assigned the `DATE` data type. For more details and explanations, watch this YouTube [video](https://www.youtube.com/watch?v=80VimLqID9U&t=17s) that was created by me for that purpose.
* Changed the data type of the **Postal Code** column from `Whole Number` to `Text`.
* Changed the data type of the **Sales** column from `Decimal Number` to `Currency`.
* Changed the data type of the **Discount** column from `Decimal Number` to `Percentage`.
* Changed the data type of the **Profit** column from `Decimal Number` to `Currency`.

### C. Added a New Column to the Table
A calculated column named **Ship Duration** was created using the following in the formula bar.
```
=Duration.Days([Ship Date] - [Order Date])
```
This column was necessary to determine the duration of each customer's order.

The cleaned data contained 9800 rows and 22 columns.

## Data Modeling in Excel
To model the data, a fact table and three dimension tables were created. Then, relationships were built between these tables to form the STAR schema. 

### A. Created Dimension Tables
Three-dimensional tables were created. To do this, the original table with cleaned data was duplicated to form three times.  

#### 1. The Product Table
This table contained all information related to products. The following columns were kept while others were deleted: Product ID, Category, Sub-Category, and Product Name.  
* The Product ID column was considered the primary key of this table.
* Duplicates were deleted in the Product ID column in the Product table to keep unique values. This was to ensure an effective one-to-many relationship with the Orders table using the Product ID column in both tables.

#### 2. The Location Table
This table contained all information related to locations. The following columns were kept while others were deleted: Postal Code, Country, City, State, and Region.  
* The Postal Code column was considered the primary key of this table.
* Duplicates were deleted in the Postal Code column in the Location table to keep unique values. This was to ensure an effective one-to-many relationship with the Orders table using the Postal code column in both tables.

#### 3. The Customer Table
This table contained all information related to customers. The following columns were kept while others were deleted: Customer ID, Customer Name, and Segment.  
* The Customer ID column was considered the primary key of this table.
* Duplicates were deleted in the Customer ID column in the Customer table to keep unique values. This was to ensure an effective one-to-many relationship with the Orders table using the Customer ID column in both tables.

### B. Created a Fact Table
A fact table named **Orders** was created by duplicating the initial table with cleaned data. The following columns were kept: Row ID, Order ID, Customer ID, Product ID, Postal Code, Order Date, Ship Date, Ship Duration, Ship Mode, Sales, Quantity, Discount, and profit. Other columns were deleted from this table because they already appeared in the dimension tables.  
Here, it should be highlighted that:
* Row ID was the primary key of this fact table.
* Order ID, Customer ID, Product ID, and Postal Code were foreign keys from the dimension tables.

### C. Adding Data to the Model
After the dimension and fact tables were created, each of them was added to the model. To do that, I  
* Selected the worksheet and clicked on Power Pivot.
* Clicked on Add to Data Model
* Performing these steps for each table added the four tables to the data model.

### D. Building Relationships Between Tables
One-to-many relationships were created between the tables as follows.  
* Between the Product table and the Orders table using the Product ID column.
* Between the Location table and the Orders table using the Postal Code column.
* Between the Customer table and the Orders table using the Customer ID column.

| Figure: Relationships between tables using the STAR schema |
| :------------: |
<figure>
  <img src="https://github.com/Songonge/Excel-Projects/blob/main/Sales%20Analysis/Relationship_Star_Schema.png" width=100% height=100% alt="alt text">
<!--   <figcaption>Figure: Relationships between tables using the STAR schema</figcaption> -->
</figure>
<!-- <br/><br/> -->

## Data Analysis in Excel
The analysis was conducted using various Excel functions and tools, including:
* Pivot tables for aggregating and summarizing data.
* SUMIF and COUNTIF functions to extract specific insights.
* Data filtering and sorting for trend identification.
* Lookup functions for customer and product analysis.


## Data Visualization in Excel
To support the analysis, the following visualizations were created to convey numbers in visuals and to communicate insights from the analysis:
* **Bar charts** to display revenue by:  
  * Category
  * Sub-category
  * Region
  * Segment
  * Top five states
  * Top five products  

* **Line charts** for sales and profit trends over time  
* Cards to display KPIs from the data, such as:  
  * Total Customers 
  * Total Revenue
  * Total Profit
  * Total Quantity
  * Profit Margin  

* **Slicers** to filter data contained in Pivot tables, such as
  * Year
  * Ship Mode
  * Ship Duration

The following figure shows the dashboard that was built after analyzing the data.

| Figure: Sales Analysis Dashboard |
| :------------: |
<figure>
  <img src="https://github.com/Songonge/Excel-Projects/blob/main/Sales%20Analysis/Sales%20Analysis%20Dashboard.png" width=100% height=100% alt="alt text">
<!--   <figcaption>Figure: Sales Analysis Dashboard</figcaption> -->
</figure>
<!-- <br/><br/> -->

<!-- Here is the [Link to the Interactive Dashboard](https://app.powerbi.com/groups/me/reports/25b71013-82ea-423e-b684-e57c5b89c366?ctid=92454335-564e-4ccf-b0b0-24445b8c03f7&pbi_source=linkShare). -->
 
## Insights from the Data Analysis
From the analysis, the following insights were derived:

1. **Product with Highest Revenue**  
   * The Canon ImageCLASS 2200 Advanced Copier generated the most revenue.  

2. **Revenue by Region**  
   * The West region had the highest revenue among all regions.  

3. **Top 5 Customers by Revenue**  
   * Sean Miller
   * Tamara Chand
   * Raymond Buch
   * Tom Ashbrook
   * Adrian Barton

4. **Most Sought-After Products**  
   * *Category*: Technology  
   * *Subcategory*: Phones  

5. **Customer Segment with Most Customers**  
   * The Consumer segment had the highest number of customers.

6. **Sales and Profit Trends**  
   * _Sales_: November had the highest sales, while February had the lowest.  
   * _Profit_: December had the highest profit, while January had the lowest.

## Recommendations from the Data Analysis
Based on the insights, the following recommendations are suggested:  
1. Invest in High-Revenue Products  
   * Increase stock and marketing efforts for high-performing products like the Canon ImageCLASS 2200 Advanced Copier.  
2. Regional Strategy Optimization  
   * Focus on expanding sales efforts in high-revenue regions like the West.  
3. Customer Retention
   * Develop loyalty programs targeting the top customers to maintain and increase their spending.  
4. Stock Management
   * Ensure sufficient inventory for high-demand categories such as Technology and Phones.  
5. Seasonal Promotions
   * Implement targeted promotions in months with lower sales (February) and leverage high-performing months (November, December) with special offers.
6. Profit Maximization
   * Analyze why profit margins were lower in January and optimize pricing strategies accordingly.

## Conclusion
This project provided a comprehensive analysis of the Superstore dataset using Excel. By leveraging data cleaning, analysis, and visualization techniques, key insights into sales trends, customer behavior, and product performance were uncovered. Implementing the recommended strategies can drive business growth and profitability in the future.


<br/>
   
**Thank you for taking the time to read this report!**

**Please reach out for any updates.**

### Author
[Edwige Songong](https://github.com/Songonge)

