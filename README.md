# Pursuit-Core-Web-SQL-Lab

Complete the tutorial at the link [here](https://sqlbolt.com/lesson/select_queries_introduction)

Fork and clone this repo, then for each of the 18 sections, copy and paste your solution in your fork.  Submit by making a PR against this repo.



SECTION 1
1. SELECT title
   From movies

2. SELECT director
   From movies 

3. SELECT director, title
   From movies 

4. SELECT title, year
   From movies 

5. SELECT *
   From movies 


SECTION 2

1. SELECT *
   FROM movies
   WHERE id = 6

2. SELECT *
   FROM movies
   WHERE year BETWEEN 2000 AND 2010

3. SELECT *
   FROM movies
   WHERE year NOT BETWEEN 2000 AND 2010

4. SELECT *, year
   FROM movies
   WHERE id BETWEEN 1 AND 5


SECTION 3 

1. SELECT * 
   FROM movies
   WHERE title LIKE 'Toy Story%'

2. SELECT * 
   FROM movies
   WHERE title LIKE 'Toy Story%'

3. SELECT * 
   FROM movies
   WHERE director LIKE 'john lasseter'

4. SELECT * 
   FROM movies
   WHERE director NOT LIKE 'John Lasseter'

5. SELECT * 
   FROM movies
   WHERE title LIKE 'wall%'


SECTION 4 

1. SELECT DISTINCT director
   FROM movies
   ORDER BY director ASC

2. SELECT *
   FROM movies
   ORDER BY year DESC LIMIT 4
   
3. SELECT *
   FROM movies
   ORDER BY title ASC LIMIT 5

4. SELECT *
   FROM movies
   ORDER BY title ASC LIMIT 5 OFFSET 5


SECTION 5 

1. SELECT city, population  
   FROM north_american_cities
   WHERE country LIKE 'canada'

2. SELECT city 
   FROM north_american_cities
   WHERE country LIKE 'united states'
   ORDER BY latitude DESC

3. SELECT city
   FROM north_american_cities
   WHERE longitude < -87.629798
   ORDER BY longitude ASC 

4. SELECT city
   FROM north_american_cities
   WHERE country  LIKE 'mexico' 
   ORDER BY population DESC LIMIT 2
   
5. SELECT city
   FROM north_american_cities
   WHERE country  LIKE 'united states' 
   ORDER BY population DESC LIMIT 2 OFFSET 2
   

SECTION 6

1. SELECT *
   FROM movies
   INNER JOIN boxoffice
   ON movies.id = boxoffice.movie_id
   ORDER BY id 

2. SELECT *
   FROM movies
   INNER JOIN boxoffice
   ON movies.id = boxoffice.movie_id
   WHERE boxoffice.domestic_sales < boxoffice.international_sales
   ORDER BY id 

3. SELECT *
   FROM movies
   INNER JOIN boxoffice
   ON movies.id = boxoffice.movie_id
   ORDER BY boxoffice.rating DESC


SECTION 7 

1. SELECT DISTINCT building
   FROM employees

2. SELECT *
   FROM buildings

3. SELECT DISTINCT role, building_name
   FROM buildings
   LEFT JOIN  employees 
   ON building = building_name


SECTION 8

1. SELECT name , role ,building
   FROM employees
   WHERE building IS null

2. SELECT DISTINCT building_name ,name
   FROM Buildings 
   LEFT JOIN employees
   ON building_name = building
   WHERE name IS null


SECTION 9

1. SELECT title, (domestic_sales + international_sales) / 1000000 AS combined_sales_in_millions
   FROM movies
   JOIN boxoffice
   ON movies.id = boxoffice.movie_id

2. SELECT title,rating * 10 AS rating_in_percent
   FROM movies
   JOIN boxoffice
   ON movies.id = boxoffice.movie_id;

3. SELECT title, year
   FROM movies
   WHERE ((year/2) + (0.5)) * 2 != year // (also can use year % 2 = 0)


SECTION  10 

1. SELECT name, MAX(years_employed)
   FROM employees;

2. SELECT name ,role ,  AVG(years_employed)
   FROM employees
   GROUP BY role

3. SELECT building, SUM(years_employed) as Total_years_employed
   FROM employees
   GROUP BY building


SECTION 11 

1. SELECT name ,SUM(role LIKE 'artist') AS artist_sum
   FROM employees;

2. SELECT *, COUNT(name) AS number_of_employees_in_each_role
   FROM employees
   GROUP BY role

3. SELECT *, SUM(years_employed)
   FROM employees
   GROUP BY role
   HAVING  role LIKE 'engineer'


SECTION 12

1. SELECT director, COUNT(title) AS sum_of_movies_directed_by_director
   FROM movies
   GROUP BY director

2.    SELECT director, SUM(domestic_sales + international_sales) AS total_sales 
      FROM movies
      INNER JOIN boxoffice
      ON id = movie_id
      GROUP BY director



SECTION 13 

1. INSERT INTO movies
   VALUES(15,'Toy Story 4','John Lasseter',2100,95)

2. INSERT INTO boxoffice
   VALUES(15, 8.7,34000000,270000000)



SECTION 14

1. UPDATE movies
   SET director = 'John Lasseter'
   WHERE id = 2

2. UPDATE movies
   SET year = 1999
   WHERE id = 3

3. UPDATE movies
   SET title = 'Toy Story 3', director = 'Lee Unkrich'
   WHERE id = 11


SECTION 15

1. DELETE FROM movies
   where year < 2005

2. DELETE FROM movies
   where director = 'Andrew Stanton'


SECTION 16 

1. CREATE TABLE IF NOT EXISTS Database (
       name TEXT PRIMARY KEY,
       version INTERGER FLOAT,
       download_count INTERGER 
);


SECTION 17

1. ALTER TABLE movies
   ADD Aspect_ratio FLOAT

2. ALTER TABLE Movies
   ADD COLUMN LANGUAGE TEXT DEFAULT english;


SECTION 18

1. DROP TABLE IF EXISTS movies

2. DROP TABLE IF EXISTS boxoffice
   
   
   








