# SQL-Instagram-Database-Clone

**Overview**
This project is a MySQL-based Instagram database clone, developed as part of The Ultimate MySQL Bootcamp: Go from SQL Beginner to Expert by Colt Steele and Ian Schoonover on Udemy. It replicates Instagram’s core functionalities through a robust schema design for users, photos, comments, likes, follows, tags, and photo tags, with optimized queries for data analysis and foreign key constraints for data integrity. The project includes sample data and queries to analyze user behavior, posting patterns, and hashtag popularity.
Features

**Complete Schema:** Tables for users, photos, comments, likes, follows, tags, and photo_tags with primary keys, foreign keys, and composite keys.
Sample Data: Pre-populated with 100 users, 257 photos, follows, tags, and photo tags for testing.
Analytical Queries: Includes queries to find the oldest users, most popular registration days, inactive users, most-liked photos, average posts per user, top hashtags, and users who liked every photo.
Data Integrity: Enforces unique constraints (e.g., usernames, tag names) and referential integrity via foreign keys.
Real-World Simulation: Models social media interactions like posting, liking, commenting, following, and tagging.

**Installation
Prerequisites:**
MySQL 8.x and MySQL Workbench (or another MySQL client).
Basic SQL knowledge.

**Set Up Database:**
Open MySQL Workbench and connect to your MySQL server.
Run sql.sql to create the instagram_clone database, tables, and insert sample data.

**Usage
Access the Database:**
Connect to the instagram_clone database using MySQL Workbench or the MySQL command-line client.


**Run Example Queries:**
Execute queries from sql.sql to analyze the data. Examples include:
Oldest Users:SELECT * FROM users ORDER BY created_at LIMIT 5;


**Most Popular Registration Day:** SELECT DAYNAME(created_at) AS day, COUNT(*) AS total
FROM users GROUP BY day ORDER BY total DESC LIMIT 2;


**Most-Liked Photo:** SELECT username, photos.id, photos.image_url, COUNT(*) AS total
FROM photos
INNER JOIN likes ON likes.photo_id = photos.id
INNER JOIN users ON photos.user_id = users.id
GROUP BY photos.id ORDER BY total DESC LIMIT 1;


**Top 5 Hashtags:** SELECT tags.tag_name, COUNT(*) AS total
FROM photo_tags JOIN tags ON photo_tags.tag_id = tags.id
GROUP BY tags.id ORDER BY total DESC LIMIT 5;


**Schema Details**

users: Stores user information (id, username, created_at).
photos: Stores photo details (id, image_url, user_id, created_at).
comments: Stores comments on photos (id, comment_text, photo_id, user_id, created_at).
likes: Tracks photo likes (user_id, photo_id, created_at).
follows: Manages follower relationships (follower_id, followee_id, created_at).
tags: Stores unique tags (id, tag_name, created_at).
photo_tags: Links photos to tags (photo_id, tag_id).

**Requirements**

Database: MySQL 8.x.
Tools: MySQL Workbench or equivalent MySQL client.
OS: Windows, macOS, or Linux.




