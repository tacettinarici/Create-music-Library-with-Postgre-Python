# Create-music-Library-with-Postgre-Python




# Data Modeling With Python - PostgreSQL

This project is part of Udacity Data Engineer Nanodegree program.

## 1.Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and bring you on the project. Our role is to create a database schema and ETL pipeline for this analysis. We'll be able to test your database and ETL pipeline by running queries given to us by the analytics team from Sparkify and compare our results with their expected results.

Project Description
In this project, we'll apply data modeling skills with Postgres and build an ETL pipeline using Python. To complete the project, we will need to define fact and dimension tables for a star schema for a particular analytic focus, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

Data Model
The data model I've implemented is a star model. It is the typical schema for a Data Warehouse. The tables are:

Fact Table
Table songplays

## 2. Dataset

###  2.1 Song Dataset
The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are filepaths to two files in this dataset.

`song_data/A/B/C/TRABCEI128F424C983.json`
`song_data/A/A/B/TRAABJL12903CDCF1A.json`
And below is an example of what a single song file, `TRAABJL12903CDCF1A.json`, looks like.

`{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0}`

### 2.2 Log Dataset
The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate activity logs from a music streaming app based on specified configurations.

The log files in the dataset you'll be working with are partitioned by year and month. For example, here are filepaths to two files in this dataset.

- `log_data/2018/11/2018-11-12-events.json`
- `log_data/2018/11/2018-11-13-events.json`

# 3. Files
In addition to the data files, this repository has six files:

- `test.ipynb` displays the first few rows of each table to let you check your database.
- `create_tables.py` drops and creates your tables. You run this file to reset your tables before each time you run your ETL scripts.
- `etl.ipynb` reads and processes a single file from song_data and log_data and loads the data into your tables. This notebook contains detailed instructions on the        ETL process for each of the tables.
- `etl.py` reads and processes files from song_data and log_data and loads them into your tables. You can fill this out based on your work in the ETL notebook.
- `sql_queries.py` contains all your sql queries, and is imported into the last three files above.
