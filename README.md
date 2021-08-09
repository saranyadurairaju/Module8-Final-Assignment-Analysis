# Amazing Prime Data cleaning with ETL

ETL, which stands for extract, transform and load, is a data integration process that combines data from multiple data sources into a single, consistent data store that is loaded into a data warehouse or other target system. Below are the some advantages of ETL:

* Facilitate performance.
* Provide a visual flow.
* Track and perform impact analysis.
* Provide operational resilience.
* Handle Big Data.

## Overview of Project

Britta works for Amazing Prime and she needs to gather data from both Wikipedia and Kaggle, combine them, and save them into a SQL database for hackathon (An event where teams of analysts collaborate to work intensively on a project, using data to solve a problem) participants to have a nice, clean dataset to use. She is confident about the data-cleaning strategy where we are going to follow an iterative process based on three key steps: plan, inspect, execute. So, we are finding the below details:

  *	ETL Function to Read Three Data Files. 
  *	Extract and Transform the Wikipedia Data.
  *	Extract and Transform the Kaggle data.
  *	Creating the Movie Database
   
## Analysis 

Before we start doing our Analysis, we need to setup the dependencies Panda and Numpy libraries in our code to work with Data and Calculations. We have to load the file with the path and use .read function of Panda to read the data. Below are the dependencies we need:

![image](https://user-images.githubusercontent.com/85472349/128661228-ac6c23d1-bb6f-4d57-ae9b-c9e6b10fdbb8.png)
  
### ETL Function to Read Three Data Files

In this we are doing the below steps to write a function to read Data files:

* The function converts the Wikipedia JSON file to a Pandas DataFrame, and the DataFrame is displayed

* Also it converts the Kaggle metadata file to a Pandas DataFrame, and the DataFrame is displayed 
 
* MovieLens ratings data file also converted to a Pandas DataFrame and displayed

![image](https://user-images.githubusercontent.com/85472349/128661433-3f774b01-60e0-4be1-9ec6-0a663b25e001.png)

### Extract and Transform the Wikipedia Data

The extraction and transformation of the Wikipedia data in the ETL function does the following:

* A list comprehension is used to keep columns with non-null values. 

* The non-null box office data is converted to string values using the lambda and join functions.

* A regular expression is used to match the six elements of "form_one" of the box office data. 

* A regular expression is used to match the three elements of "form_two" of the box office data. 

* The following columns are cleaned in the Wikipedia DataFrame: 
	The box office column
	The budget column
	The release date column
	The running time column
* The cleaned Wikipedia data is converted to a Pandas DataFrame, and the DataFrame is displayed.

![image](https://user-images.githubusercontent.com/85472349/128661779-f8692833-4fb3-43a4-a458-17ee72da44ef.png)

![image](https://user-images.githubusercontent.com/85472349/128661813-06601c59-4eb0-445c-978e-daa9782a9a1f.png)

### Extract and Transform the Kaggle data

**The extraction and transformation of the Kaggle metadata using the ETL function does the following:**

* The Kaggle metadata is cleaned. 

* The Wikipedia and Kaggle DataFrames are merged.

* Columns are dropped, filled with missing data, filtered & renamed to create the movies_df.


**The extraction and transformation of the MovieLens ratings data using the ETL function does the following:**

* The ratings counts are cleaned. 

* The movies_df DataFrame is merged with the cleaned ratings DataFrame to create the movies_with_ratings_df DataFrame. 

* The empty values in the movies_with_ratings_df DataFrame are filled with “0”. 

**The movies_with_ratings_df and the movies_df DataFrames are displayed.**

![image](https://user-images.githubusercontent.com/85472349/128662070-516cd171-d048-4239-9727-c3a9cca884e2.png)

![image](https://user-images.githubusercontent.com/85472349/128662095-428ea7c9-15a6-4e4b-ad1e-1dececf7cbe7.png)


## Results

Here are the links for each delivery items mentioned above:

1) https://github.com/saranyadurairaju/Module8-Final-Assignment-Analysis/blob/main/ETL_function_test.ipynb

2) https://github.com/saranyadurairaju/Module8-Final-Assignment-Analysis/blob/main/ETL_clean_wiki_movies.ipynb

3) https://github.com/saranyadurairaju/Module8-Final-Assignment-Analysis/blob/main/ETL_clean_kaggle_data.ipynb


#### Movie Database Creation

The data from the movies_df DataFrame replaces the current data in the movies table in the SQL database.

![image](https://user-images.githubusercontent.com/85472349/128662456-61d61854-8fc5-4287-b48a-be026c098b24.png)


Below image show the query details of movies table from Postgres PgAdmin.



#### Adding MovieLens rating file

The data from the MovieLens rating CSV file is added to the ratings table in the SQL database.

![image](https://user-images.githubusercontent.com/85472349/128662558-3a6eff2e-25ee-4459-a64a-9502d85a6db7.png)


Below image show the query details of ratings table from Postgres PgAdmin.

#### The elapsed time

In our program, the elapsed time to add the data to the database is displayed like below:

![image](https://user-images.githubusercontent.com/85472349/128662644-11ba4df5-a546-4337-9d60-5f9884ff16cf.png)

Below are the links for database creation and Resource folder:

4) https://github.com/saranyadurairaju/Module8-Final-Assignment-Analysis/blob/main/ETL_create_database.ipynb

5) https://github.com/saranyadurairaju/Module8-Final-Assignment-Analysis/tree/main/Resources


So, this Movies-ETL(Module8-Final-Assignment-Analysis) GitHub repository contains the below list of items:

* The ETL_function_test.ipynb file

* The ETL_clean_wiki_movies.ipynb file

* The ETL_clean_kaggle_data.ipynb file

* The ETL_create_database.ipynb file

* The Resources folder with the wikipedia.movies.json, movies_metadata.csv, movies_query.png, and ratings_query.png files.

**Hurry! Database is ready for Hackathon!!!**