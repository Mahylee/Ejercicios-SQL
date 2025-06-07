# SQLZOO

# SELECT basics ####

- **1. SELECT basics **
```
solution: 
SELECT population FROM world
  WHERE name = 'Germany'
```
- **2. SELECT basics **
```
solution:
SELECT name, population FROM world
  WHERE name IN ('Sweden', 'Norway', 'Denmark');
```
- **3. SELECT basics **
```
solution:
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
```
# SELECT basics Quiz ####
- **1. SELECT basics Quiz **
```
SELECT name, population
FROM world
WHERE population BETWEEN 1000000 AND 1250000
```
- **2. SELECT basics Quiz **
```
      SELECT name, population
      FROM world
      WHERE name LIKE "Al%"
```
- **3. SELECT basics Quiz **
```
SELECT name FROM world
 WHERE name LIKE 'a%' OR name LIKE 'l%'
```
- **4. SELECT basics Quiz **
```
SELECT name,length(name)
FROM world
WHERE length(name)=5 and region='Europe'
```
- **5. SELECT basics Quiz **
```
SELECT name, area*2 FROM world WHERE population = 64000
```
- **6. SELECT basics Quiz **
```
SELECT name, area, population
  FROM world
 WHERE area < 50000 AND population < 10000000
```
- **7. SELECT basics Quiz **
```
SELECT name, area/population
FROM world WHERE name IN ('China', 'Nigeria', 'France', 'Australia')
```

# SELECT names #
- **1. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE 'Y%'
```
- **2. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE '%Y'
```
- **3. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE '%x%'
```
- **4. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE '%land'
```
- **5. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE 'C%ia'
```
- **6. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE '%oo%'
```
- **7. SELECT names **
```
solution:
SELECT name FROM world
  WHERE name LIKE '%a%a%a%'
```
- **8. SELECT names **
```
solution:
SELECT name FROM world
 WHERE name LIKE '_t%'
ORDER BY name
```
- **9. SELECT names **
```
solution:
SELECT name FROM world
 WHERE name LIKE '%o__o%'
```
- **10. SELECT names **
```
solution:
SELECT name FROM world
 WHERE length (name)=4
## Harder Questions ##
```
- **12. SELECT names **
```
solution:
SELECT name
  FROM world
 WHERE name=capital
```
- **13. SELECT names **
```
solution:
SELECT name
  FROM world
 WHERE capital LIKE '% City'
```
- **13. SELECT names **
```
solution:
SELECT capital, name
FROM world
WHERE
  capital LIKE CONCAT('%',name,'%')
```
- **14. SELECT names **
```
solution:
SELECT capital, name
FROM world
WHERE
  capital LIKE CONCAT('%',name,'%')
AND 
   length(capital)>length(name)
```
# SELECT from world #
- **1. SELECT from world **
```
solution:
SELECT name, continent, population FROM world
```
- **2. SELECT from world **
```
solution:
SELECT name 
FROM world 
WHERE population >= 200000000;

```
- **3. SELECT from world **
```
solution:
SELECT name, gdp / population AS per_capita_gdp
FROM world
WHERE population >= 200000000;
```
- **4. SELECT from world **
```
solution:
SELECT name, population / 1000000 AS population_millions
FROM world
WHERE continent = 'South America';
```
- **5. SELECT from world **
```
solution:
SELECT name, population
FROM world
WHERE name IN ('France', 'Germany', 'Italy');
```
- **6. SELECT from world **
```
solution:
SELECT name
FROM world
WHERE name LIKE '%United%';
```
- **7. SELECT from world **
```
solution:
SELECT name, population, area
FROM world
WHERE area > 3000000 OR population > 250000000;
```
- **8. SELECT from world **
```
solution:
SELECT name, population, area
FROM world
WHERE (area > 3000000 AND population <= 250000000) 
   OR (population > 250000000 AND area <= 3000000);
```
- **9. SELECT from world **
```
solution:
SELECT name, 
       ROUND(population / 1000000, 2) AS population_millions, 
       ROUND(gdp / 1000000000, 2) AS gdp_billions
FROM world
WHERE continent = 'South America';
```
- **10. SELECT from world **
```
solution:
SELECT name, 
       ROUND(gdp / population, -3) AS per_capita_gdp
FROM world
WHERE gdp >= 1000000000000;
```
- **11. SELECT from world **
```
solution:
SELECT name, capital
FROM world
WHERE LENGTH(name) = LENGTH(capital);
```
- **12. SELECT from world **
```
solution:
SELECT name, capital
FROM world
WHERE LEFT(name, 1) = LEFT(capital, 1)
  AND name <> capital;
```
- **13. SELECT from world **
```
solution:
SELECT name
FROM world
WHERE name LIKE '%a%' 
  AND name LIKE '%e%' 
  AND name LIKE '%i%' 
  AND name LIKE '%o%' 
  AND name LIKE '%u%' 
  AND name NOT LIKE '% %';
```
# SELECT from world Quiz ####
- **1. SELECT from world Quiz **
SELECT name, continent, population FROM world;
- **2. SELECT from world Quiz **
SELECT name FROM world
WHERE population >= 200000000
- **3. SELECT from world Quiz **
select name,gdp/population from world
WHERE population > 200000000
- **4. SELECT from world Quiz **
SELECT name, population/1000000
FROM world WHERE continent = 'South America'
- **5. SELECT from world Quiz **
SELECT name, population
FROM world
WHERE name in ('France', 'Germany', 'Italy')
- **6. SELECT from world Quiz **
SELECT name
FROM world
WHERE name LIKE '%United%'
- **7. SELECT from world Quiz **
select name,gdp/population from world
WHERE population > 200000000
- **8. SELECT from world Quiz **
select name,gdp/population from world
WHERE population > 200000000
# SELECT from nobel ####
- **1. SELECT from nobel **
```
Solution:
SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
```
- **2. SELECT from nobel **
```
Solution:
SELECT winner
FROM nobel
WHERE yr = 1962
  AND subject = 'literature';
```
- **3. SELECT from nobel **
```
Solution:
SELECT yr, subject
FROM nobel
WHERE winner = 'Albert Einstein';
```
- **4. SELECT from nobel **
```
Solution:
SELECT winner
FROM nobel
WHERE subject = 'peace'
  AND yr >= 2000;
```
- **5. SELECT from nobel **
```
Solution:
SELECT yr, subject, winner
FROM nobel
WHERE subject = 'literature'
  AND yr BETWEEN 1980 AND 1989;
```
- **6. SELECT from nobel **
```
Solution:
SELECT *
FROM nobel
WHERE winner IN ('Theodore Roosevelt',
'Thomas Woodrow Wilson', 'Jimmy Carter',
'Barack Obama');
```
- **7. SELECT from nobel **
```
Solution:
SELECT winner
FROM nobel
WHERE winner LIKE 'john%'
```
- **8. SELECT from nobel **
```
Solution:
SELECT yr, subject, winner
FROM nobel
WHERE subject = 'physics' AND yr = 1980

UNION

SELECT yr, subject, winner
FROM nobel
WHERE subject = 'chemistry' AND yr = 1984;
```
- **9. SELECT from nobel **
```
Solution:
SELECT yr, subject, winner
FROM nobel
WHERE yr = 1980
  AND subject NOT IN ('chemistry', 'medicine');
```
- **10. SELECT from nobel **
```
Solution:
SELECT yr, subject, winner
FROM nobel
WHERE subject = 'medicine' 
  AND yr < 1910

UNION

SELECT yr, subject, winner
FROM nobel
WHERE subject = 'literature' 
  AND yr >= 2004;
```
- **11. SELECT from nobel **
```
Solution:
SELECT *
FROM nobel
WHERE winner = 'PETER GRÜNBERG';
```
- **12. SELECT from nobel **
```
Solution:
SELECT *
FROM nobel
WHERE winner = 'EUGENE O''NEILL';
```
- **13. SELECT from nobel **
```
Solution:
SELECT winner, yr, subject
FROM nobel
WHERE winner LIKE 'Sir%'
ORDER BY yr DESC, winner ASC
```
- **14. SELECT from nobel **
```
Solution:
SELECT winner, subject
 FROM nobel
WHERE yr=1984
ORDER BY subject IN ('physics', 'chemistry'),subject,winner
```
# SELECT from nobel Quiz ####
- **1. SELECT from nobel Quiz **
SELECT name FROM nobel
 WHERE winner LIKE '%C%' AND winner LIKE '%n%'
