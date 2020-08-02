# PROYECTO 1 DATA ENGINEERING 
## Data Modeling with Postgres

**The project is about a startup called Sparkify, which is an online music provider. Sparkify wants to collect and analyze data about your user activities. For example, you are interested in a detailed understanding of the songs that users are currently listening to. User activity data is stored as JSON files on a file system. Analysts are currently unable to easily query and analyze data.**

- In this project, I applied everything I learned during the classes regarding data modeling with postgres and building ETL pipes with python.

- Tables  were created through the execution of constructed scripts, data with python code were inserted in the jupyter notebook and the final construction of these was verified through the same method.

- With the files that are in the data folder (log_data and song_data) I was able to fill the tables: songs, artists, users, time and songsplay.

**The main part of the project is to design a data model that best suits analytical needs. Additionally, an ETL pipeline must be developed, which loads and transforms the raw JSON data into the database. The underlying database technology is Postgres**

## These tables contained the following:

1. songs: song_id, title, artist_id, year, duration
   It contains the list of songs, where the name appears, the id of the artist who sings the song, in which year it was created and its duration.
   
    ![Table Songs](https://github.com/Javiera93/udacity/blob/master/songs.png)

2. artists: artist_id, name, location, latitude, longitude
   Contains all the artist data, such as name, location, among others.
   
    ![Table Artists](https://github.com/Javiera93/udacity/blob/master/artists.png)

3. users: user_id, first_name, last_name, gender, level
   Contains user records of songs.
   
    ![Table Users](https://github.com/Javiera93/udacity/blob/master/users.png)

4. time: start_time, hour, day, week, month, year, weekday
   Contains timestamps of songs.

    ![Table Time](https://github.com/Javiera93/udacity/blob/master/time.png)
   
5. songsplay: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
   Table that is made up of what is important, such as the song id, the artist id, the time, the user agent, among others. The important thing about this table is that the          songplay_id is built by default taking a serial format.
   
    ![Table SongsPlay](https://github.com/Javiera93/udacity/blob/master/songplays.png)

## Files in the repository

**_THE_ _SCRIPTS_ _WERE_ _RUN_ _THROUGH_ _THE_ _CONSOLE_, _WITH_ _THE_ _COMMAND_: !python name_file.py**

1. **sql_queries.py:** 
This Python file contains all the CREATE TABLE statements to create the fact and dimension tables, as well as the INSER statements that are used during the loading process. These statements are imported and used in the files below.

2. **create_tables.py:** This will create the postgres database and all relevant tables 
Create and connect to the postgres database (which is called sparkifydb), drop the existing tables and create all the fact and dimension tables that. The declarations defined in sql_queries.py are used for this task. The etl.py script (see below) polulates these tables with data.

3. **!python etl.py:** This will start the etl process and fill all the tables with data
This file implements the ETL process, that is, extracting the data from the raw JSON files, transforming it into the startup schema, and loading it into the tables created with the create_tables.py script.

