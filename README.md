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


