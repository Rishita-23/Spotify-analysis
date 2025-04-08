# Spotify Advanced SQL Project and Query Optimization P-6
Project Category: Advanced
[Click Here to get Dataset](https://www.kaggle.com/datasets/sanjanchaudhari/spotify-dataset)

![Spotify Logo] (data:image/png;base64,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)

## Overview
This project involves analyzing a Spotify dataset with various attributes about tracks, albums, and artists using **SQL**. It covers an end-to-end process of normalizing a denormalized dataset, performing SQL queries of varying complexity (easy, medium, and advanced), and optimizing query performance. The primary goals of the project are to practice advanced SQL skills and generate valuable insights from the dataset.

```sql
-- create table
DROP TABLE IF EXISTS spotify;
CREATE TABLE spotify (
    artist VARCHAR(255),
    track VARCHAR(255),
    album VARCHAR(255),
    album_type VARCHAR(50),
    danceability FLOAT,
    energy FLOAT,
    loudness FLOAT,
    speechiness FLOAT,
    acousticness FLOAT,
    instrumentalness FLOAT,
    liveness FLOAT,
    valence FLOAT,
    tempo FLOAT,
    duration_min FLOAT,
    title VARCHAR(255),
    channel VARCHAR(255),
    views FLOAT,
    likes BIGINT,
    comments BIGINT,
    licensed BOOLEAN,
    official_video BOOLEAN,
    stream BIGINT,
    energy_liveness FLOAT,
    most_played_on VARCHAR(50)
);
```
## Project Steps

### 1. Data Exploration
Before diving into SQL, it’s important to understand the dataset thoroughly. The dataset contains attributes such as:
- `Artist`: The performer of the track.
- `Track`: The name of the song.
- `Album`: The album to which the track belongs.
- `Album_type`: The type of album (e.g., single or album).
- Various metrics such as `danceability`, `energy`, `loudness`, `tempo`, and more.

### 4. Querying the Data
After the data is inserted, various SQL queries can be written to explore and analyze the data. Queries are categorized into **easy**, **medium**, and **advanced** levels to help progressively develop SQL proficiency.

#### Easy Queries
- Simple data retrieval, filtering, and basic aggregations.
  
#### Medium Queries
- More complex queries involving grouping, aggregation functions, and joins.
  
#### Advanced Queries
- Nested subqueries, window functions, CTEs, and performance optimization.

### 5. Query Optimization
In advanced stages, the focus shifts to improving query performance. Some optimization strategies include:
- **Indexing**: Adding indexes on frequently queried columns.
- **Query Execution Plan**: Using `EXPLAIN ANALYZE` to review and refine query performance.
  
---

## 15 Practice Questions

### Easy Level
1. Retrieve the names of all tracks that have more than 1 billion streams.
2. List all albums along with their respective artists.
3. Get the total number of comments for tracks where `licensed = TRUE`.
4. Find all tracks that belong to the album type `single`.
5. Count the total number of tracks by each artist.

### Medium Level
1. Calculate the average danceability of tracks in each album.
2. Find the top 5 tracks with the highest energy values.
3. List all tracks along with their views and likes where `official_video = TRUE`.
4. For each album, calculate the total views of all associated tracks.
5. Retrieve the track names that have been streamed on Spotify more than YouTube.

### Advanced Level
1. Find the top 3 most-viewed tracks for each artist using window functions.
2. Write a query to find tracks where the liveness score is above the average.
3. **Use a `WITH` clause to calculate the difference between the highest and lowest energy values for tracks in each album.**
```sql
WITH cte
AS
(SELECT 
	album,
	MAX(energy) as highest_energy,
	MIN(energy) as lowest_energery
FROM spotify
GROUP BY 1
)
SELECT 
	album,
	highest_energy - lowest_energery as energy_diff
FROM cte
ORDER BY 2 DESC
```
   
5. Find tracks where the energy-to-liveness ratio is greater than 1.2.
6. Calculate the cumulative sum of likes for tracks ordered by the number of views, using window functions.


Here’s an updated section for your **Spotify Advanced SQL Project and Query Optimization** README, focusing on the query optimization task you performed. You can include the specific screenshots and graphs as described.

---

## Query Optimization Technique 

To improve query performance, we carried out the following optimization process:

- **Initial Query Performance Analysis Using `EXPLAIN`**
    - We began by analyzing the performance of a query using the `EXPLAIN` function.
    - The query retrieved tracks based on the `artist` column, and the performance metrics were as follows:
        - Execution time (E.T.): **7 ms**
        - Planning time (P.T.): **0.17 ms**
    - Below is the **screenshot** of the `EXPLAIN` result before optimization:
      ![EXPLAIN Before Index](https://github.com/najirh/najirh-Spotify-Data-Analysis-using-SQL/blob/main/spotify_explain_before_index.png)

- **Index Creation on the `artist` Column**
    - To optimize the query performance, we created an index on the `artist` column. This ensures faster retrieval of rows where the artist is queried.
    - **SQL command** for creating the index:
      ```sql
      CREATE INDEX idx_artist ON spotify_tracks(artist);
      ```

- **Performance Analysis After Index Creation**
    - After creating the index, we ran the same query again and observed significant improvements in performance:
        - Execution time (E.T.): **0.153 ms**
        - Planning time (P.T.): **0.152 ms**
    - Below is the **screenshot** of the `EXPLAIN` result after index creation:
      ![EXPLAIN After Index](https://github.com/najirh/najirh-Spotify-Data-Analysis-using-SQL/blob/main/spotify_explain_after_index.png)

- **Graphical Performance Comparison**
    - A graph illustrating the comparison between the initial query execution time and the optimized query execution time after index creation.
    - **Graph view** shows the significant drop in both execution and planning times:
      ![Performance Graph](https://github.com/najirh/najirh-Spotify-Data-Analysis-using-SQL/blob/main/spotify_graphical%20view%203.png)
      ![Performance Graph](https://github.com/najirh/najirh-Spotify-Data-Analysis-using-SQL/blob/main/spotify_graphical%20view%202.png)
      ![Performance Graph](https://github.com/najirh/najirh-Spotify-Data-Analysis-using-SQL/blob/main/spotify_graphical%20view%201.png)

This optimization shows how indexing can drastically reduce query time, improving the overall performance of our database operations in the Spotify project.
---

## Technology Stack
- **Database**: PostgreSQL
- **SQL Queries**: DDL, DML, Aggregations, Joins, Subqueries, Window Functions
- **Tools**: pgAdmin 4 (or any SQL editor), PostgreSQL (via Homebrew, Docker, or direct installation)

## How to Run the Project
1. Install PostgreSQL and pgAdmin (if not already installed).
2. Set up the database schema and tables using the provided normalization structure.
3. Insert the sample data into the respective tables.
4. Execute SQL queries to solve the listed problems.
5. Explore query optimization techniques for large datasets.

---

## Next Steps
- **Visualize the Data**: Use a data visualization tool like **Tableau** or **Power BI** to create dashboards based on the query results.
- **Expand Dataset**: Add more rows to the dataset for broader analysis and scalability testing.
- **Advanced Querying**: Dive deeper into query optimization and explore the performance of SQL queries on larger datasets.

---

## Contributing
If you would like to contribute to this project, feel free to fork the repository, submit pull requests, or raise issues.

---

## License
This project is licensed under the MIT License.