- **2. SELECT from nobel Quiz **
SELECT COUNT(subject) FROM nobel
 WHERE subject = 'Chemistry'
   AND BETWEEN 1950 and 1960
- **3. SELECT from nobel Quiz **
SELECT COUNT(DISTINCT yr) FROM nobel
 WHERE yr IN (SELECT DISTINCT yr FROM nobel WHERE subject <> 'Medicine')
- **4. SELECT from nobel Quiz **
SELECT subject, winner FROM nobel WHERE winner LIKE 'Sir%' AND yr LIKE '196%'
- **5. SELECT from nobel Quiz **
SELECT yr FROM nobel
 WHERE subject NOT IN(SELECT yr 
                        FROM nobel
                       WHERE subject IN ('Chemistry','Physics'))
- **6. SELECT from nobel Quiz **
SELECT DISTINCT yr
  FROM nobel
 WHERE subject='Medicine' AND
       subject NOT IN(SELECT yr from nobel
                      WHERE subject='Literature')
  AND  yr NOT IN (SELECT yr
                    FROM nobel
                   WHERE subject='Peace')
- **7. SELECT from nobel Quiz **
SELECT subject, COUNT(subject) 
   FROM nobel 
  WHERE yr ='1960' 
  GROUP BY subject
# SELECT in SELECT ####
- **1. SELECT in SELECT **
```
Solution:
SELECT name
FROM world
WHERE population > (SELECT population FROM world WHERE name = 'Russia');
```
- **2. SELECT in SELECT **
```
Solution:
SELECT name
FROM world
WHERE continent = 'Europe'
  AND (gdp / population) > (SELECT gdp / population FROM world WHERE name = 'United Kingdom');
```
- **3. SELECT in SELECT **
```
Solution:
SELECT name, continent
FROM world
WHERE continent IN (
    SELECT continent
    FROM world
    WHERE name IN ('Argentina', 'Australia')
)
ORDER BY name;
```
- **4. SELECT in SELECT **
```
Solution:
SELECT name, population
FROM world
WHERE population > (SELECT population FROM world WHERE name = 'United Kingdom')
  AND population < (SELECT population FROM world WHERE name = 'Germany');
```
- **5. SELECT in SELECT **
```
Solution:
SELECT name, 
       CONCAT(ROUND((population / (SELECT population FROM world WHERE name = 'Germany')) * 100, 0), '%') AS percentage
FROM world
WHERE continent = 'Europe';
```
- **6. SELECT in SELECT **
```
Solution:
SELECT name
FROM world
WHERE gdp > (SELECT MAX(gdp) FROM world WHERE continent = 'Europe')
  AND gdp IS NOT NULL;
```
- **7. SELECT in SELECT **
```
Solution:
SELECT continent, name, area
FROM world x
WHERE area >= ALL
  (SELECT area FROM world y
   WHERE y.continent = x.continent
     AND area > 0);
```
- **8. SELECT in SELECT **
```
Solution:
SELECT continent, name
FROM world
WHERE (continent, name) IN (
    SELECT continent, MIN(name)
    FROM world
    GROUP BY continent
);
```
- **9. SELECT in SELECT **
```
Solution:
SELECT name, continent, population
FROM world
WHERE continent IN (
    SELECT continent
    FROM world
    GROUP BY continent
    HAVING MAX(population) <= 25000000
);
```
- **10. SELECT in SELECT **
```
Solution:
SELECT name, continent
FROM world x
WHERE population/3 > ALL(
SELECT population
FROM world y
WHERE x.continent = y.continent
AND x.name != y.name)
```
# SELECT in SELECT Quiz ####
- **1. SELECT in SELECT Quiz **
 SELECCIONAR región , nombre , DE bbc x DONDE población <= TODOS ( SELECCIONAR población DE bbc y DONDE y . región = x . región Y población > 0 )
