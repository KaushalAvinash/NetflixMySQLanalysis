# Netflix_MySQL_Analysis

## Project Overview
This data analysis project is on Netflix Movies and TV Shows using MySQL. The goal is to extract valuable insights and answer various buisness questions based 
on dataset. The following README provides a detailed account of the project"s objectives, buisness problems, solutions, findings and conclusions.

## Objectives
- Analyze the distribution of content types (movies vs TV shows).
- Identify the most common ratings for movies and TV shows.
- List and analyse content based on release years, countries and durations.
- Explore and categorize content based on specific criteria and keywords.

## Dataset
The data for this project is sorced from the Kaggle dataset: [Download Here](https://www.kaggle.com/datasets/rahulvyasm/netflix-movies-and-tv-shows)

## Data Analysis
Include some Interesting code/features worked with

```MySQL
SELECT year, total_content,
ROUND(total_content/(SELECT count(*) FROM netflix WHERE country = 'India')*100),2) AS yearly_avg
FROM
(SELECT YEAR(str_to_date(date_added, '%M %d, %Y')) AS year,
count(*) AS total_content
FROM netflix
WHERE country = 'India'
GROUP BY year) AS yearly_count
ORDER BY yearly_avg DESC LIMIT 5;
```
## Findings and Conclusion

- Content Distribution: The dataset contains a diverse range of movies and TV shows with various ratings and genres.
- Common Ratings: Insights into the most common ratings provide an understanding of the content's target audience.
- Geographical Insights: THe top countries and the average content releases by India highlight regional content distribution.
- Content Categorization: Categorizing content based on specific keywords helps in understandings in nature of content available on Netflix.

This analysis provides a comprehensive view of Netflix's content and can help inform content strategy and decision-making.

