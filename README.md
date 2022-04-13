# Data-Modelling-with-Postgres

This project was aimed to organize given data in order to creat a database model which is satisfying requirements of star schema with PostgresSQL database. In this manner, Sparkify startup can be evolved on the light of the information about user activities. On the other hand, implementation of data analysis could be process on the relational database which is created by ETL pipelines and PostgresSQL.


## Project Roadmap and Files Repository

At the beginning of the project, the `sql_queries.py` file was generated via SQL in order to specify queries and adjust the tables. Then, the `etl.py` file was edited due to implementing data from the `data.zip` file, and required table data were reached. Also, the `etl.ipynb` file was used to show more details about the ETL pipeline demonstration. In this manner, the `create_tables.py` was used to create and delete tables via statements in `sql_queries.py`. Finally, `test.ipynb` was run in order to the check situation of created tables. In addition, `condition_check.ipynb` file was created for ease of use mentioned script files for modelling.


## Data Warehouse Design

In order to implement given data to build ETL pipeline, A fact table and four dimension tables were builded. These are shown in the figure below.


## FACT TABLE

### songplays
"songplay_id (primary key value)
"start_time
"user_id
"level
"song_id
"artist_id
"session_id
"location


## DIMENSION TABLES

### users                     ### songs                
"user_id (primary key)        "song_id (primary key)
"first_name                   "title
"last_name                    "artist_id  
"gender                       "duration 
"level

### artists                   ### time
"artist_id (primary key)      "start_time (primary key)  
"name                         "hour
"location                     "day
"latitude                     "week
"longitude                    "month
                              "year
                              "weekday


## IMPLEMENTATION OF MODELLING

1- In sql_queries.py, SQL query statements were edited for `create_tables.py` and `etl.py`. This file consists creat, drop and insert table statements.
2- In create_tables.py, functions defined in order to create, drop related tables. Also, sparkify database was created and connected by functions in the file. In conlusion, returns sparkifydb cursor. Finally, it closes sparkify cursor.
3- In `etl.py`, inserts data from song_data and log_data throught tables. Also, it reads and organizes the data from base folders.