- **2. SELECT in SELECT Quiz **
 SELECCIONAR nombre , región , población DE bbc x DONDE 50000 < TODO ( SELECCIONAR población DE bbc y DONDE población > 0 ) 
- **3. SELECT in SELECT Quiz **
SELECCIONAR nombre , región DE bbc x DONDE población < TODOS ( SELECCIONAR población / 3 DE bbc y DONDE y . región = x . región Y y . nombre != x . nombre )  
- **4. SELECT in SELECT Quiz **
SELECCIONAR nombre DE bbc DONDE población > ( SELECCIONAR población DE bbc DONDE nombre = 'Reino Unido' ) Y región EN ( SELECCIONAR región DE bbc DONDE nombre = 'Reino Unido' )   
- **5. SELECT in SELECT Quiz **
SELECCIONAR nombre DE bbc DONDE pib > ( SELECCIONAR MÁX ( pib ) DE bbc DONDE región = 'África' )   
- **6. SELECT in SELECT Quiz **
SELECCIONAR nombre DE bbc DONDE población < ( SELECCIONAR población DE bbc DONDE nombre = 'Rusia' ) Y población > ( SELECCIONAR población DE bbc DONDE nombre = 'Dinamarca' )  
- **7. SELECT in SELECT Quiz **
SELECCIONAR nombre DE bbc
 DONDE población > TODOS
       (SELECCIONAR MAX(población)
          DE la BBC
         DONDE región = 'Europa')
   Y región = 'Asia del Sur'
# SUM and COUNT ####
- **1. SUM and COUNT **
```
Solution:
SELECT SUM(population)
FROM world
```
- **2. SUM and COUNT **
```
Solution:
SELECT DISTINCT continent
FROM world;
```
- **3. SUM and COUNT **
```
Solution:
SELECT SUM(gdp) AS total_gdp
FROM world
WHERE continent = 'Africa';
```
- **4. SUM and COUNT **
```
Solution:
SELECT COUNT(*)
FROM world
WHERE area >= 1000000;
```
- **5. SUM and COUNT **
```
Solution:
SELECT SUM(population)
FROM world
WHERE name IN ('Estonia', 'Latvia', 'Lithuania');
```
- **6. SUM and COUNT **
```
Solution:
SELECT continent, COUNT(name) AS num_countries
FROM world
GROUP BY continent;
```
- **7. SUM and COUNT **
```
Solution:
SELECT continent, COUNT(name) AS num_countries
FROM world
WHERE population >= 10000000
GROUP BY continent;
```
- **8. SUM and COUNT **
```
Solution:
SELECT continent
FROM world
GROUP BY continent
HAVING SUM(population) >= 100000000;
```
# SUM and COUNT Quiz ####
- **1. SUM and COUNT Quiz **
 SELECT population FROM bbc WHERE region = 'Europe' SUM BY region
- **2. SUM and COUNT Quiz **
 SELECT COUNT(name) FROM bbc WHERE population < 150000
- **3. SUM and COUNT Quiz **
AVG(), COUNT(), FIRST(), LAST(), SUM()
AVG(), COUNT(), MAX(), MEDIAN(), MIN(), ROUND(), SUM()
AVG(), COUNT(), CONCAT(), FIRST(), LAST(), MAX(), MIN(), SUM()
AVG(), COUNT(), MAX(), MIN(), SUM()
COUNT(), SUM()
- **4. SUM and COUNT Quiz **
 SELECT region, SUM(area)
   FROM bbc 
  WHERE SUM(area) > 15000000 
  GROUP BY region
