# Data Lake with Spark: Song Play Analysis
> Anita Quevedo Solidoro

This ETL Pipeline was designed for a startup **Sparkify**, who wants to analyze their information collected about the songs and the activity of their users in their new music streaming application. This project extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables using parquet files.

### Files in Project
The files for running the project are:

* `dl.cfg`: which stores AWS credentials.
* `etl.py`: Reads data from s3, processes that data using Spark, and writes them back to S3. .

### Overview
This archive contain two parts:
- ###### s3://udacity-dend/song_data: 
  
  static data about artists and songs Song-data example: {"num_songs": 2, "artist_id": "ARJIE2Y1187B994AC8", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "XXXXXX", "duration": 152.92036, "year": 0}

- ###### s3://udacity-dend/log_data:
    Event data of service usage e.g. who listened what song, when, where, and with which client 

Also:
- Reading 1 JSON file from song_data: 15.2sec
- Processing and writing songs_table: 24.8sec
- Processing and writing artists_table: 20.6sec
- Reading 1 JSON file from log_data: 1.3sec
- Processing and writing users_table: 1min 3.9sec
- Processing and writing time_table: 2min 58.2sec
- Processing and writing songplays_table: 2min 49.6sec


## Steps to follow for Pipiline:
Run  : 
 - 1° : Configure dl.cfg file with AWS credentials.
 - 2°:  run pyhton etl.py
 - 
 

## Example queries:
- ##### Get count of rows in each Dimension table:


    SELECT COUNT(*) FROM songs_table;
    
    SELECT COUNT(*) FROM artists_table;
    
    SELECT COUNT(*) FROM users_table;
    
    SELECT COUNT(*) FROM time_table;
    
- #### Get count of rows in Fact table:

    SELECT COUNT(*) FROM songplays_table;