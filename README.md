# Sales Insights Analysis a Data Analysis Project

## - Introduction  ![image](https://user-images.githubusercontent.com/92949677/208624104-3fd15997-d6bf-464d-b1c6-4b53e8e7dfe9.png)


Data analytics is the process of analyzing raw data in order to draw out meaningful, actionable insights, which are then used to inform and drive smart business decisions. In this project , we will perform a data analyst project.

## - Problem statement 

A atliq hardware is a hardware company which supplies its product all over India even out of India. They want to keep track on their sales , so that they can take a meaningful decision for the betterment of the company. But, as we all know keeping track on sales will require data and to manually manage all those data is quite complex and expensive. So, atliq company hires a Data Analyst who can analyze the data and withdraw some insights from the data.

## - Purpose

To unlock sales insights that are not visible before for sales team for decision support and automate them to reduce manual time spent in data gathering.

## - Goal of the Project

An automated dashboard proving quick and latest sales insight in order to support data driven decision.

## - Success Criteria 

1. Dashboard uncovering sales insight for latest data available.
2. Sales team able to take better decision and prove 10% cost savings of total spent.
3. Sales aanlyst stops data gathering manually in order to save their 20% of business time and reinvest it value added activity.

## - Prerequisite

1. Hand on experience on SQL .
2. Hand on experience Power BI to perform ETL and Dashboard.
3. Knowledge about the business.



# Data Analysis Using Power BI

1. We have two blank zone in market table, so we have to remove that blank for better analysis

= Table.SelectRows(sales_markets, each ([zone] <> ""))

2. There is -1 and 0 in sales_amount in transactions table, We cannot keep these data for our visualization

= Table.SelectRows(sales_transactions, each ([sales_amount] <> -1 and [sales_amount] <> 0))

3. Removing deuplicate data 

= Table.SelectRows(#"Filtered Rows", each ([currency] = "INR#(cr)" or [currency] = "USD"))

4. We had USD and INR in our currency column , so we need to convert USD into INR currency 

= Table.AddColumn(#"Filtered Rows1", "normalised_currency", each if [currency] = "USD" then [sales_amount]*82 else [sales_amount])


# Dashboard

![dashboard_pdf_page-0001](https://user-images.githubusercontent.com/92949677/208621294-d50d2f8e-0661-451a-a800-bea3311d9da8.jpg)