- **5. SUM and COUNT Quiz **
 SELECT AVG(population) FROM bbc WHERE name = ('Poland', 'Germany', 'Denmark')
- **6. SUM and COUNT Quiz **
 SELECT region, COUNT(population)/COUNT(area) AS density FROM bbc GROUP BY region
- **7. SUM and COUNT Quiz **
 SELECT name, density AS population/area FROM bbc WHERE population = (SELECT MAX(population) FROM bbc)
- **8. SUM and COUNT Quiz **
 SELECT region, SUM(area) 
   FROM bbc 
  GROUP BY region 
  HAVING SUM(area)<= 20000000
# JOIN ####
- **1. JOIN **
```
Solution:
SELECT matchid, player 
FROM goal 
WHERE teamid = 'GER';
```
- **2. JOIN **
```
Solution:
SELECT id, stadium, team1, team2
FROM game
WHERE id = 1012;
```
- **3. JOIN **
```
Solution:
SELECT player, teamid, stadium, mdate
FROM game
JOIN goal ON game.id = goal.matchid
WHERE teamid = 'GER';
```
- **4. JOIN **
```
Solution:
SELECT team1, team2, player
FROM game
JOIN goal ON game.id = goal.matchid
WHERE player LIKE 'Mario%';
```
- **5. JOIN **
```
Solution:
SELECT player, teamid, coach, gtime
FROM goal
JOIN eteam ON goal.teamid = eteam.id
WHERE gtime <= 10;
```
- **6. JOIN **
```
Solution:
select mdate, teamname from game JOIN eteam ON
(team1=eteam.id) where coach = 'Fernando Santos'
```
- **7. JOIN **
```
Solution:
SELECT goal.player
FROM game
JOIN goal ON game.id = goal.matchid
WHERE game.stadium = 'National Stadium, Warsaw';
```
- **8. JOIN **
```
Solution:
SELECT distinct player
FROM game JOIN goal ON matchid = id 
WHERE (team1='GER' OR team2='GER') AND teamid <> 'GER'
```
- **9. JOIN **
```
Solution:
SELECT teamname, COUNT(*)
FROM eteam JOIN goal ON id=teamid
GROUP BY teamname;
```
- **10. JOIN **
```
Solution:
SELECT stadium, COUNT(*) AS total_goals
FROM game
JOIN goal ON game.id = goal.matchid
GROUP BY stadium;
```
- **11. JOIN **
```
Solution:
SELECT game.id AS matchid, game.mdate AS date, COUNT(goal.matchid) AS total_goals
FROM game
JOIN goal ON game.id = goal.matchid
WHERE game.team1 = 'POL' OR game.team2 = 'POL'
GROUP BY game.id, game.mdate;
```
- **12. JOIN **
```
Solution:
SELECT game.id AS matchid, game.mdate AS date, COUNT(goal.matchid) AS goals_scored_by_GER
FROM game
JOIN goal ON game.id = goal.matchid
WHERE (game.team1 = 'GER' AND goal.teamid = 'GER') 
   OR (game.team2 = 'GER' AND goal.teamid = 'GER')
GROUP BY game.id, game.mdate;
```
- **13. JOIN **
```
Solution:
SELECT mdate,
  team1, sum(CASE WHEN teamid=team1 THEN 1 ELSE 0 END) score1, team2,sum(CASE WHEN teamid=team2 THEN 1 ELSE 0 END) score2
  FROM game JOIN goal ON matchid = id
GROUP BY mdate,matchid,team1,team2
order by mdate, matchid, team1, team2
```
# JOIN Quiz ####
- **1. JOIN Quiz **
 eteam JOIN game ON (id=team1)
 eteam JOIN game ON (id=team2)
 eteam JOIN goal ON (teamid=id)
 game  JOIN goal ON (id=matchid)
 game  JOIN goal ON (team1=teamid OR team2=teamid)
- **2. JOIN Quiz **
 gtime, mdate, stadium, matchid
 mdate, stadium, id
 matchid, teamid, player, gtime, id, teamname, coach
 matchid, teamid, player, gtime, mdate, stadium, team1
 stadium, team1, team2
- **3. JOIN Quiz **
SELECT player, teamid, COUNT(*)
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = "GRE" OR team2 = "GRE")
   AND teamid != 'GRE'
 GROUP BY player, teamid
SELECT player, teamid, COUNT(*)
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = "GRE") AND teamid != 'GRE'
 GROUP BY player, teamid
SELECT player, teamid, COUNT(*)
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = "POL" OR team2 = "POL")
   AND teamid != 'POL'
 GROUP BY player, teamid
SELECT player, teamid, COUNT(*)
  FROM game JOIN goal WITH matchid = id
 WHERE (team1 = "GRE" OR team2 = "GRE")
   AND teamid != 'GRE'
 GROUP BY player, teamid
SELECT player, teamid
  FROM game JOIN goal ON matchid = id
 WHERE (team1 = "GRE" OR team2 = "GRE")
   AND teamid != 'GRE'
 GROUP BY player, teamid
- **4. JOIN Quiz **
SELECT DISTINCT teamid, mdate
  FROM goal JOIN game on (matchid=id)
 WHERE mdate = '9 June 2012'
