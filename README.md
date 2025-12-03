# Amazon-prime-Movies-Series-data-analysis

## Overview

This project is a complete database representation of Amazon Prime Video content, including movies, series, actors, users, ratings, and watch history. It is designed to simulate a real-world streaming platform database for learning, analysis, and reporting purposes.

The project contains SQL structures for:

* Content (Movies & Series)
* Actors
* Content-Actor mappings
* Users
* Ratings
* Watch History

It also includes sample data with realistic values to facilitate testing and analysis.

## Tables & Structure

### 1. `Content`

Stores information about movies and series.

* `content_id` (INT, PK)
* `title` (VARCHAR)
* `type` (ENUM: Movie, Series)
* `genre` (VARCHAR)
* `release_year` (YEAR)
* `duration_minutes` (INT, nullable for series)
* `imdb_rating` (DECIMAL)
* `language` (VARCHAR)
* `budget` (BIGINT)
* `box_office` (BIGINT)
* `streaming_regions` (VARCHAR)
* `created_at` (DATETIME)

### 2. `Actors`

Stores actor details.

* `actor_id` (INT, PK)
* `actor_name` (VARCHAR)
* `dob` (DATE)
* `nationality` (VARCHAR)

### 3. `Content_Actors`

Mapping table connecting content and actors.

* `content_id` (INT, FK)
* `actor_id` (INT, FK)
* `role` (VARCHAR)

### 4. `Users`

Stores platform users.

* `user_id` (INT, PK)
* `name` (VARCHAR)
* `email` (VARCHAR)
* `phone` (VARCHAR)
* `address` (VARCHAR)
* `created_at` (DATETIME)

### 5. `Ratings`

Stores ratings and reviews given by users.

* `rating_id` (INT, PK)
* `user_id` (INT, FK)
* `content_id` (INT, FK)
* `rating` (DECIMAL)
* `review` (TEXT)
* `created_at` (DATETIME)

### 6. `WatchHistory`

Tracks user watch activity.

* `history_id` (INT, PK)
* `user_id` (INT, FK)
* `content_id` (INT, FK)
* `watched_on` (DATETIME)
* `progress_minutes` (INT)

