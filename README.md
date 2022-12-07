# Movies-ETL

Project Description
Amazing Prime, which is a platform where movies and shows can be streamed online has developed a event for users called "The Hackathon". This event allows for users to predict the popularity of movies that are part of a clean dataset. The dataset for this event needs to be created first and involves the extraction of movie data from both Wikipedia and the MovieLens website. Data from these websites is merged into a single dataset and then loaded into a SQL database. The purpose of this project is to streamline the process by creating an automated pipeline which accomplishes this process utilizing less code overall. The code will transform both the Wikipedia and MovieLens extracted data and then load two tables into SQL automatically (a table containing the movies with associated information and another table for rating information).

Summary
4 separate Jupyter Notebook files were created:

ETL_function_test
ETL_clean_wiki_movies
ETL_clean_kaggle_data
ETL_create_database
ETL_function_test
This file tests a function called extract_transform_load() which reads kaggle metadata, a MovieLens ratings CSV, and a Wikipedia data JSON file and transforms each of these into a Pandas DataFrame. The head of each DataFrame is displayed at the end of this file.

ETL_clean_wiki_movies
This file incorporates a function called clean_movie() prior to the extract_transform_load() function which cleans the Wikipedia movie data from the JSON file by merging columns together with redundant data and changing the column names. The extract_transform_load() function now includes function within it called parse_dollars() which cleans up the data in the Box office column and Budget column. Regex is utilized to transform the Box office, Budget, release_date, and Running time columns each to a specific and uniform data format.

ETL_clean_kaggle_data
This file is the same as the ETL_clean_wiki_movies file but includes code which cleans up the kaggle metadata by removing unwanted data (dropping the adult column), converting the video column into a Boolean, converting budget, id, and popularity into numeric columns, converting release_date into datetime format, and merging this with the Wikipedia dataframe. This file also includes that cleaning of the ratings data (grouping by movieID and rating and merging with the movies DataFrame.

ETL_create_database
This last file incorporates the loading step of ETL into the extract_transform_load() function and imports the tables into SQL. The final product is 2 tables which are available to query in SQL - the movies table and the ratings table. I struggled getting the module to install and kept getting the error "ModuleNotFoundError: No module named 'psycopg2'" when attepting to get the SQL databases to run.  It is the only part I could nto figure out and wanted to get this turned in.   
