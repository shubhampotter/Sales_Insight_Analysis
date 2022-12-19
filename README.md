-----------------Sales Analysis ---------------------

-- 1. How many total number of transaction we have?

SELECT 
    COUNT(*) total_transactions
FROM
    sales.transactions;

-- 2. Total tranction in city Chennai

SELECT 
    COUNT(*) total_transactions
FROM
    sales.transactions
WHERE
    market_code = 'Mark001';

-- 3. fetch All transaction of Year-2022

SELECT 
    t.*, O.Year
FROM
    sales.transactions t
        INNER JOIN
    sales.date O ON t.Order_date = O.date
WHERE
    O.Year = 2020;

-- 4. check the distinct year that is present in our data

SELECT DISTINCT
    (year)
FROM
    sales.date;

-- 5. Total revenue made in year 2020

SELECT 
    SUM(t.sales_amount) Total_Revenue
FROM
    sales.transactions t
        INNER JOIN
    sales.date O ON t.Order_date = O.date
WHERE
    O.Year = 2020;

-- 6.Total revenue per year

SELECT 
    year, SUM(t.sales_amount) Total_Revenue
FROM
    sales.transactions t
        INNER JOIN
    sales.date O ON t.Order_date = O.date
GROUP BY year;

-- 7.Total revenue in chennai city in 2020

SELECT 
    SUM(t.sales_amount) Total_Revenue
FROM
    sales.transactions t
        INNER JOIN
    sales.date O ON t.Order_date = O.date
WHERE
    year = 2020 AND market_code = 'Mark001';

-- 8. distinct product sold in chennai

SELECT DISTINCT
    (P.product_code)
FROM
    sales.transactions T
        INNER JOIN
    sales.products P ON T.product_code = P.product_code;

-- 9. check where the sum amount is less than 0

SELECT 
    *
FROM
    sales.transactions
WHERE
    sales_amount <= 0;

