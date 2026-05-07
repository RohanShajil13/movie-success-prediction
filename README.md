Movie Success Prediction Using TMDB Data
CS 210: Data Management for Data Science

Project Description
This project predicts movie financial success using the TMDB 5000 movie dataset. A movie is classified as successful if its revenue is greater than its budget. The project combines database design, data cleaning, visualization, and machine learning to analyze which movie features are most related to success.

Dataset
The project uses the TMDB 5000 Movies Dataset, which contains movie metadata such as title, budget, revenue, runtime, popularity, vote average, vote count, release date, genre, cast, and crew information.

Raw dataset files:
- Datasets/tmdb_5000_movies.csv
- Datasets/tmdb_5000_credits.csv

Cleaned dataset:
- Datasets/clean_movies.csv

Project Structure
Final Course Project/
- Datasets/
  - tmdb_5000_movies.csv
  - tmdb_5000_credits.csv
  - clean_movies.csv

- Database/
  - movie_success.db

- SQL_Results/
  - top_revenue_movies.csv
  - avg_profit_by_genre.csv
  - high_rated_movies.csv
  - director_success.csv
  - success_count.csv

- Visualization_Results/
  - top_genres_by_avg_profit.csv

- ML_Results/
  - model_performance.csv
  - random_forest_feature_importance.csv

- Notebooks/
  - data_cleaning.ipynb
  - sql_database.ipynb
  - visualization.ipynb
  - machine_learning.ipynb

Notebook Descriptions

1. data_cleaning.ipynb
This notebook loads the raw TMDB movies and credits datasets, merges them, cleans missing and invalid values, extracts useful information from JSON-style columns, creates new features, and saves the final cleaned dataset.

Main tasks:
- Load raw CSV files
- Merge movie and credit data
- Extract genres, keywords, cast, and director
- Remove invalid budget and revenue rows
- Create release_year, profit, ROI, main_genre, and main_actor
- Create the target variable success
- Save clean_movies.csv

2. sql_database.ipynb
This notebook creates a relational SQLite database using the cleaned movie dataset. The data is split into multiple related tables and SQL queries are used to analyze movie revenue, genre profitability, ratings, director success, and success counts.

Database tables:
- movies
- financials
- ratings
- people

Main tasks:
- Create SQLite database
- Insert cleaned movie data into relational tables
- Run SQL queries using joins, grouping, ordering, and aggregation
- Save query results to SQL_Results/

3. visualization.ipynb
This notebook performs exploratory data analysis using visualizations. It analyzes movie ratings, budget vs revenue, success distribution, genre profitability, popularity vs rating, and correlations between numeric variables.

Main visualizations:
- Distribution of movie ratings
- Budget vs revenue
- Successful vs unsuccessful movie count
- Top genres by average profit
- Popularity vs vote average
- Correlation heatmap

4. machine_learning.ipynb
This notebook trains machine learning models to predict whether a movie is financially successful.

Models used:
- Logistic Regression
- Decision Tree
- Random Forest

Evaluation metrics:
- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

Best model:
The Random Forest model performed best overall with an accuracy of approximately 76.9% and an F1-score of approximately 0.837.

How to Run the Project
Run the notebooks in this order:

1. Notebooks/data_cleaning.ipynb
2. Notebooks/sql_database.ipynb
3. Notebooks/visualization.ipynb
4. Notebooks/machine_learning.ipynb

Required Python Libraries
The project uses the following Python libraries:

- pandas
- numpy
- matplotlib
- seaborn
- sqlite3
- scikit-learn
- os
- ast

Install required libraries with:

pip install pandas numpy matplotlib seaborn scikit-learn

Notes
- SQLite is used for the database component, so no external database server is required.
- The cleaned dataset removes rows with missing or zero budget/revenue values because these values are needed to define financial success.
- Since the dataset contains more successful movies than unsuccessful movies, precision, recall, and F1-score are used along with accuracy to evaluate machine learning performance.

Limitations
Some features such as popularity, vote count, and vote average may only be fully known after a movie is released. Therefore, the machine learning model is best interpreted as predicting movie financial success using available movie performance indicators, rather than strictly predicting success before release. Also, removing movies with missing budget or revenue may bias the dataset toward movies with better-documented financial information.

Project Goal:
The goal of this project is to show how my database management, data cleaning, visualization, and machine learning can be combined to analyze and predict movie success using real-world movie data.