# SQL-BEECROWD

# LEVEL 1####
- ** EJERCICIO 2603 Customer Address **
```
solucion:
SELECT name, street
FROM customers
WHERE city = 'Porto Alegre';
```
![image](https://github.com/user-attachments/assets/e62173ef-5bab-4170-9d23-a84488855b6f)
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

- ** EJERCICIO 2615 Expanding the Business **
```
Solucion:
SELECT DISTINCT(city)
FROM customers;
```
![image](https://github.com/user-attachments/assets/731f3034-49a0-4432-b362-81b5fca1b6bc)

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

- ** EJERCICIO 2744 Passwords **
```
Solucion:
SELECT id, password, MD5(password)
FROM account;
```
![image](https://github.com/user-attachments/assets/00465fc9-3da8-44e2-9243-60a2644e2791)

- ** EJERCICIO 2746 Viruses **
```
Solucion:
SELECT REPLACE(name, 'H1', 'X') AS name
FROM virus;
```
![image](https://github.com/user-attachments/assets/615cce18-e129-4815-a1d7-a9e9264320b4)

# LEVEL 2####

- ** EJERCICIO 2604 Under 10 or Greater Than 100 **
```
Solucion:
SELECT id, name
FROM products
WHERE price < 10 OR price > 100;
```
![image](https://github.com/user-attachments/assets/56d93a5e-e8df-4fdb-a954-c1c1891f4cb4)

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

- ** EJERCICIO 3480 Adjacent Chairs **
```
solución:
SELECT c1.queue,
       c1.id AS left,
       c2.id AS right
FROM chairs c1
JOIN chairs c2 ON c1.queue = c2.queue AND c1.id + 1 = c2.id
WHERE c1.available = TRUE AND c2.available = TRUE
ORDER BY c1.id;
```

- ** EJERCICIO 3481 Classifying a Tree **
```
solución:
SELECT 
    n.id,
    CASE 
        WHEN n.parent_id IS NULL THEN 'ROOT'
        WHEN c.id IS NULL THEN 'LEAF'
        ELSE 'INNER'
    END AS type
FROM 
    nodes n
LEFT JOIN 
    nodes c ON n.id = c.parent_id
GROUP BY 
    n.id, n.parent_id
ORDER BY 
    n.id;
```

- ** EJERCICIO 3482 Followers **
```
solución:
SELECT
    CASE
        WHEN u1.posts < u2.posts THEN u1.name
        ELSE u2.name
    END AS user_with_fewer_posts,
    
    CASE
        WHEN u1.posts < u2.posts THEN u2.name
        ELSE u1.name
    END AS user_with_more_posts
FROM
    follows f1
JOIN
    follows f2 ON f1.follower_id = f2.followed_id AND f1.followed_id = f2.follower_id
JOIN
    users u1 ON f1.follower_id = u1.id
JOIN
    users u2 ON f1.followed_id = u2.id
WHERE
    u1.id < u2.id  -- prevent duplicate pairs (e.g., avoid (A,B) and (B,A))
ORDER BY
    CASE
        WHEN u1.posts < u2.posts THEN u1.id
        ELSE u2.id
    END;
```
- ** EJERCICIO 3483 Second Largest and Smallest **
```
solucion:
SELECT 
    city_name, population
FROM 
    cities
WHERE 
    population = (SELECT DISTINCT population
                   FROM cities
                   ORDER BY population DESC
                   LIMIT 1 OFFSET 1) -- Segunda mayor población
UNION ALL
SELECT 
    city_name, population
FROM 
    cities
WHERE 
    population = (SELECT DISTINCT population
                   FROM cities
                   ORDER BY population ASC
                   LIMIT 1 OFFSET 1) -- Segunda menor población
ORDER BY 
    population DESC;
```
# LEVEL 3####
- ** EJERCICIO 2606 Categories **
```
solucion:
SELECT p.id, p.name
FROM products p
JOIN categories c ON p.id_categories = c.id
WHERE c.name LIKE 'super%';
```
![image](https://github.com/user-attachments/assets/5a942937-afff-4228-8b64-d0a5c7b916e1)

- ** EJERCICIO 2610 Average Value of Products **
```
Solucion:
SELECT ROUND(AVG(price), 2) AS price
FROM products;
```
![image](https://github.com/user-attachments/assets/fac6504e-a585-44ac-be23-99fd2149c4d4)

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

- ** EJERCICIO 2624 Number of Cities per Customers **
```
Solucion:
SELECT COUNT(DISTINCT(city))
FROM customers;
```
![image](https://github.com/user-attachments/assets/acd83124-e8e5-4cfa-a4df-b0d75386d053)

- ** EJERCICIO 2743 Number of Characters **
```
Solucion:
SELECT name, LENGTH(name)
FROM
people
ORDER BY LENGTH(name) DESC;
```
![image](https://github.com/user-attachments/assets/2937315b-7b35-4869-8f0d-b2ede2b0025b)

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

- ** EJERCICIO 2993 Most Frequent **
```
Solucion:
SELECT amount
FROM value_table
GROUP BY amount ORDER BY COUNT(amount) DESC LIMIT 1;
```
![image](https://github.com/user-attachments/assets/cd1108dd-7192-4558-a998-0c0fdca0d28e)

# LEVEL 4####
- ** EJERCICIO 2602 Basic Select **
```
solucion:
SELECT name
FROM customers
WHERE state='RS';
```
![image](https://github.com/user-attachments/assets/a07e6c02-c6ef-4eaa-b7ef-b9b2dfe0ad51)

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
