# SQL Queries for Segmentation Analysis

## Analysis for Year Release of Movies 

````sql
SELECT 
  (CASE WHEN year_of_release BETWEEN 1930 AND 1959 THEN '1930-1959'
  WHEN year_of_release BETWEEN 1960 AND 1989 THEN '1960-1989'
  WHEN year_of_release BETWEEN 1990 AND 2019 THEN '1990-2019'
  END) AS year_bracket,
  COUNT(*) AS total_movies_count,
  ROUND(SUM(gross_total_in_millions), 2) AS total_gross,
  ROUND(AVG(imdb_rating), 1) AS avg_rating,
  ROUND(AVG(run_time_in_mins), 0) AS avg_run_time
FROM 
  movies.imdb_top_100_movies
GROUP BY 
  year_bracket
ORDER BY 
  year_bracket
````

#### Walkthrough: 

* In order to better group the movies based on the year of their release, I created three "brackets" that the movies would fall under based on their release year. This was done in order to simplify the data and to also have a conhesive format for a new attribute of the dataset based on the year release.
* Using the **GROUP BY** to group together based on the ```year_bracket``` in order to determine the ```total_gross```, ```avg_rating```, and ```avg_run_time```. 
* Lastly used the **ORDER BY** clause to sort the results based on the ```year_bracket```.

#### Results: 

| year_bracket           | total_movies_count | total_gross | avg_rating |
| :-----------:          | :-----------:      | :---------: | :---------:|
| 1930-1950              | 76                 | 343.51      | 8.3        |
| 1960-1989              | 74                 | 2648.25     | 8.4        |
| 1990-2019              | 36                 | 8521.3      | 8.3        |


 
 ## Analysis for Category of Movies 
 
 ````sql
 SELECT 
  category,
  ROUND(SUM(gross_total_in_millions), 2) AS total_gross,
  COUNT(*) AS total_count,
  ROUND(AVG(imdb_rating), 2) AS avg_rating
FROM 
  movies.imdb_top_100_movies
GROUP BY 
  category
ORDER BY 
  total_gross DESC 
 ````  
 #### Walkthrough: 

* The movie category is characterized based on the rating the movie received. A few examples are **PG-13, Rated R, Rated PG, etc**. 
* Using the **GROUP BY** to group together based on the ```category``` in order to determine the ```total_gross```, ```avg_rating```, and ```total_count```. 
* Lastly used the **ORDER BY** clause to sort the results based on the ```total_gross``` in descending order.
 
 #### Results: 

| category    | total_gross | total_count | avg_rating  |
| :----------:| :---------: | :---------: | :---------: |
| PG-13       | 4697.41     | 16          | 8.42        |
| R           | 4257.53     | 58          | 8.33        |
| PG          | 1593.59     | 11          | 8.38        |
| G           | 695.18      | 6           | 8.37        | 
| Passed      | 228.94      | 3           | 8.07        | 
| Approved    | 24.19       | 4           | 8.55        | 
| GP          | 16.22       | 1           | 8.1         | 
 

 
 ## Analysis for Genre of Movies 
 
 ````sql
WITH cte AS (SELECT 
  genre,
  ROUND(SUM(gross_total_in_millions), 2) AS total_gross,
  COUNT(*) AS total_count,
  ROUND(AVG(imdb_rating), 2) AS avg_rating
FROM 
  movies.imdb_top_100_movies
GROUP BY 
  genre,
  genre_2,
  genre_3
ORDER BY 
  total_gross DESC 
)


SELECT 
  genre,
  ROUND(SUM(total_gross)) AS total_gross,
  ROUND(AVG(avg_rating), 2) AS avg_rating,
  SUM(total_count) AS total_count
FROM 
  cte 
GROUP BY 
  genre 
ORDER BY
  total_gross DESC 
  ````
 
#### Walkthrough: 

* The movie genre is characterized based on the type of genre the movie is. A few examples are **Action, Drama, Comedy, etc**. 
* Within the **cte**, I used a **GROUP BY** clause to group together based on the multiple genres of the movies in order to determine the ```total_gross``` and ```avg_rating``` of each movie genre. 
* Lastly called upon the **cte** and used the **ORDER BY** clause to sort the results based on the ```total_gross``` in descending order.
 
  
#### Results: 
 
| genre       | total_gross | avg_rating    | 
| :----------:| :---------: | :---------:   | 
| Action      | 5739.0      | 16            | 
| Drama       | 1761.0      | 58            | 
| Crime       | 1138.0      | 11            | 
| Adventure   | 647.0       | 6             | 
| Biography   | 629.0       | 3             | 
| Comedy      | 321.0       | 4             | 
| Mystery     | 123.0       | 1             | 
| Horror      | 93.0        | 1             |   

 
 
 
