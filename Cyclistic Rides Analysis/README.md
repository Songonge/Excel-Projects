# Project: Cyclistic Rides Analysis

## Table of Contents  
1. [Introduction](#introduction)
2. [Problem](#problem)
3. [Project Aim](#project-aim)
4. [Business Task](#business-task)
   * [Project Objective](#project-objective)
   * [Project Scope](#project-scope)
   * [Key Questions](#key-questions)
   * [Expected Outcomes](#expected-outcomes)
   * [Success Metrics](#success-metrics)
5. [Data Acquisition and Preparation](#data-acquisition-and-preparation)
6. [Data Cleaning and Processing](#data-cleaning-and-processing)
8. [Data Analysis and Visualization](#data-analysis-and-visualization)
9. [Share](#share)
10. [Act](#act)

## Introduction

Cyclistic is a company in Chicago that offers trips to customers daily. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, the purpose of this project is to understand how casual riders and annual members use Cyclistic bikes differently. This will help design a new marketing strategy to convert casual riders into annual members.

## Problem
The major problem is that Cyclistic wants more customers to sign up for membership instead of being casual riders. 

As a junior data analyst working with the marketing analyst team at Cyclistic, the director of marketing and my manager have asked me to answer the question: **How do annual members and casual riders use Cyclistic bikes differently?**

Answering the above question will help the marketing team identify the reasons why casual riders do not sign up for membership. It will also help propose new strategies to motivate casual riders to sign up for membership.

## Project Aim
Use Excel to design marketing strategies aimed at converting Cyclistic’s casual riders into annual members. 

This report will follow a roadmap to highlight the following deliverables:
1.	A clear statement of the business task 
2.	A description of all data sources used 
3.	Documentation of any cleaning or manipulation of data 
4.	A summary of my analysis 
5.	Supporting visualizations and key findings
6.	My top three recommendations based on my analysis
   
## Business Task

### Project Objective 
Convert Cyclistic’s casual riders into annual members.

### Project Scope
Use data analytics to identify:
*	Key factors that prevent casual riders from becoming annual members.
*  Factors that will make casual riders interested in becoming annual members.
*	Patterns in riders' behaviors and product performance.
*	Opportunities to increase Cyclistic customer satisfaction.

### Key Questions
*	What is the problem I am trying to solve?
*	How can my insights drive business decisions?
*	What are the common characteristics of annual members?
  
### Expected Outcomes
*	A detailed report highlighting actionable insights.
*	Recommendations for targeted marketing strategies.
*	A dashboard providing real-time customer data.
  
### Success Metrics
*	Increase in Cyclistic riders.
*	Increase in Cyclistic annual memberships.
*	Conversion of many casual riders to annual members.

## Data Acquisition and Preparation
*	I used the data of Cyclistic trip data made available by Motivate International Inc. 
*	Data for the first quarter of 2019 was downloaded for the Cyclistic trip data.  

## Data Cleaning and Processing
I chose **Excel** to clean the data because it is easy to use and the dataset is not large.  The following steps were performed:
*	I sorted and filtered data to remove unnecessary and inaccurate data. 
*	I removed duplicate
*	I removed blanks or rows with empty cells to ensure the remaining data could be used.
*	Fixed rows and columns by verifying that columns with numbers were all numbers by converting text in some cells into numbers.
*	Checked the data for errors.
*	Ensured that each field had the appropriate data type by performing some conversions where needed. 
*	The raw data were transformed and changed into a standard data format suitable for analysis, storage, and easy use.

## Data Analysis and Visualization
* The following calculations were performed in individual files first, such as:
  ```
  Mean of ride_length: =AVERAGE(D2:D32767)
  ```
  This gave `0:14:55`
  
  ```Max of ride_length: =MAX(D2:D32767)
  ```
  This gave `232:09:59`
  

  ```
  Mode of day_of_week: =MODE(E2:E32767)
  ```
  This gave `5`
     
* A pivot table was created to quickly calculate and visualize the data.
  * I calculated the `average ride_length` for members and casual riders by adding `member_casual` under `Rows` and `ride_length` under `Values` and selecting `Average` from the `Values Field Settings`.
  * I calculated the `average ride_length` for users by `day_of_week` by adding `day_of_week` under `Columns`, `member_casual` under `Rows`, and `Average` of `ride_length` under `Values`
  * I calculated the `number of rides` for users by `day_of_week` by adding `Count of ride_id` to `Values`.

* Performing these descriptive analysis steps helped make some initial observations, such as the day with the most rides is `Thursday`. The table below was designed to show the difference between casual riders and members.

|      Calculations     |      Casual Riders    | Members |
| :-------------: | :-------------: | :-------------: |
| Total Count of Rides   |      5934    | 339423 |
| Average Ride Length  | 0:37:01	       | 0:13:52   |

  * From the above table, it can be seen that the total number of trips for members was far greater than that for casual riders in the first quarter of 2019.

The following table shows the max and min rides for both rider types.

|      Calculations     |      Casual Riders    | Members |
| :-------------: | :-------------: | :-------------: |
| Max number of rides   |      1321    | 63519 |
| Day of max rides | Saturday	       | Thursday   |
| Min number of rides   |      568    | 23988 |
| Day of min rides | Monday	       | Sunday   |

## Share
* I was able to answer the question of how annual members and casual riders use Cyclistic bikes differently. The analysis helped me see that many riders have memberships. In addition, the ride length for casual riders was longer than that of members.
* The story that my data tells is that for the first quarter of 2019, the data tells that the maximum number of rides is on Thursday for members and Saturday for casual riders. Looking at Table 4, we can say that the number of rides decreased from January to February and then considerably increased from February to March 2019.
* The data visualization given by the Dashboard in Figure 1 helped me communicate and share my findings. This is because it provides details and directly shows the summary of data in charts, graphs, and figures, which are easy to understand.
* Supporting visualizations and key findings

In the following table, I display the total number of daily rides for each rider type.

| Day of Week	| Casual Riders	| Member Riders	| Total Number of Rides per day |
| :-------------: | :-------------: | :-------------: | :-------------: |
| 1	| 976	| 23988	|  24964  |
| 2	| 568	|	48161	|	48729  |
| 3	| 783	|	57928	|	58711  |
| 4	| 628	|	57521	|	58149  |
| 5	| 784	|	63519	|	64303  |
| 6	| 874	|	59244	|	60118  |
| 7	| 1321|	29062	|	30383  |

After completing the data analysis, a dashboard was designed to clearly communicate the insights. That is shown below.

| Figure: Cyclistic Rides Analysis Dashboard |
| :------------: |
<figure>
  <img src="https://github.com/Songonge/Excel-Projects/blob/main/Cyclistic%20Rides%20Analysis/Cyclistic%20Ride%20Analysis%20Dashboard.png" width=100% height=100% alt="alt text">
<!--   <figcaption>Figure: Cyclistic Rides Analysis Dashboard</figcaption> -->
</figure>
<!-- <br/><br/> -->

## Act
Now that I have finished creating my visualizations, I can act on my findings. The three top recommendations based on my analysis are: 
* Based on my analysis, my conclusion is that the number of rides for member riders is greater than that of casual riders. Therefore, for casual riders to become members, the company can add some promotions to the membership enrollment.
* The majority of riders are adults in the age range of 30 and 50. Therefore, the marketing team can create events to invite people of other age ranges. This will be a motivation to obtain more customers.
* The day of the week with maximum rides is Saturday for casual riders. Therefore, this day can be used to reach out to these riders and talk to them about the benefits of membership.

![Cyclistic Ride Analysis Interactive Dashboard.mp4](https://github.com/user-attachments/assets/2acc1b7f-d49e-4c22-b842-0466dd4a2dae)

<br/><br/>

**Thank you for taking the time to read this report!**

**Please reach out for any updates.**

### Author
[Edwige Songong](https://github.com/Songonge)
