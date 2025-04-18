###🎧 Spotify Advanced SQL Project and Query Optimization
📌 Project Category: Advanced SQL Practice
Dataset: Click here to access the dataset

📄 Overview
This project involves analyzing a Spotify dataset containing various attributes of tracks, albums, and artists using PostgreSQL. It walks through an end-to-end process of:

✅ Normalizing a denormalized dataset

✅ Writing SQL queries ranging from easy to advanced

✅ Optimizing query performance using techniques like indexing and query planning

The core aim is to strengthen advanced SQL skills and uncover meaningful insights from music data.

🗃️ Dataset Description
The dataset includes fields such as:

🎤 artist: Performer of the track

🎵 track: Name of the song

💿 album: Album to which the track belongs

🧾 album_type: Album category (e.g., single, album)

📈 Streaming metrics like views, likes, comments, streams

🎶 Audio features like danceability, energy, tempo, valence

📊 Additional metadata for analysis

🛠️ Table Creation (DDL)
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

🚀 Query Optimization
In advanced stages, the focus shifts to improving query performance. Some optimization strategies include:
- **Indexing**: Adding indexes on frequently queried columns.
- **Query Execution Plan**: Using `EXPLAIN ANALYZE` to review and refine query performance.
  
---

## 15 Practice Questions

🟢 Easy Level
1. Retrieve the names of all tracks that have more than 1 billion streams.
2. List all albums along with their respective artists.
```sql
select
distinct album, artist
from spotify
order by 1;
```
3. Get the total number of comments for tracks where `licensed = TRUE`.
4. Find all tracks that belong to the album type `single`.
5. Count the total number of tracks by each artist.
```sql
select 
	artist, count(*) as total_songs
from spotify
group by artist
order by 1 desc;
```

🟡 Medium Level
1. Calculate the average danceability of tracks in each album.
2. Find the top 5 tracks with the highest energy values.
3. List all tracks along with their views and likes where `official_video = TRUE`.
```sql
select 
	track, 
	sum(views) as total_views,
	sum(likes) as total_likes
from spotify
where official_video = 'true'
group by 1;
```
4. For each album, calculate the total views of all associated tracks.

🔴 Advanced Level
1. Find the top 3 most-viewed tracks for each artist using window functions.
2. Write a query to find tracks where the liveness score is above the average.
```sql
select 
	track, 
	artist,
	liveness
from spotify
where liveness > (select avg(liveness) from spotify);
--select avg(liveness) from spotify -- 0.19
```
🧰 Tech Stack & Tools
🛢️ PostgreSQL for database and query execution
🖥️ pgAdmin 4 or any SQL IDE for querying
💻 EXPLAIN ANALYZE for performance analysis
📦 SQL Concepts: DDL, DML, Joins, Subqueries, Window Functions, Indexes

🎯 Next Steps
📊 Visualization: Build dashboards with BI tools
🧩 Scalability: Expand dataset for stress testing
🧠 Deep Dive: Explore indexing, query rewriting, partitioning
---

🤝 Contributing
Feel free to fork, raise issues, or open pull requests to collaborate. Let's learn and grow together! 🌱
---