- **5. JOIN Quiz **
  SELECT DISTINCT player, teamid 
  FROM game JOIN goal ON matchid = id 
  WHERE stadium = 'National Stadium, Warsaw' 
 AND (team1 = 'GER' OR team2 = 'GER')
   AND teamid != 'GER'
  SELECT DISTINCT player, teamid 
   FROM game JOIN goal ON matchid = id 
  WHERE stadium = 'National Stadium, Warsaw' 
 AND (team1 = 'POL' OR team2 = 'POL')
   AND teamid != 'POL'
 
 SELECT DISTINCT player, teamid 
   FROM game JOIN goal ON matchid = id 
  WHERE stadium = 'National Stadium, Warsaw' AND teamid != 'POL'
 
 SELECT DISTINCT player, teamid 
   FROM game JOIN goal ON matchid = id 
  WHERE stadium = 'Stadion Miejski (Wroclaw)' 
 AND (team1 = 'POL' OR team2 = 'POL')
  AND teamid != 'POL'
 
 SELECT DISTINCT stadium, mdate 
   FROM game JOIN goal ON matchid = id 
  WHERE stadium = 'National Stadium, Warsaw' 
 AND (team1 = 'POL' OR team2 = 'POL')
  AND teamid != 'POL'
- **6. JOIN Quiz **
SELECT DISTINCT player, teamid, gtime
  FROM game JOIN goal ON matchid = id
 WHERE stadium = 'National Stadium, Warsaw'
   AND (( teamid = team2 AND team1 != 'ITA') OR ( teamid = team1 AND team2 != 'ITA'))
SELECT DISTINCT player, teamid, gtime
  FROM game JOIN goal ON matchid = id
 WHERE stadium = 'Stadion Miejski (Wroclaw)'
   AND (( teamid = team2 AND team1 != 'ESP') OR ( teamid = team1 AND team2 != 'ESP'))
SELECT DISTINCT player, teamid, gtime
  FROM game JOIN goal ON matchid = id
 WHERE stadium = 'Stadion Miejski (Wroclaw)'
   AND (( teamid = team2 AND team1 != 'ITA') OR ( teamid = team1 AND team2 != 'ITA'))
- **7. JOIN Quiz **
SELECT teamname, COUNT(*)
  FROM eteam JOIN goal ON teamid = id
 GROUP BY teamname
HAVING COUNT(*) < 3
# More JOIN ####
- **1. More JOIN **
```
Solution:
SELECT id, title
 FROM movie
 WHERE yr=1962
```
- **2. More JOIN **
```
Solution:
SELECT yr
FROM movie
WHERE title='Citizen Kane'
```
- **3. More JOIN **
```
Solution:
SELECT id, title, yr
FROM movie
WHERE title LIKE '%Star Trek%'
ORDER BY yr;
```
- **4. More JOIN **
```
Solution:
SELECT id
FROM actor
WHERE name = 'Glenn Close';
```
- **5. More JOIN **
```
Solution:
SELECT id
FROM movie
WHERE title = 'Casablanca'
```
- **6. More JOIN **
```
Solution:
SELECT actor.name
FROM actor
JOIN casting ON actor.id = casting.actorid
WHERE casting.movieid = 11768;
```
- **7. More JOIN **
```
Solution:
SELECT actor.name
FROM actor
JOIN casting ON actor.id = casting.actorid
JOIN movie ON casting.movieid = movie.id
WHERE movie.title = 'Alien';

```
- **8. More JOIN **
```
Solution:
SELECT movie.title
FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE actor.name = 'Harrison Ford';
```
- **9. More JOIN **
```
Solution:
SELECT movie.title
FROM movie
JOIN casting ON movie.id = casting.movieid
JOIN actor ON actor.id = casting.actorid
WHERE actor.name = 'Harrison Ford'
  AND casting.ord != 1;
```
- **10. More JOIN **
```
Solution:
SELECT title,name
FROM movie 
JOIN casting 
JOIN actor 
WHERE casting.ord = 1
AND movie.id=casting.movieid
AND actor.id=casting.actorid
AND movie.yr = 1962
```
- **11. More JOIN **
```
Solution:
SELECT yr,COUNT(title)FROM 
 movie JOIN casting ON movie.id=movieid
   JOIN actor ON actorid=actor.id
where name='Rock Hudson'
GROUP BY yr
HAVING COUNT(title) > 2
```
- **12. More JOIN **
```
Solution:
SELECT m.title, a.name AS leading_actor
FROM movie m
JOIN casting c ON m.id = c.movieid
JOIN actor a ON c.actorid = a.id
WHERE c.ord = 1
  AND m.id IN (
      SELECT m.id
      FROM movie m
      JOIN casting c ON m.id = c.movieid
      JOIN actor a ON c.actorid = a.id
      WHERE a.name = 'Julie Andrews'
  )
ORDER BY m.title;
```
- **13. More JOIN **
```
Solution:
SELECT a.name
FROM actor a
JOIN casting c ON a.id = c.actorid
WHERE c.ord = 1  -- This ensures the actor is in the starring role
GROUP BY a.name
HAVING COUNT(c.movieid) >= 15
ORDER BY a.name;
```
- **14. More JOIN **
```
Solution:
SELECT m.title, COUNT(c.actorid) AS actor_count
FROM movie m
JOIN casting c ON m.id = c.movieid
WHERE m.yr = 1978
GROUP BY m.title
ORDER BY actor_count DESC, m.title;
```
- **15. More JOIN **
```
Solution:
SELECT DISTINCT a.name
FROM actor a
JOIN casting c ON a.id = c.actorid
JOIN movie m ON c.movieid = m.id
WHERE m.id IN (
    SELECT movieid
    FROM casting
    JOIN actor ON casting.actorid = actor.id
    WHERE actor.name = 'Art Garfunkel'
)
AND a.name != 'Art Garfunkel';
```
# More JOIN Quiz ####
- **1. More JOIN Quiz **
```
SELECT JOIN(name FROM actor, movie
       ON actor.id:director WHERE gross < budget)
 GROUP BY name
SELECT name
 FROM actor INNER JOIN movie BY actor.id = director
 HAVING gross < budget
SELECT name
  FROM actor INNER JOIN movie ON actor.id = director
 WHERE gross < budget
SELECT name
  FROM actor INNER JOIN movie ON actor.id:director
 WHERE gross < budget
SELECT name
  FROM director INNER JOIN movie ON movie.id = director.id
 WHERE gross < budget
 ```
