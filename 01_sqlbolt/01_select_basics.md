# SQLBolt lessons 1 - 5 : SELECT basics
# Database: sample Dataset 'Movies' from SQLBolt.com

## 1. SELECT
```sql
SELECT Title, director
FROM movies; 
```

## 2. WHERE; BETWEEN; IN;
```sql
SELECT title, director
FROM movies
WHERE director = 'John Lasseter';

SELECT title, year
FROM movies
WHERE year  BETWEEN 1998 AND 2008; --   or WHERE year NOT BETWEEN 2002 AND 2005 -- i find this really good for exceptions 

SELECT title
FROM movies
WHERE year NOT IN (2002, 2003, 2005); -- to avoid spam "OR"
``` 
## 3. LIKE; %%; !=; _ 
```sql
SELECT title
FROM movies
WHERE director LIKE 'Lee Unkric_';  -- for LIKE need to use correct writing, with _ looks only for one additional character

SELECT city
FROM north_american_cities
WHERE country LIKE '%anad%'; -- looking for every match in sequence with this string( zero or more characters )

SELECT city  
FROM north_american_cities
WHERE country != 'Mexico'; -- filter for everything except "Mexico" 
```

## 4. DISTINCT 
```sql
SELECT DISTINCT director
FROM movies
WHERE year BETWEEN 2002 AND 2010; -- DISTINCT to avoid duplicate rows
```

## 5. ORDER BY, LIMIT, OFFSET 
```sql
SELECT title
FROM movies
WHERE director = 'John Lasseter'
ORDER BY year ASC -- or DESC 
LIMIT 2 OFFSET 2; -- OFFSET specify where to start counting
```

## 6. HOW TO ORDER
```sql
 SELECT column, another_one_column
 FROM table
 WHERE -- filter like "BETWEEN, column >, IN, LIKE"
 ORDER BY column ASC -- or DESC 
 LIMIT x OFFSET x;
```