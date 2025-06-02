
<span style="color:red">Ejercicios-SQL</span>

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
    * SQL Tutorial Lesson: Top-Selling Artists
SELECT
  artist_name,
  concert_revenue,
  genre,
  number_of_members,
  concert_revenue / number_of_members AS revenue_per_member,
  RANK() OVER (
    PARTITION BY genre
    ORDER BY concert_revenue / number_of_members DESC) AS ranked_concerts
FROM concerts;
   * Supercloud Customer
SELECT 
  customers.customer_id, 
  COUNT(DISTINCT products.product_category) AS product_count
FROM customer_contracts AS customers
INNER JOIN products 
  ON customers.product_id = products.product_id
GROUP BY customers.customer_id;
   * Swapped Food Delivery
SELECT COUNT(order_id) AS total_orders 
FROM orders;
24. Window Function - 303
   * Card Launch Success
SELECT MAKE_DATE(issue_year, issue_month, 1)
FROM monthly_cards_issued;
25. SQL Ranking
   * Top 5 Artists
WITH top_10_cte AS (
  SELECT 
    artists.artist_name,
    DENSE_RANK() OVER (
      ORDER BY COUNT(songs.song_id) DESC) AS artist_rank
  FROM artists
  INNER JOIN songs
    ON artists.artist_id = songs.artist_id
  INNER JOIN global_song_rank AS ranking
    ON songs.song_id = ranking.song_id
  WHERE ranking.rank <= 10
  GROUP BY artists.artist_name
)

SELECT artist_name, artist_rank
FROM top_10_cte
WHERE artist_rank <= 5;
   * Histogram of Users and Purchases
SELECT 
  transaction_date, 
  user_id, 
  product_id, 
  RANK() OVER (
    PARTITION BY user_id 
    ORDER BY transaction_date DESC) AS transaction_rank 
  FROM user_transactions;
   * Odd and Even Measurements
SELECT 
date(measurement_time) as measurement_day,
measurement_value,
DENSE_RANK() OVER(PARTITION BY date(measurement_time) ORDER BY measurement_time) AS RN
FROM measurements)
26. SQL LEAD & LAG - 304
   * SQL Tutorial Lesson: Stock Performance
SELECT *,LEAD(CLOSE) OVER( ORDER BY date),close - LEAD(CLOSE) OVER( ORDER BY date) ,LAG(CLOSE,3) OVER( ORDER BY date),close - LAG(CLOSE,3) OVER( ORDER BY date) AS DIFFERENCE FROM stock_prices where ticker = 'GOOG' ;
   * Y-on-Y Growth Rate
SELECT
EXTRACT(YEAR FROM u1.transaction_date) AS year,
u1.product_id,
u1.spend AS curr_year_spend,
u2.spend AS prev_year_spend,
ROUND((u1.spend/u2.spend *100) - 100 , 2) AS yoy_rate
FROM
user_transactions u1
LEFT JOIN user_transactions u2 ON EXTRACT(YEAR FROM u1.transaction_date)-1 = EXTRACT(YEAR FROM u2.transaction_date)
      AND u1.product_id = u2.product_id
ORDER BY 2,1;
   * Y-on-Y Growth Rate
SELECT 
    EXTRACT(YEAR FROM transaction_date) AS year,
    product_id,
    spend AS curr_year_spend,
    LAG(spend) OVER (PARTITION BY product_id ORDER BY transaction_date) AS prev_year_spend,
    round(100 * (spend - LAG(spend) OVER (PARTITION BY product_id ORDER BY transaction_date)) / LAG(spend) OVER (PARTITION BY product_id ORDER BY transaction_date),2) AS yoy_rate
FROM user_transactions;
27. SQL Self-Joins - 305
   * SQL Tutorial Lesson: SQL Joins
SELECT
  b1.genre,
  b1.book_title AS current_book,
  b2.book_title AS suggested_book
FROM goodreads AS b1
INNER JOIN goodreads AS b2
  ON b1.genre = b2.genre
WHERE b1.book_id != b2.book_id
ORDER BY b1.book_title;
28. SQL Union - 306
   * Maximize Prime Item Inventory
SELECT
  item_type,
  SUM(square_footage) AS total_sqft,
  COUNT(*) AS item_count
FROM inventory
GROUP BY item_type;
   * Page With No Likes
SELECT page_id FROM pages
except 
SELECT page_id FROM page_likes;
29. Write Clean SQL - 307
30. Execution Order - 308
31. SQL PIVOTING - 309
32. String Functions - 310
   * SQL LOWER Practice Exercise
Assume you're given the customer table containing all customer details.
The branch manager is looking for a male customer whose name ends with "son" and he's 20 years old.
Write a SQL query which uses LOWER and LIKE to find this customer's details.
SELECT *
FROM customers
WHERE LOWER(customer_name) LIKE '%son'
  AND gender = 'Male'
  AND age = 20;
33. Instacart SQL Case - 311
   * Instacart Exploration  Case Study Checkpoint #1
  Explore the ic_products data. Here are some questions to investigate:
  How many items are there?
  How many different products are in the dataset?
SELECT COUNT(*) AS total_items
FROM (
    SELECT * FROM ic_order_products_curr
    UNION ALL
    SELECT * FROM ic_order_products_prior
) AS all_orders;
SELECT COUNT(DISTINCT product_id) AS unique_products
FROM ic_products;

------------------------------------------------------------------------------------------
 
SQLZoo
Tutorial de SQL
0. SELECCIONAR conceptos básicos
  1. Introducing the world table of countries
SELECT population FROM world
  WHERE name = 'Germany'
  2. Scandinavia
SELECT name, population FROM world
WHERE name IN ('Sweden', 'Norway', 'Denmark');
  3. Just the right size
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
0. QUIZ
  1. Selct the code wich produces this table
SELECT name, population
  FROM world
 WHERE population BETWEEN 1000000 AND 1250000
  2. Pick the result you would obtain from this code:
SELECT name, population
FROM world
WHERE name LIKE "Al%0"
RESULT: TABLE-E
  3. Select the code wich shows the countries that end in A or L
SELECT name FROM world
WHERE name LIKE '%a' OR name LIKE '%l'
  4. Pick the result from the query
SELECT name,length(name)
FROM world
WHERE length(name)=5 and region='Europe'
RESULT: Italy 5
        Malta 5
        Spain 5
  5. Here are the first few rows of the world table
SELECT name, area*2 FROM world WHERE population =64000
RESULT: Andorra 936
  6. Select the code that would show the countries with an area larger than 50000 and a population smaller than 10000000
SELECT name, area, population
  FROM world
 WHERE area > 50000 AND population < 10000000
   7. Select the code that shows the population density of China, Australia, Nigeria and France
SELECT name, population/area
  FROM world
 WHERE name IN ('China', 'Nigeria', 'France', 'Australia')


 SELECT names
 1. Find the country that start with Y
 SELECT name FROM world
 WHERE name LIKE 'Y%
 2. Find the countries that end with y
 SELECT name FROM world
 WHERE name LIKE '%y'
 3. Find the countries that contain the letter x
 SELECT name FROM world
 WHERE name LIKE '%x%'
 4. Find the countries that end with land
 SELECT name FROM world
    WHERE name '%land'
5. Find the countries that star