- **2. More JOIN Quiz **
```
SELECT JOIN(name FROM actor, movie
       ON actor.id:director WHERE gross < budget)
 GROUP BY name
SELECT name
 FROM actor INNER JOIN movie BY actor.id = director
 HAVING gross < budget
SELECT name
  FROM actor INNER JOIN movie ON actor.id = director
 WHERE gross < budget
SELECT name
  FROM actor INNER JOIN movie ON actor.id:director
 WHERE gross < budget
SELECT name
  FROM director INNER JOIN movie ON movie.id = director.id
 WHERE gross < budget
 ```
- **3. More JOIN Quiz **
```
SELECT name, COUNT(movieid)
  FROM actor JOIN casting ON actorid=actor.id
 WHERE name IN 'John %'
 GROUP BY name ORDER BY 2
SELECT name, COUNT(movieid)
  FROM actor JOIN casting ON actorid=actor.id
 WHERE name LIKE 'J%'
 GROUP BY name ORDER BY 2 DESC
SELECT name, COUNT(movieid)
  FROM casting JOIN actor ON actorid=actor.id
 WHERE name LIKE 'John %'
 GROUP BY name ORDER BY 2 DESC
SELECT name, COUNT(movieid)
  FROM casting JOIN actor
 WHERE (actorid ON actor.id)
   AND name LIKE 'John %'
 GROUP BY name ORDER BY 2 DESC
SELECT name, COUNT(movieid)
  FROM casting JOIN actor
 WHERE name LIKE 'John %'
 GROUP BY name ORDER BY COUNT(movieid) DESC
 ```
- **4. More JOIN Quiz **
```
 SELECT title 
   FROM movie JOIN casting ON (movieid=movie.id)
              JOIN actor   ON (actorid=actor.id)
  WHERE name='Paul Hogan' AND ord = 1
  ```
- **5. More JOIN Quiz **
```
SELECT name
  FROM movie JOIN casting
   AND actor ON movie.id = movieid
   AND actor.id = actorid
 WHERE ord = 1
  AND actor = 351
SELECT name
  FROM movie JOIN casting
  JOIN actor ON movie.id = movieid
    OR actor.id = actorid
 WHERE ord = 1 AND director = 351
SELECT name
  FROM movie JOIN casting ON movie.id = movieid
  JOIN actor ON actor.id = actorid
 WHERE ord = 1 AND actorid = 351
SELECT name
  FROM movie JOIN casting ON movie.id = movieid
  JOIN actor ON actor.id = actorid
WHERE ord = 1 AND director = 351
SELECT name
  FROM movie JOIN casting ON movie.id = actorid
  JOIN actor ON actor.id = movieid
 WHERE director = 351
 ```
