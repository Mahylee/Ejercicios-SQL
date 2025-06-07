# SQL HACKER RANK
# Aggregation ###

- ** Avarage Population **
```
SELECT FLOOR(AVG(POPULATION))
FROM CITY;
```
- ** Japan Population **
```
SELECT SUM(POPULATION) FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
- ** Population Density Difference **
```
SELECT MAX(POPULATION) - MIN(POPULATION)
FROM CITY;
```
- ** Revising Aggregations **
```
SELECT AVG(POPULATION) FROM CITY
WHERE DISTRICT = 'California';
```
- ** Revising Aggregations - The counts Function **
```
SELECT COUNT(*) FROM CITY
WHERE POPULATION > 100000;
```
- ** Revising Aggregations - The Sum Function **
```
SELECT SUM(POPULATION) FROM CITY
WHERE DISTRICT = 'California';
```
- ** The Blunder **
```
SELECT
    CEIL(AVG(Salary) - AVG(REPLACE(SALARY, '0', '')))
FROM EMPLOYEES;
```
- ** Top Earners **
```
SELECT salary * months AS earnings, COUNT(*)
FROM Employee
GROUP BY earnings
ORDER BY earnings DESC
LIMIT 1;
```
- ** Weather Observation Station 13 **
```
SELECT 
    TRUNCATE(SUM(LAT_N), 4)
FROM
    STATION
WHERE
    LAT_N BETWEEN 38.7880 AND 137.2345;
```
- ** Weather Observation Station 14 **
```
SELECT
    TRUNCATE(MAX(LAT_N), 4)
FROM
    STATION
WHERE
    LAT_N < 137.2345;
```
- ** Weather Observation Station 15 **
```
SELECT ROUND(LONG_W, 4)
FROM STATION
WHERE LAT_N < 137.2345
ORDER BY LAT_N DESC
LIMIT 1;
```
- ** Weather Observation Station 16 **
```
SELECT 
    ROUND(MIN(LAT_N), 4)
FROM
    STATION
WHERE
    LAT_N > 38.7780;
```
- ** Weather Observation Station 17 **
```
SELECT ROUND(LONG_W, 4)
FROM STATION
WHERE LAT_N > 38.7780
ORDER BY LAT_N
LIMIT 1;
``` 
- ** Weather Observation Station 18 **
```
SELECT
    ROUND(ABS(MAX(LAT_N)  - MIN(LAT_N))
        + ABS(MAX(LONG_W) - MIN(LONG_W)), 4)
FROM 
    STATION;
```
- ** Weather Observation Station 19 **
```
SELECT
    ROUND(SQRT(
        POWER(MAX(LAT_N)  - MIN(LAT_N),  2)
      + POWER(MAX(LONG_W) - MIN(LONG_W), 2)
    ), 4)
FROM 
    STATION;
```
- ** Weather Observation Station 20 **
```
SELECT 
    ROUND(SUM(LAT_N), 2),
    ROUND(SUM(LONG_W), 2)
FROM
    STATION;
```

# BASIC JOIN ###
- ** African Cities **
```
SELECT CITY.NAME 
FROM CITY, COUNTRY
WHERE CITY.COUNTRYCODE = COUNTRY.CODE AND COUNTRY.CONTINENT = 'Africa';
```
- ** Asian Population **
```
SELECT SUM(CITY.POPULATION) 
FROM CITY, COUNTRY
WHERE CITY.COUNTRYCODE = COUNTRY.CODE AND COUNTRY.CONTINENT = 'Asia';
```
- ** Average Population of Each Continent **
```
SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION))
FROM CITY INNER JOIN COUNTRY
ON CITY.COUNTRYCODE = COUNTRY.CODE
GROUP BY COUNTRY.CONTINENT;
```
- ** The Report **
```
SELECT IF (S.Marks < 70, 'NULL', S.Name), G.Grade, S.Marks
FROM Students AS S, Grades AS G
WHERE S.Marks BETWEEN G.Min_Mark AND G.Max_Mark
ORDER BY G.GRADE DESC, S.NAME;
```

# BASIC SELECT ###
- ** Employee Names **
```
SELECT name FROM Employee
ORDER BY name;
```
- ** mployee Salaries **
```
SELECT name FROM Employee
WHERE salary > 2000 AND months < 10
ORDER BY employee_id;
```
- ** Higher Than 75 Marks **
```
SELECT Name FROM STUDENTS
WHERE Marks > 75
ORDER BY RIGHT(Name, 3), ID;
```
- ** Japanese Cities' Attributes **
```
SELECT * FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
- ** Japanese Cities' Names **
```
SELECT NAME FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
- ** Revising the Select Query I **
```
SELECT * FROM CITY
WHERE COUNTRYCODE = 'USA' AND POPULATION > 100000;
```
- ** Revising the Select Query II **
```
SELECT NAME FROM CITY
WHERE COUNTRYCODE = 'USA' AND POPULATION > 120000;
```
- ** Select All **
```
SELECT* FROM CITY;
```
- ** Select By ID **
```
SELECT * FROM CITY
WHERE ID = 1661;
```
- ** Weather Observation Station 1 **
```
SELECT CITY, STATE FROM STATION;
```
- ** Weather Observation Station 10 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '[^aeiou]$';
```
- ** Weather Observation Station 11 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[^aeiou]|[^aeiou]$';
```
- ** Weather Observation Station 12 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[^aeiou].*[^aeiou]$';
```
- ** Weather Observation Station 3 **
```  
SELECT DISTINCT CITY FROM STATION
WHERE ID % 2 = 0;
```
- ** Weather Observation Station 4 **
```
SELECT 
    COUNT(CITY) - COUNT(DISTINCT CITY)
FROM
    STATION;
```
- ** Weather Observation Station 5 **
```
SELECT CITY, LENGTH(CITY) FROM STATION
ORDER BY LENGTH(CITY), CITY
LIMIT 1;

SELECT CITY, LENGTH(CITY) FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY
LIMIT 1;
```
- ** Weather Observation Station 6 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[aeiou]';
```
- ** Weather Observation Station 7 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '[aeiou]$';
```
- ** Weather Observation Station 8 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[aeiou].*[aeiou]$';
```
- ** Weather Observation Station 9 **
```
SELECT DISTINCT CITY FROM STATION
WHERE CITY REGEXP '^[^aeiou]';
```