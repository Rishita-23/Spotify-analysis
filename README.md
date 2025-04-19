# 🎧 Spotify Advanced SQL Project and Query Optimization

📌 **Project Category:** Advanced SQL Practice  
🗂️ **Dataset:** [Click here to access the dataset](https://www.kaggle.com/datasets/sanjanchaudhari/spotify-dataset) 

---

## 📄 Overview

This project analyzes a Spotify dataset containing various attributes of tracks, albums, and artists using **PostgreSQL**. It guides you through:

✅ Normalizing a denormalized dataset  
✅ Writing SQL queries ranging from easy to advanced  
✅ Optimizing query performance using techniques like indexing and query planning

🎯 The main goal is to practice advanced SQL skills and extract insightful analytics from Spotify music data.

---

## 🗃️ Dataset Description

The dataset includes the following attributes:

- 🎤 `artist`: Performer of the track  
- 🎵 `track`: Name of the song  
- 💿 `album`: Album to which the track belongs  
- 🧾 `album_type`: Album category (e.g., single, album)  
- 🎚️ Audio metrics: `danceability`, `energy`, `loudness`, `tempo`, `valence`, etc.  
- 📈 Streaming stats: `views`, `likes`, `comments`, `streams`  
- 🔖 Metadata: `official_video`, `licensed`, `channel`, etc.

---

## 🛠️ Table Creation (DDL)

```sql
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

🔎 Practice Questions
🟢 Easy Level
1. Retrieve the names of all tracks that have more than 1 billion streams.
``` sql
select * from spotify;

select * from spotify 
where stream>1000000000;
```
2. List all albums along with their respective artists

```sql
SELECT DISTINCT album, artist
FROM spotify
ORDER BY 1;
```
3. Get the total number of comments for tracks where licensed = TRUE.
```sql
select 
	sum(comments) as total_comments
from spotify
where licensed = 'true';
```
4. Find all tracks that belong to the album type single.
```sql
select artist, track from spotify
where album_type = 'single';
```
5. Count the total number of tracks by each artist.

```sql
SELECT 
    artist, 
    COUNT(*) AS total_songs
FROM spotify
GROUP BY artist
ORDER BY 1 DESC;
```

🟡 Medium Level

6. Calculate the average danceability of tracks in each album.
```sql
select 
	album, avg(danceability) as avg_danceability
from spotify
group by 1
order by 2 desc;
```
7. Find the top 5 tracks with the highest energy values.
```sql
select 
	track,
	max(energy)
from spotify 
group by 1
order by 2 desc
limit 5;
```
8. List all tracks along with their views and likes where official_video = TRUE.
```sql
select 
	track, 
	sum(views) as total_views,
	sum(likes) as total_likes
from spotify
where official_video = 'true'
group by 1;	
```
9. For each album, calculate the total views of all associated tracks.
```sql
select 
	album,
	track,
	sum(views) as total_views
from spotify
group by 1,2;
```

🔴 Advanced Level
   
10. Find the top 3 most-viewed tracks for each artist using window function
```sql
-- each artist and total views for each track
--track with highest view for each artist (we need top 3)
--dense rank

with ranking_artist
as
(select 
	artist,
	track,
	sum(views) as total_view,
	dense_rank() over(partition by artist order by sum(views)desc) as rank
from spotify
group by 1,2
order by 1, 3 desc)
select * from ranking_artist
where rank<=3;
```
11. Write a query to find tracks where the liveness score is above the average.
```sql
select 
	track, 
	artist,
	liveness
from spotify
where liveness > (select avg(liveness) from spotify);
--select avg(liveness) from spotify -- 0.19
```

##🚀 Query Optimization
✅ Step-by-step Process
EXPLAIN ANALYZE Before Indexing

Query on artist column
Execution Time: 7 ms, Planning Time: 0.17 ms

Index Creation

```sql
Copy code
CREATE INDEX idx_artist ON spotify(artist);
```
EXPLAIN ANALYZE After Indexing

Execution Time: 0.153 ms, Planning Time: 0.152 ms

📊 Graphical Performance Comparison
A graph visualizing execution and planning time before and after indexing shows a drastic improvement in performance.

---

## 🧰 Tech Stack & Tools
🛢️ Database: PostgreSQL

💻 Tools: pgAdmin 4 / DBeaver / Any SQL IDE

🧠 Concepts Covered:

• DDL, DML

• Aggregations & Joins

• Subqueries & Window Functions

• Query Optimization & Indexing

EXPLAIN ANALYZE

---

## 🎯 Next Steps
📊 Visualization: Create dashboards in Power BI / Tableau

🧩 Scalability: Expand dataset and perform stress testing

🧠 Advanced Optimization: Explore query rewriting, indexing, and partitioning

---

## 🤝 Contributing
If you'd like to contribute:Feel free to fork, raise issues, or open pull requests to collaborate. Let's learn and grow together! 🌱
Let's learn and grow together! 🌱