- **6. More JOIN Quiz **
```
link the director column in movies with the id column in actor
join casting to itself
link the actor column in movies with the primary key in actor
connect the primary keys of movie and actor via the casting table
link the director column in movies with the primary key in actor
connect the primary keys of movie and actor via the casting table
link the director column in movies with the primary key in actor
connect the primary keys of movie and casting via the actor table
link the movie column in actor with the director column in actor
connect movie and actor via the casting table
```
- **7. More JOIN Quiz **
```
 SELECT title, yr 
   FROM movie, casting, actor 
  WHERE name='Robert De Niro' AND movieid=movie.id AND actorid=actor.id AND ord = 3
```
# Using NULL ####
- **1. Using NULL **
```
Solution:
SELECT name
FROM teacher
WHERE dept IS NULL;
```
- **2. Using NULL **
```
Solution:
SELECT teacher.name, dept.name
 FROM teacher INNER JOIN dept
           ON (teacher.dept=dept.id)
```
- **3. Using NULL **
```
Solution:
SELECT teacher.name, dept.name 
FROM teacher 
LEFT JOIN dept 
 ON (teacher.dept=dept.id)
```
- **4. Using NULL **
```
Solution:
SELECT teacher.name, dept.name 
FROM teacher 
RIGHT JOIN dept 
 ON (teacher.dept=dept.id)
```
- **5. Using NULL **
```
Solution:
SELECT name, COALESCE(mobile, '07986 444 2266') 
FROM teacher;
```
- **6. Using NULL **
```
Solution:
SELECT teacher.name, COALESCE(dept.name, 'None')
FROM teacher
LEFT JOIN dept 
 ON (teacher.dept=dept.id)
```
- **7. Using NULL **
```
Solution:
SELECT 
    COUNT(teacher.id) AS number_of_teachers,
    COUNT(teacher.mobile) AS number_of_mobile_phones
FROM teacher;
```
- **8. Using NULL **
```
Solution:
SELECT dept.name, COUNT(teacher.name) 
FROM teacher
RIGHT JOIN dept
    ON (teacher.dept=dept.id)
GROUP BY dept.name;
```
- **9. Using NULL **
```
Solution:
SELECT name, 
CASE WHEN teacher.dept = 1 OR teacher.dept = 2 THEN 'Sci' ELSE 'Art' END
FROM teacher
```
- **10. Using NULL **
```
Solution:
SELECT name, 
CASE 
WHEN teacher.dept = 1 OR teacher.dept = 2 THEN 'Sci'
WHEN teacher.dept = 3 THEN'Art'
ELSE 'None'END
FROM teacher
```
# Using NULL Quiz ####
- **1. Using NULL Quiz **
```
SELECT teacher.name, dept.name FROM teacher JOIN dept ON (dept = id)
 SELECT teacher.name, dept.name FROM teacher, dept INNER JOIN ON (teacher.dept = dept.id)
 SELECT teacher.name, dept.name FROM teacher, dept JOIN WHERE(teacher.dept = dept.id)
 SELECT teacher.name, dept.name FROM teacher OUTER JOIN dept ON dept.id
 SELECT teacher.name, dept.name FROM teacher LEFT OUTER JOIN dept ON (teacher.dept = dept.id)
 ```
- **2. Using NULL Quiz **
```
 SELECT dept.name FROM teacher JOIN dept ON (dept.id = (SELECT dept FROM teacher WHERE name = 'Cutflower'))
 SELECT dept.name FROM teacher JOIN dept ON (dept.id = teacher.dept) WHERE dept.id = (SELECT dept FROM teacher HAVING name = 'Cutflower')
 SELECT dept.name FROM teacher JOIN dept ON (dept.id = teacher.dept) WHERE teacher.name = 'Cutflower'
 SELECT dept.name FROM teacher JOIN dept WHERE dept.id = (SELECT dept FROM teacher WHERE name = 'Cutflower')
 SELECT name FROM teacher JOIN dept ON (id = dept) WHERE id = (SELECT dept FROM teacher WHERE name = 'Cutflower')
 ```
- **3. Using NULL Quiz **
```
 SELECT dept.name, COUNT(*) FROM teacher LEFT JOIN dept ON dept.id = teacher.dept
 SELECT dept.name, COUNT(teacher.name) FROM teacher, dept JOIN ON dept.id = teacher.dept GROUP BY dept.name
 SELECT dept.name, COUNT(teacher.name) FROM teacher JOIN dept ON dept.id = teacher.dept GROUP BY dept.name
 SELECT dept.name, COUNT(teacher.name) FROM teacher LEFT OUTER JOIN dept ON dept.id = teacher.dept GROUP BY dept.name
 SELECT dept.name, COUNT(teacher.name) FROM teacher RIGHT JOIN dept ON dept.id = teacher.dept GROUP BY dept.name
 ```
- **4. Using NULL Quiz **
```
display 0 in result column for all teachers
display 0 in result column for all teachers without department
do nothing - the statement is incorrect
set dept value of all teachers to 0
set dept value of all teachers without department to 0
```
- **5. Using NULL Quiz **
```
SELECT name,
       CASE WHEN phone = 2752 THEN 'two'
            WHEN phone = 2753 THEN 'three'
            WHEN phone = 2754 THEN 'four'
            END AS digit
  FROM teacher
  ```
- **6. Using NULL Quiz **
```
 SELECT name, 
      CASE 
       WHEN dept 
        IN (1) 
        THEN 'Computing' 
       ELSE 'Other' 
      END 
  FROM teacher
  ```
