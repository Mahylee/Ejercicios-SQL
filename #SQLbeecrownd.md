# SQL-BEECROWD
- ** EJERCICIO 2602 Basic Select **
```
solucion:
SELECT name
FROM customers
WHERE state='RS';
```
![image](https://github.com/user-attachments/assets/a07e6c02-c6ef-4eaa-b7ef-b9b2dfe0ad51)
- ** EJERCICIO 2603 Customer Address **
```
solucion:
SELECT name, street
FROM customers
WHERE city = 'Porto Alegre';
```
![image](https://github.com/user-attachments/assets/e62173ef-5bab-4170-9d23-a84488855b6f)
- ** EJERCICIO 2604 Under 10 or Greater Than 100 **
```
Solucion:
SELECT id, name
FROM products
WHERE price < 10 OR price > 100;
```
![image](https://github.com/user-attachments/assets/56d93a5e-e8df-4fdb-a954-c1c1891f4cb4)

- ** EJERCICIO 2605 Executive Representatives **
```
solucion:
SELECT p.name, pr.name
FROM products p
INNER JOIN
providers pr
ON
p.id_providers = pr.id
INNER JOIN
categories c
ON
p.id_categories = c.id
WHERE 
c.id=6;
```
![image](https://github.com/user-attachments/assets/2aaf5fa7-69db-4601-8967-39e0f7072f0d)
- ** EJERCICIO 2606 Categories **
```
solucion:
SELECT p.id, p.name
FROM products p
JOIN categories c ON p.id_categories = c.id
WHERE c.name LIKE 'super%';
```
![image](https://github.com/user-attachments/assets/5a942937-afff-4228-8b64-d0a5c7b916e1)
- ** EJERCICIO 2607 Providers' City in Alphabetical Order **
```
Solucion:
SELECT DISTINCT (city)
FROM providers
ORDER BY city ASC;
```
![image](https://github.com/user-attachments/assets/cbf31e98-ba44-4a68-8744-ff1cbe245901)
- ** EJERCICIO 2608 Higher and Lower Price **
```
Solucion:
SELECT MAX(price), MIN(price)
FROM products;
```
![image](https://github.com/user-attachments/assets/3c3333f5-42fc-41c5-9ba4-999ecf3b72d6)
- ** EJERCICIO 2609 Products by Categories **
```
Solucion:
SELECT c.name, SUM(p.amount) AS sum
FROM products p
JOIN categories c ON p.id_categories = c.id
GROUP BY c.name;
```
![image](https://github.com/user-attachments/assets/05efd491-164b-43cd-ba33-67b482e81e28)

- ** EJERCICIO 2610 Average Value of Products **
```
Solucion:
SELECT ROUND(AVG(price), 2) AS price
FROM products;
```
![image](https://github.com/user-attachments/assets/fac6504e-a585-44ac-be23-99fd2149c4d4)
- ** EJERCICIO 2611 Action Movies **
```
Solucion:
SELECT m.id, m.name
FROM movies m
JOIN genres g 
ON 
m.id_genres = g.id
WHERE g.description = 'Action';
```
![image](https://github.com/user-attachments/assets/452ac428-2091-45e8-a486-0f20b9a7f06b)

- ** EJERCICIO 2613 Cheap Movies **
```
Solucion:
SELECT m.id, m.name
FROM movies m
INNER JOIN
prices p
ON
m.id_prices = p.id
WHERE
p.value < 2;
```
![image](https://github.com/user-attachments/assets/d20a85ec-5f33-484e-bad7-577059ea94e2)
- ** EJERCICIO 2614 September Rentals **
```
Solucion:
SELECT c.name, r.rentals_date
FROM rentals r
JOIN customers c ON r.id_customers = c.id
WHERE r.rentals_date >= '2016-09-01' AND r.rentals_date < '2016-10-01';
```
![image](https://github.com/user-attachments/assets/aa9a126d-3e06-4256-9642-33bf7543de0a)

- ** EJERCICIO 2615 Expanding the Business **
```
Solucion:
SELECT DISTINCT(city)
FROM customers;
```
![image](https://github.com/user-attachments/assets/731f3034-49a0-4432-b362-81b5fca1b6bc)

- ** EJERCICIO 2616 No Rental **
```
Solucion:
SELECT c.id, c.name
FROM customers c
LEFT JOIN locations l ON c.id = l.id_customers
WHERE l.id_customers IS NULL
ORDER BY c.id;
```
![image](https://github.com/user-attachments/assets/5fe86899-1878-44df-82e4-fc4eee58664c)

- ** EJERCICIO 2617 Provider Ajax SA **
```
Solucion:
SELECT products.name, providers.name
FROM products
INNER JOIN providers ON
products.id_providers=providers.id
WHERE 
providers.name = 'Ajax SA';
```
![image](https://github.com/user-attachments/assets/307c35d8-ca55-4baf-9344-fc64f4e2d9cd)

- ** EJERCICIO 2618 Imported Products **
```
Solucion:
SELECT p.name, pr.name, c.name
FROM
products p
INNER JOIN
providers pr
ON
p.id_providers = pr.id
INNER JOIN
categories c
ON
p.id_categories = c.id
WHERE 
pr.name = 'Sansul SA' AND c.name = 'Imported';
```
![image](https://github.com/user-attachments/assets/4b62bf0c-861e-46b9-9e44-a2c5348b7736)

- ** EJERCICIO 2619 Super Luxury **
```
Solucion:
SELECT p.name, pr.name, p.price
FROM products p
INNER JOIN
providers pr
ON
p.id_providers = pr.id
INNER JOIN 
categories c
ON
p.id_categories = c.id
WHERE
p.price > 1000 AND c.name='Super Luxury';
```
![image](https://github.com/user-attachments/assets/6a5319cd-4f37-4ec5-ad9e-473bc78fe647)

- ** EJERCICIO 2620 Orders in First Half **
```
Solucion:
SELECT
c.name, o.id
FROM
customers c
INNER JOIN
orders o
ON
c.id=o.id_customers 
WHERE 
EXTRACT(MONTH FROM o.orders_date)<=6;
```
![image](https://github.com/user-attachments/assets/8c631907-09dd-481f-a4fc-e8108d3176bd)

- ** EJERCICIO 2621 Amounts Between 10 and 20 **
```
Solucion:
SELECT 
pr.name
FROM
providers p
INNER JOIN
products pr
ON 
p.id = pr.id_providers
WHERE
(pr.amount>=10 AND pr.amount<=20) AND
p.name LIKE 'P%';
```
![image](https://github.com/user-attachments/assets/6bc5be02-9632-4b1c-9e8a-a1ab56054a8f)

- ** EJERCICIO 2622 Legal Person **
```
Solucion:
SELECT c.name
FROM
customers c
INNER JOIN
legal_person lp
ON
c.id = lp.id_customers;
```
![image](https://github.com/user-attachments/assets/bf1f6aa9-d1ef-4e7b-b2d3-ac9a07f25d8e)

- ** EJERCICIO 2623 Categories with Various Products **
```
Solucion:
SELECT 
products.name, categories.name
FROM
products
INNER JOIN
categories
ON
products.id_categories=categories.id
WHERE
products.amount > 100 AND categories.id IN (1,2,3,6,9)
ORDER BY
categories.id ASC;
```
![image](https://github.com/user-attachments/assets/54810e71-896d-4005-a661-d580fdf3d936)

- ** EJERCICIO 2624 Number of Cities per Customers **
```
Solucion:
SELECT COUNT(DISTINCT(city))
FROM customers;
```
![image](https://github.com/user-attachments/assets/acd83124-e8e5-4cfa-a4df-b0d75386d053)

- ** EJERCICIO 2625 CPF Validation **
```
Solucion:
SELECT
 LPAD(SUBSTRING(cpf, 1, 3), 3, '0') || '.' ||
 LPAD(SUBSTRING(cpf, 4, 3), 3, '0') || '.' ||
 LPAD(SUBSTRING(cpf, 7, 3), 3, '0') || '-' ||
 LPAD(SUBSTRING(cpf, 10, 2), 2, '0')
AS
CPF
FROM 
natural_person
```
![image](https://github.com/user-attachments/assets/3ad04b3a-23c7-4b0a-891d-c0f8663f8165)

- ** EJERCICIO 2737 Lawyers **
```
Solucion:
(
  SELECT name, customers_number
  FROM lawyers
  ORDER BY customers_number DESC
  LIMIT 1
)
UNION ALL
(
  SELECT name, customers_number
  FROM lawyers
  ORDER BY customers_number ASC
  LIMIT 1
)
UNION ALL
(
  SELECT 'Average' AS name, CAST(AVG(customers_number) AS INTEGER) AS customers_number
  FROM lawyers
);
```
![image](https://github.com/user-attachments/assets/ffb8a00a-dfe2-467f-af7e-5ee35a3a055f)

- ** EJERCICIO 2738 Contest **
```
Solucion:
SELECT 
c.name,
ROUND(((s.math * 2) + (s.specific * 3) + (s.project_plan * 5)) / 10.0, 2)
AS avg
FROM 
candidate c
JOIN 
score s 
ON 
c.id = s.candidate_id
ORDER BY 
avg DESC;
```
![image](https://github.com/user-attachments/assets/cbccab1c-cec6-4618-b659-bfcbcb572dab)

- ** EJERCICIO 2739 Payday **
```
Solucion:

```
- ** EJERCICIO 2740 League **
```
Solucion:
SELECT 'Podium: ' || team AS name
FROM league
WHERE position <= 3

UNION ALL

SELECT 'Demoted: ' || team AS name
FROM league
WHERE position >= 14;
```
![image](https://github.com/user-attachments/assets/7f8311c0-ee08-4f1f-b9e4-e4d2aa251af4)

- ** EJERCICIO 2741 Payday **
```
Solucion:
SELECT 'Approved: ' || name AS name, grade
FROM students
WHERE grade >= 7
ORDER BY grade DESC;
```
![image](https://github.com/user-attachments/assets/9f23a524-0d42-4a41-8713-a9986f0f81f5)

- ** EJERCICIO 2742 Richard's Multiverse **
```
Solucion:
SELECT lr.name, ROUND(lr.omega * 1.618, 3) AS "The N Factor"
FROM life_registry lr
JOIN dimensions d ON lr.dimensions_id = d.id
WHERE (d.name = 'C875' OR d.name = 'C774')
  AND lr.name LIKE 'Richard%'
ORDER BY lr.omega ASC;
```
![image](https://github.com/user-attachments/assets/d20df2d6-4a63-4434-9b0b-c7033135a649)

- ** EJERCICIO 2743 Number of Characters **
```
Solucion:
SELECT name, LENGTH(name)
FROM
people
ORDER BY LENGTH(name) DESC;
```
![image](https://github.com/user-attachments/assets/2937315b-7b35-4869-8f0d-b2ede2b0025b)

- ** EJERCICIO 2744 Passwords **
```
Solucion:
SELECT id, password, MD5(password)
FROM account;
```
![image](https://github.com/user-attachments/assets/00465fc9-3da8-44e2-9243-60a2644e2791)

- ** EJERCICIO 2745 Taxes **
```
Solucion:
SELECT 
name, ROUND(salary*0.10, 2) as tax
FROM
people
WHERE
salary > 3000;
```
![image](https://github.com/user-attachments/assets/8c9329fb-2e3d-46b1-a6a1-f191e372dc17)

- ** EJERCICIO 2746 Viruses **
```
Solucion:
SELECT REPLACE(name, 'H1', 'X') AS name
FROM virus;
```
![image](https://github.com/user-attachments/assets/615cce18-e129-4815-a1d7-a9e9264320b4)
- ** EJERCICIO 2988 Cearense Championship **
```
Solucion:
SELECT
    t.name,
    COUNT(m.id) AS matches,
    SUM(CASE
        WHEN (t.id = m.team_1 AND m.team_1_goals > m.team_2_goals) OR
             (t.id = m.team_2 AND m.team_2_goals > m.team_1_goals)
        THEN 1 ELSE 0 END) AS victories,
    SUM(CASE
        WHEN (t.id = m.team_1 AND m.team_1_goals < m.team_2_goals) OR
             (t.id = m.team_2 AND m.team_2_goals < m.team_1_goals)
        THEN 1 ELSE 0 END) AS defeats,
    SUM(CASE
        WHEN m.team_1_goals = m.team_2_goals THEN 1 ELSE 0 END) AS draws,
    SUM(CASE
        WHEN (t.id = m.team_1 AND m.team_1_goals > m.team_2_goals) OR
             (t.id = m.team_2 AND m.team_2_goals > m.team_1_goals)
        THEN 3
        WHEN m.team_1_goals = m.team_2_goals THEN 1
        ELSE 0 END) AS score
FROM
    teams t
JOIN
    matches m
    ON t.id = m.team_1 OR t.id = m.team_2
GROUP BY
    t.name
ORDER BY
    score DESC;
```
![image](https://github.com/user-attachments/assets/c0d04be4-6454-4750-a5f2-e1cefa071fb5)
![image](https://github.com/user-attachments/assets/6fc0fb2a-c059-442e-9a8c-d2c91d19070e)

- ** EJERCICIO 2989 Departments and Divisions **
```
Solucion:

```

- ** EJERCICIO 2990 Employees CPF **
```
Solucion:
SELECT 
  e.cpf,
  e.enome,
  d.dnome
FROM 
  empregados e
JOIN 
  departamentos d ON e.dnumero = d.dnumero
WHERE 
  e.cpf NOT IN (SELECT cpf_emp FROM trabalha)
ORDER BY 
  e.cpf;
```
![image](https://github.com/user-attachments/assets/cda34516-69a1-4815-b302-1c76cd2281fa)

- ** EJERCICIO 2991 Department Statistics **
```
Solucion:

```
- ** EJERCICIO 2992 Highest Avarage Salary Divisions **
```
Solucion:

```
- ** EJERCICIO 2993 Most Frequent **
```
Solucion:
SELECT amount
FROM value_table
GROUP BY amount ORDER BY COUNT(amount) DESC LIMIT 1;
```
![image](https://github.com/user-attachments/assets/cd1108dd-7192-4558-a998-0c0fdca0d28e)

- ** EJERCICIO 2994 How much does a Doctor earn? **
```
Solucion:
SELECT d.name, ROUND( SUM(a.hours*150+a.hours*150*(w.bonus/100)),1) AS salary
FROM 
doctors d
INNER JOIN 
attendances a
ON 
d.id = a.id_doctor
INNER JOIN 
work_shifts w
ON
a.id_work_shift = w.id
GROUP BY d.id
ORDER BY salary DESC;
```
![image](https://github.com/user-attachments/assets/b872d607-e81c-4ef4-b473-8744eb9e6284)

- ** EJERCICIO 2995 The Sensor Message **
```
Solucion:
SELECT 
  temperature,
  COUNT(*) AS number_of_records
FROM 
  records
GROUP BY 
  mark, temperature
ORDER BY 
  MIN(id);
```
![image](https://github.com/user-attachments/assets/6fbb7e7e-8703-4530-b432-e7f78bfce1dd)

- ** EJERCICIO 2996 Package Delivery **
```
Solucion:

```

- ** EJERCICIO 2997 Employees Payment **
```
Solucion:

```

- ** EJERCICIO 2998 The Payback **
```
Solucion:
WITH accumulated_profits AS (
  SELECT
    o.client_id,
    o.month,
    SUM(o.profit) OVER (PARTITION BY o.client_id ORDER BY o.month) AS accumulated_profit
  FROM operations o
),
payback_info AS (
  SELECT
    c.id,
    c.name,
    c.investment,
    MIN(CASE WHEN ap.accumulated_profit >= c.investment THEN ap.month ELSE NULL END) AS month_of_payback,
    -- The accumulated profit at the payback month:
    MIN(CASE WHEN ap.accumulated_profit >= c.investment THEN ap.accumulated_profit ELSE NULL END) AS profit_at_payback
  FROM clients c
  LEFT JOIN accumulated_profits ap ON c.id = ap.client_id
  GROUP BY c.id, c.name, c.investment
)
SELECT
  name,
  investment,
  month_of_payback AS month_of_payback,
  COALESCE(profit_at_payback - investment, 0) AS return
FROM payback_info
WHERE month_of_payback IS NOT NULL
ORDER BY return DESC;

```

- ** EJERCICIO 2999 Highest Division Salary **
```
Solucion:

```

- ** EJERCICIO 2301 Update sem Where **
```
Solucion:
SELECT
  name,
  CASE type
    WHEN 'A' THEN 20.0
    WHEN 'B' THEN 70.0
    WHEN 'C' THEN 530.5
  END AS price
FROM products
ORDER BY
  CASE type
    WHEN 'A' THEN 1
    WHEN 'B' THEN 2
    WHEN 'C' THEN 3
  END,
  id DESC;
```
![image](https://github.com/user-attachments/assets/7170e5c9-e194-419d-a291-cc4a3a82b302)
![image](https://github.com/user-attachments/assets/b223f96a-1794-4e1b-a2eb-0313cb2065af)

- ** EJERCICIO 2380 Sillas Adyacentes **
```
Solucion:

```

- ** EJERCICIO 2381 Clasificación de un Árbol **
```
Solucion:

```

- ** EJERCICIO 2382 Seguidores **
```
Solucion:

```

- ** EJERCICIO 2383 Segundo Mayor y Menor **
```
Solucion:

```