# Ejercicios-SQL
Ejercicios de DataLemur en SQL
1. Lección 101 - SQL TUTORIAL INTRO
   * SQL Select Practice Exercise
SELECT user_id, stars FROM reviews WHERE stars = 3;
   * Given the reviews table, write a query to retrieve all 3-star reviews using the SQL WHERE clause. Only display the user_id and stars columns.
2. Lección 102 - SQL SELECT
   * SQL Select Practice Exercise
SELECT * FROM Products;
   * Your given a products table, which contains data about different Microsoft Azure cloud products.
   Output all the data, in all the columns.
3. Lección 103 - SQL WHERE tutorial with examples
   * SQL Select Practice Exercise
SELECT user_id, stars FROM reviews WHERE stars = 3;
   * Given the reviews table, write a query to retrieve all 3-star reviews using the SQL WHERE clause. Only display the user_id and stars columns.
4. Lección 104 - SQL AND, OR, NOT
   * SQL Select Practice Exercise
SELECT * FROM reviews WHERE stars >= 4  AND review_id < 6000  AND review_id > 2000  AND NOT user_id = 142;
   * Let's practice using AND along with WHERE to filter Amazon reviews based on all 4 of these conditions: the review should have 4 or more stars
   the review ID is less than 6000
   the review ID is more than 2000
   the review can't come from user 142
5. Lección 105 - SQL BETWEEN
   * SQL Select Practice Exercise
SELECT manufacturer, drug, units_sold FROM pharmacy_sales WHERE manufacturer IN ('Biogen','AbbVie','Eli Lilly') AND units_sold BETWEEN 100000 AND 105000;
   * Imagine you are a Data Analyst working at CVS Pharmacy, and you had access to pharmacy sales data. Use the BETWEEN SQL command to find data on medicines:
   which sold between 100,000 units and 105,000 units
   AND were manufactured by either Biogen, AbbVie, or Eli Lilly
6. Lección 106 - SQL IN
   * SQL Select Practice Exercise
SELECT manufacturer, drug, units_sold
  FROM pharmacy_sales
  WHERE manufacturer IN ('Roche', 'Bayer', 'AstraZeneca')
   AND units_sold NOT BETWEEN 55000 AND 550000;
   * Imagine you are a Data Analyst working at CVS Pharmacy, and you had access to pharmacy sales data. Use the IN SQL command to find data on medicines:
   which were manufactured by either Roche, Bayer, or AstraZeneca
   and did not sell between 55,000 and 550,000 units
7. Lección 107 - SQL like
   * SQL LIKE % Practice Exercise
SELECT * FROM customers WHERE customer_name LIKE 'F%ck';
   * SQL LIKE _Practice
SELECT * FROM customers WHERE customer_name LIKE 'F%ck';
   * You have a table of 1000 customer records from a small-business based in Australia.
   * You have a table of 1000 customer records from a small-business based in Australia.
8. Lección 108 - SQL FILTERING REVIEW
   * SQL Select Practice Exercise
SELECT *
FROM customers
WHERE age BETWEEN 18 AND 22
  AND state IN ('Victoria', 'Tasmania', 'Queensland')
  AND gender != 'n/a'
  AND (customer_name LIKE 'A%' OR customer_name LIKE 'B%');
9. Lección 109 - SQL ORDER BY
   * SQL Select Practice Exercise, Pharmacy Analytics
SELECT drug,
(total_sales-cogs) as total_profit
FROM pharmacy_sales
ORDER BY total_profit DESC
LIMIT 3
10. Lección 201 - INTERMEDIA SQL
11. Lección 202 - SUM, AVG, ACOUNT
   * SQL Count Practice Exercise, pharmacy_sales
SELECT COUNT (*) FROM pharmacy_sales;
   * SQL SUM Practice Exercise
SELECT COUNT(product_id), SUM(total_sales) FROM pharmacy_sales WHERE manufacturer = 'Pfizer';
   * SQL AVG Practice Exercise
SELECT AVG (open) FROM stock_prices where ticker = 'GOOG';
   * SQL MIN Practice Exercise
SELECT MIN(open) FROM stock_prices WHERE ticker='MSFT';
   * SQL MAX Practice Exercise
SELECT MAX(open) FROM stock_prices WHERE ticker='NFLX';
12. Lección 203 - SQL GROUP BY
   * GROUP BY Practice Exercise #1
SELECT ticker, MIN(open) FROM stock_prices GROUP BY ticker ORDER BY min DESC;SELECT * FROM stock_prices
   * GROUP BY Practice Exercise #2
