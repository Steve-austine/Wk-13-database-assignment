Importing tha data was easy and it is quite interesting that you can be able to create tables automatically.

2. **Data Fun (20 pts):**

**Use simple SQL queries to play with the data.**

1. **most common rating**

SELECT rating, COUNT(*) AS count
FROM netflix_titles
GROUP BY rating
ORDER BY count DESC
LIMIT 1;

Result: Most common rating is 'TV-MA'

2. **Top country producing content**

SELECT country, COUNT(*) AS count
FROM netflix_titles
GROUP BY country
ORDER BY count DESC
LIMIT 1;

Result: The top country producing content is USA

**Use basic SQL queries like (COUNT, AVG, and SUM) to understand more about the data you have.**
1. **count of Tv shows and Movies**

SELECT type, COUNT(*) AS count
FROM netflix_titles
GROUP BY type;

Result: moivies 55, TV shows 45

**Average release year**

SELECT AVG(release_year) AS avg_release_year
FROM netflix_titles;

Result: 2015

**Total duration of all movieas in minutes**
SELECT SUM(CAST(SUBSTRING(duration, 1, LENGTH(duration) - 4) AS CHAR)) AS total_duration
FROM netflix_titles
WHERE type = 'Movie';

Result: 5540

**3. Ask Away (30 pts):**

**Formulate 2 questions about the data (e.g., what are popular shows in different countries?).**
**Question 1: What are the most popular genres?**
SELECT listed_in, COUNT(*) AS count
FROM netflix_titles
GROUP BY listed_in
ORDER BY count DESC
LIMIT 5;

Result:
Action & Adventure, Anime Features, International Movies - 12
Children & Family Movies - 6
Kids' TV - 5
Reality TV - 4
Children & Family Movies, Comedies - 3

**Question 2: What are the popular shows in the united states?**
SELECT title
FROM netflix_titles
WHERE type = 'TV Show' AND country = 'United States'
ORDER BY release_year DESC
LIMIT 10;

Result:
Dear White People
He-Man and the Masters of the Universe
Nailed It
Lucifer
Kid Cosmic
Saved by the Bell