# self JOIN ####
- **1. self JOIN **
```
Solution:
SELECT COUNT(*) 
FROM stops
```
- **2. self JOIN **
```
Solution:
SELECT id
FROM stops
WHERE name = 'Craiglockhart'
```
- **3. self JOIN **
```
Solution:
SELECT stops.id, stops.name
FROM stops
JOIN route ON stops.id = route.stop
WHERE route.num = '4' AND route.company = 'LRT';
```
- **4. self JOIN **
```
Solution:
SELECT company, num, COUNT(*)
FROM route
WHERE stop = 149 OR stop = 53
GROUP BY company, num
HAVING COUNT(*) = 2;
```
- **5. self JOIN **
```
Solution:
SELECT a.company, a.num, a.stop, b.stop
FROM route a
JOIN route b ON (a.company = b.company AND a.num = b.num)
WHERE a.stop = 53 AND b.stop = 149;
```
- **6. self JOIN **
```
Solution:
SELECT a.company, a.num, stopa.name, stopb.name
FROM route a
JOIN route b ON (a.company = b.company AND a.num = b.num)
JOIN stops stopa ON (a.stop = stopa.id)
JOIN stops stopb ON (b.stop = stopb.id)
WHERE stopa.name = 'Craiglockhart' AND stopb.name = 'London Road';
```
- **7. self JOIN **
```
Solution:
SELECT DISTINCT a.company,a.num
FROM route a JOIN route b ON 
(a.company=b.company AND a.num=b.num)
JOIN stops stopa ON(a.stop=stopa.id)
JOIN stops stopb ON(b.stop=stopb.id)
WHERE stopa.name='Haymarket' AND stopb.name= 'Leith'
```
- **8. self JOIN **
```
Solution:
SELECT a.company, a.num
FROM route a
JOIN route b ON (a.company = b.company AND a.num = b.num)
JOIN stops stopa ON (a.stop = stopa.id)
JOIN stops stopb ON (b.stop = stopb.id)
WHERE stopa.name = 'Craiglockhart' AND stopb.name = 'Tollcross';
```
- **9. self JOIN **
```
Solution:
SELECT DISTINCT stopb.name,a.company,a.num
FROM route a JOIN route b ON 
(a.company=b.company AND a.num=b.num)
JOIN stops stopa ON(a.stop=stopa.id)
JOIN stops stopb ON(b.stop=stopb.id)
WHERE stopa.name='Craiglockhart' 
AND a.company='LRT'
```
# self JOIN Quiz ####
- **1. self JOIN Quiz  **
```
SELECT DISTINCT a.name, b.name
  FROM stops a JOIN route z IN a.id=z.stop
  JOIN route y ON y.num = z.num
  JOIN stops b IN y.stop=b.id
 WHERE a.name='Craiglockhart' AND b.name ='Haymarket'
SELECT DISTINCT a.name, b.name
  FROM stops a JOIN route z ON a.id=z.stop
  JOIN route y JOIN stops b ON y.stop=b.id
 WHERE a.name='Craiglockhart' AND b.name ='Haymarket'
SELECT DISTINCT a.name, b.name
  FROM stops a JOIN route z ON a.id=z.stop
  JOIN route y ON y.num = z.num
  JOIN stops b ON y.stop=b.id
 WHERE a.name='Craiglockhart' AND b.name ='Haymarket'
SELECT DISTINCT a.name, b.name from stops a
  JOIN route z ON a.id=z.stop
  JOIN route y ON y.num = z.num
  JOIN stops b ON y.stop=b.id
 WHERE a.name='Craiglockhart' AND b.name ='Sighthill'
SELECT DISTINCT a.name, b.name
  FROM stops a JOIN route z ON a.id=z.stop
  JOIN route y ON y.num = z.num
  JOIN stops b ON y.stop=b.id
 WHERE y.name='Craiglockhart' AND z.name ='Haymarket'
 ```
- **2. self JOIN Quiz  **
```
SELECT S2.id, S2.name, R2.company, R2.num
  FROM stops S1, stops S2, route R1, route R2
 WHERE S1.name='Haymarket' AND S1.id=R1.stop
   AND S1.company=S2.company AND S1.num=S2.num
   AND R2.stop=S2.id AND R1.num='2A'
SELECT S2.id, S2.name, R2.company, R2.num
  FROM stops S1, stops S2, route R1, route R2
 WHERE S1.name='Haymarket' AND S1.id=R1.num
   AND R1.company=R2.company AND R1.num=R2.num
   AND R2.stop=S2.id AND R2.num='2A'
SELECT S2.id, S2.name, R2.company, R2.num
  FROM stops S1, stops S2, route R1, route R2
 WHERE S1.name='Haymarket' AND S1.id=R1.stop
   AND R1.company=R2.company AND R1.num=R2.num
   AND R2.stop=S2.id
SELECT S2.id, S2.name, R2.company, R2.num
  FROM stops S1, stops S2, route R1, route R2
 WHERE S1.name='Haymarket' AND S1.id=R1.stop
   AND R1.company=R2.company AND R1.num=R2.num
   AND R2.stop=S2.id AND R2.num='2'
SELECT S2.id, S2.name, R2.company, R2.num
  FROM stops S1, stops S2, route R1, route R2
 WHERE S1.name='Haymarket' AND S1.id=R1.stop
   AND R1.company=R2.company AND R1.num=R2.num
   AND R2.stop=S2.id AND R2.num='2A'
   ```
- **3. self JOIN Quiz  **
```
SELECT a.company, a.num, stopa.name, stopb.name
  FROM route a JOIN route b ON (a.company=b.company AND a.num=b.num)
  JOIN stops stopa ON (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
SELECT a.company, a.num, stopa.name, stopb.name
  FROM route a JOIN route b ON (a.company=b.company AND a.num=b.num)
  JOIN stops stopa ON (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
 WHERE stopa.name='Sighthill'
SELECT a.company, a.num, stopa.name, stopb.name
  FROM route a JOIN route b IN (a.company=b.company AND a.num=b.num)
  JOIN stops stopa IN (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
 WHERE stopa.name='Tollcross'
SELECT a.company, a.num, stopa.name, stopb.name
  FROM route a JOIN route b ON (a.company=b.company AND a.num=b.num)
  JOIN stops stopa ON (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
 WHERE stopa.name='Tollcross'
SELECT a.company, a.num, stopa.name, stopb.name
  FROM route a JOIN route b ON (a.company=b.company AND a.num=b.num)
  JOIN stops stopa ON (a.stop=stopa.id)
  JOIN stops stopb ON (b.stop=stopb.id)
 WHERE stopz.name='Tollcross'
```