SELECT skill, COUNT(candidate_id) FROM candidates GROUP BY skill ORDER BY count DESC;
13. Lección 204 - SQL HAVING
   * SQL HAVING Practice Exercise #1
SELECT ticker, MIN(open) FROM stock_prices GROUP BY ticker HAVING MIN(open) > 100;
   * SQL HAVING Practice Exercise #2
SELECT candidate_id FROM candidates GROUP BY candidate_id HAVING COUNT(candidate_id) > 2;
14. Lección 205 - SQL Distinct
   * SQL Count Practice Exercise
 SELECT category, COUNT(DISTINCT product) FROM product_spend GROUP BY category;
15. Lección 206 - SQL Arithmetic
   * Practice SQL Subtraction: CVS Pharmacy Interview Question
SELECT drug, total_sales - cogs AS total_profit FROM pharmacy_sales ORDER BY total_profit DESC LIMIT 3;
   * Practice SQL Arithmetic: JPMorgan Chase SQL Interview Question
SELECT  card_name, MAX(issued_amount) - MIN(issued_amount) AS difference FROM monthly_cards_issued GROUP BY card_name ORDER BY difference DESC;
   * SQL Math Practice Exercise: Big-Mover Months
SELECT ticker, COUNT(ticker) FROM stock_prices WHERE (close - open)/open > 0.10 OR (close - open)/open < -0.10 GROUP BY ticker ORDER BY count DESC;
16. Lección 207 - SQL Math Functions
   * SQL CEIL Practice Exercise
SELECT drug, CEIL(total_sales / units_sold) AS unit_cost FROM pharmacy_sales WHERE manufacturer = 'Merck' ORDER BY unit_cost;
17. Lección 208 - SQL DIVISION 
   * 
18. Lección 209 - SQL NULL
   * Unfinished Parts
SELECT part, assembly_step FROM parts_assembly WHERE finish_date IS NULL;
19. Lección 210 - SQL CASE 
   * SQL Tutorial Lesson: Superheroes' Likes
SELECT actor, character, platform, avg_likes, CASE  WHEN avg_likes >= 15000 THEN 'Super Likes' WHEN avg_likes BETWEEN 5000 AND 14999 THEN 'Good Likes'
    ELSE 'Low Likes' END AS likes_category FROM marvel_avengers ORDER BY avg_likes DESC;
   * Laptop vs. Mobile Viewership
SELECT 
  COUNT(*) FILTER (WHERE device_type = 'laptop') AS laptop_views,
  COUNT(*) FILTER (WHERE device_type IN ('tablet', 'phone'))  AS mobile_views 
FROM viewership;
20. Lección 211 - SQL JOINS
    * SQL Selecte Practice Exercise
SELECT * FROM trades JOIN users ON trades.user_id = users.user_id;
 * Cities With Completed Trades
SELECT 
  users.city, 
  COUNT(trades.order_id) AS total_orders 
FROM trades 
INNER JOIN users 
  ON trades.user_id = users.user_id 
WHERE trades.status = 'Completed' 
GROUP BY users.city 
ORDER BY total_orders DESC
LIMIT 3;
*   * Page With No Likes
SELECT page_id FROM pages;
21. Lección - Date Functions
   * Average Post Hiatus (Part 1)
SELECT 
	user_id, 
    MAX(post_date::DATE) - MIN(post_date::DATE) AS days_between
FROM posts
WHERE DATE_PART('year', post_date::DATE) = 2021 
GROUP BY user_id
HAVING COUNT(post_id)>1;
   * Second Day Confirmation
SELECT *
FROM emails 
INNER JOIN texts
  ON emails.email_id = texts.email_id;
   * Average Post Hiatus (Part 1)
SELECT 
	user_id, 
    MAX(post_date::DATE) - MIN(post_date::DATE) AS days_between
FROM posts
WHERE DATE_PART('year', post_date::DATE) = 2021 
GROUP BY user_id
HAVING COUNT(post_id)>1;
22. CTE vs SUBQUERRY - 301
   * SQL Tutorial Lesson: Top-Selling Artists
SELECT
  artist_name,
  concert_revenue,
  genre,
  number_of_members,
  concert_revenue / number_of_members AS revenue_per_member,
  RANK() OVER (
    PARTITION BY genre
    ORDER BY concert_revenue / number_of_members DESC) AS ranked_concerts  FROM concerts;
    * Supercloud Customer
ELECT 
  customers.customer_id, 
  COUNT(DISTINCT products.product_category) AS product_count
FROM customer_contracts AS customers
INNER JOIN products 
  ON customers.product_id = products.product_id
GROUP BY customers.customer_id;
    * Page With No Likes
SELECT page_id
FROM pages;
23. Date Functions - 302
