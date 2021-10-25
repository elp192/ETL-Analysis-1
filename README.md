# Overview of the Project
In this project, the Extract, Transform, Load (ETL) process is performed on the dataset (i.e., [wikipedia data](https://github.com/elp192/ETL-Analysis-1/blob/5f60c07dc34687ee747dd730dcf32d9d6824dc24/data/wikipedia-movies.json), [movies metadata](https://github.com/elp192/ETL-Analysis-1/blob/5f60c07dc34687ee747dd730dcf32d9d6824dc24/data/movies_metadata.csv), and [ratings](https://www.kaggle.com/rounakbanik/the-movies-dataset?select=ratings.csv)). This ETL process prepares the data for the future project, predicting which of the released movies with a low budget can be popular.<br>
The following files are created to perform the ETL process:

1. Link to [**function_test**](https://github.com/elp192/ETL-Analysis-1/blob/5f60c07dc34687ee747dd730dcf32d9d6824dc24/function_test.ipynb) file
- Extracted Wikipedia and Kaggle data (kaggle metadata and ratings), which are in the format of JSON and CSV, respectively.
- Converted/transformed data into DataFrames.

2. Link to [**clean_wiki**](https://github.com/elp192/ETL-Analysis-1/blob/5f60c07dc34687ee747dd730dcf32d9d6824dc24/clean_wiki.ipynb) file
- clean_movie function: Handled the alternative titles by adding the "alt_titles" column as a dictionary.
- change_column_name subfunction: Merged the columns with the similar name and same contents.
- extract_transform_load function: 
  - Filtered TV shows by writing list comprehension.<br>
  - Applied clean_movie function on the movies by writing list comprehension.<br>
  - Extracted the movies ID using regular expression (regex) and removed duplicated ID.<br>
  - Removed null columns by writing list comprehension.<br>
  - Cleaned "Box Office", "Budget", "Release date", and "Running Time" columns by using regex, map, apply methods and/or parse_dollars subfunction (convert extracted values to a numeric values).<br>

3. Link to [**clean_kaggle**](https://github.com/elp192/ETL-Analysis-1/blob/5cf1a0a36f9e75327cc626a2110d67e7649eb21c/clean_kaggle.ipynb) file
- Added following tasks to the extract_transform_load function:
  - Dropped "adult" column.
  - Converted "video", "budget", "id", and "popularity" columns. Comparison operators, astype and pd.to_numeric methods are used.
  - Merged Wikipedia and Kaggle data(i.e., dropped unnecessary columns, used fill_missing_kaggle_data subfunction to fill the missing data, renamed columns).
  - Cleaned rating data and merged it to Wikipedia and Kaggle data.
  
4. Link to [**create_database**](https://github.com/elp192/ETL-Analysis-1/blob/5cf1a0a36f9e75327cc626a2110d67e7649eb21c/create_database.ipynb) file
- Transferred data to SQL table.
<br>
To perform ETL process following tools, language, and software are used:<br>
- Language: Python - code is written in Jupyter Notebook.<br>
- Software: PostgreSQL, PgAdmin.<br>
- Dependencies: Pandas, Numpy, json, re, sqlalchemy, psycopg2, config, time.
