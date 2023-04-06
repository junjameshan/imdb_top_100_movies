# IMDB Top 100 Movies of All Time 

![image](https://user-images.githubusercontent.com/123096758/230480135-84d1be13-febd-40a1-958e-be017aa255d3.png)

## Background 

The IMDb Dataset is a table that includes the 100 greatest movies of all time according to the rankings provided by IMDb up until the year of 2015. The table includes information regarding the IMDb rating, gross earnings (Million $), runtime (minutes), year of release and the total number of votes. 

## Challenges

With the dataset, we want to understand the business insights and metrics that can analyzed. A few challenges that come to mind are: 

* How can we simplify the segmentation of the years that the movies were released? 
* What are the important metrics to analyze for each segmentation breakdown? (i.e. genre, category, year, etc.) 
* Is there a correlation between the total gross of a movie compared to that of the other attributes within the dataset? 

## Segmentation Analysis 

The first segmentation analysis performed to analyze the key metrics for was the year bracket. 

### Total Gross per Year Bracket 

![image](https://user-images.githubusercontent.com/123096758/230493044-cb76a9a3-79e3-4adb-a7f0-05d29f8a92f9.png)

The pie chart visualizes the total percentage breakdown for the total gross that movies generated based on the year brackets that the movies fall under based on their release date. 

* The highest year bracket from **1990-2019** generated **8,521.3 (Million $)** with **61 movies** being released during this time period. 
* The second highest year bracket from **1960-1989** generated **2,648.3 (Million $)** with **24 movies** being released during this time period. 
* The lowest year bracket from **1930-1959** generated **343.51 (Million $)** with **14 movies** being released during this time period. 

### Total Gross per Movie Genre 

![image](https://user-images.githubusercontent.com/123096758/230494464-11ae42ef-6437-4faf-b832-1ee1015a5fb5.png)

The column chart visualizes the total gross earnings based on the 9 genres of the movies. 

* **Action, Drama and Crime** generated the most revenue with a count of **25, 22 and 16** respectively for each genre. 
* In terms of the IMDB Ratings, **Action, Drama and Horror** had the highest average ratings of **8.36, 8.35 and 8.35** respectively.

### Total Gross per Movie Category 

![image](https://user-images.githubusercontent.com/123096758/230494839-af7f170b-e2ed-410f-a5b5-1bc063da6818.png)

The column chart visualizes the total gross earnings based on the 7 movie catergory ratings. 

* The top 3 movie categories based on total gross earnings are **PG-13, R, and PG.** 
* In terms of the IMDB Ratings, movies in the **Approved** category had the highest average rating of **8.55** followed by **PG-13** with **8.42** and **PG** with **8.38.**

## Regression Analysis 

In order to better understand if there is a relationship between the total gross of a movie and the other variables within the dataset, I attempted to produce a regression analysis to test my hypothesis on determining if there is a correlation. 

### Heatmap Correlation Graph for IMDB Movie Variables 

![image](https://user-images.githubusercontent.com/123096758/230495514-3938716b-536d-44fe-b9e9-3fa704c930c3.png)

The heatmap graph on the left hand side visualizes the significance of a correlation between each of the variables within the IMDb Movies dataset. The variable that had the strongest positive correlation with the total gross of a movie was determined to be year of release based on the shading in the heatmap graph. 

### Linear Model Plot: Year of Release vs. Total Gross 

![image](https://user-images.githubusercontent.com/123096758/230496107-970ed518-eabc-42be-ad31-4b423c5382aa.png)

A visual representation representing the relationship between the total gross of a movie vs. the year of release for a movie was created as a linear model plot. The plot shows a significant positive correlation between the two variables as the total gross of a movie increasing as the year of release for a movie became more recent. 

### Prediction Linear Regression vs. Actual Test Data 

![image](https://user-images.githubusercontent.com/123096758/230496226-a66d1746-ef04-4f98-8fa7-fd1d8e1f0196.png)

By training the linear regression model based on the variable that we are hypothesizing will correlate to the total gross of a movie, I have created a model selection in order to split the data into training and testing sets.

From the results of the model selection, I have developed a plot visualization for the testing data of the year release of the movie and the testing data of the gross total of the movie. The results of the plot represent a positive correlation between the two variables.

## Conclusion 

Based on the results of the analysis, I have concluded a few key findings: 

1. Movies that had released in the more recent years have tended to perform higher in terms of total gross revenue generated. This can due to the fact that inflation is not adjusted within the data set for older movies and the significant surge in the number of movies being released in modern times. 

2. Action movies will always be the most popular genre amongst fans. 

3. PG-13 rated movies are more family friend and can cater to a larger demographic while Rated R movies will be a close second in its popularity amongst fans. 











