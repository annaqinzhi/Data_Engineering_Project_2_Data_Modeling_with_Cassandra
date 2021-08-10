# Project: Project: Data Modeling with Cassandra

###### by Anna Qin 2021-08-10

## Project Description

In this project, I will apply what I've learned on *`data modeling`* with *`Apache Cassandra`* and complete an ETL pipeline using Python. 
To complete the project, I will need to model my data by creating tables in Apache Cassandra to run queries. 
the ETL pipeline transfers data from a set of CSV files within a directory(local) to create a streamlined CSV file to model and insert data into Apache Cassandra tables.

## Datasets

*`event_data`*. The directory of CSV files partitioned by date. Here are examples of filepaths to two files in the dataset: 

*event_data/2018-11-08-events.csv *   
*event_data/2018-11-09-events.csv *   

efter processing the files, will get a new data file csv which will be used for Apache Cassandra tables, as below:
![even_datafile_new](images/image_event_datafile_new.jpg)

### Based the 3 queries to create 3 Tables

1. **session_library** - Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4
                       - artist_name, song_title, song_length, sessionId, itemInSession PRIMARY KEY (sessionId, itemInSession)
2. **artist_library** - Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182
                      - userId, sessionId, artist_id, artist_name, song_title, itemInSession, user_firstname, user_lastname PRIMARY KEY ((userId, sessionId), itemInSession))
3. **user_library** - Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'
                    - userId, song_title, user_firstname, user_lastname PRIMARY KEY (song_title, userId)

## Project Files

1. ``Project_1B_Data_Modeling_Cassandra.ipynb`` 
2. ``README.md`` provides explaination on this project.

## ETL Pipepline

Extract, transform, load (ETL) is the general procedure of copying data from one or more sources into a destination system which represents the data differently from, or in a different context than, the sources.
in this case, ETL cvs files into tables in Cassandra

### Steps to run this pipeline

1. run ``Project_1B_Data_Modeling_Cassandra.ipynb`` in the jupyter notebook, to check if the the tables have been successfully created
2. if any update or change, ``Project_1B_Data_Modeling_Cassandra.ipynb`` should be restart.
