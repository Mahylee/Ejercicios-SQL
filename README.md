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
     SELECT * FROM reviews
     WHERE stars >= 4 
     AND review_id < 6000 
     AND review_id > 2000 
     AND NOT user_id = 142;
   * Let's practice using AND along with WHERE to filter Amazon reviews based on all 4 of these conditions:

   the review should have 4 or more stars
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
     SELECT
       manufacturer
     ,drug
     ,units_sold
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
10. INTERMEDIA SQL
  * SQL Select Practice Exercise
     SELECT