# Movie Analysis

## About
This project focuses on analyzing movie data to derive insights across various aspects of film performance, content strategy, and release optimization. The dataset was obtained from [Kaggle Top Rated Movies Dataset](https://www.kaggle.com/datasets/khalidalam980/top-rated-movies-data-set)

## Aim of the project
The primary objectives of this analysis are:

**1. Movie Performance:**

- Identify top-performing movies.

- Understand performance trends over time.

**2. Content Strategy:**

- Analyze language and market focus to inform content decisions.

**3. Release Strategy Optimization:**

- Determine optimal release windows for movies.

## Dataset
This dataset was obtained from [Top Rated Movies Dataset](https://www.kaggle.com/datasets/khalidalam980/top-rated-movies-data-set). Contains various aspects of the movies collected that be used to classify. This data contains 9 columns and 9610 rows

| Column Name               | Description                          | Data Type     |
|---------------------------|--------------------------------------|---------------|
|  Unnamed: 0               | Unnamed index column                 | int64
|  id                       | Unique identifier for the movie      | int64
|  original_language        | Original language of the movie       | object
|  title                    | Title of the movie                   | oject
|  overview                 | Brief summary or synopsis of the movie | object
| popularity                | Popularity score of the movie        | float64
| release_date              | Date when the movie was released     | object
| vote_average              | Average rating of the movie          | float64
| vote_count                | Numbers of votes received by the movie | int64

## Notebook Structure and Analysis Steps
The [main.ipynb](https://github.com/d-kod/movie_analysis/blob/main/code/main.ipynb) notebook follows a structured approach, encompassing several key stages of data analysis:

**1. Import Libraries**

Essential Python libraries for data manipulation, analysis, and visualization are imported, including:

- numpy

- pandas

- matplotlib.pyplot

- seaborn

**2. Importing Dataset**

The [top_rated_movies.csv](https://github.com/d-kod/movie_analysis/blob/main/code/top_rated_movies.csv) file is read into a pandas DataFrame named movies.

**3. Data Profiling**

This section includes an initial examination of the dataset to understand its structure, content, and basic statistics. This involves:

- Displaying the head of the DataFrame ___movies.head()___

- Checking information about the DataFrame, including data types and non-null counts ___movies.info()___

- Generating descriptive statistics ___movies.describe()___

- Checking the shape of the DataFrame ___movies.shape___

- Displaying column names ___movies.columns___

**4. Data Cleaning**

This crucial step addresses data quality issues:

- **Handling Duplicates:** The notebook checks for and confirms no duplicate rows exist ___movies.duplicated().sum()___

- **Handling Missing Values:** Missing values are identified, specifically 2 missing values in the 'overview' column ___movies.isna().sum()___

- **Dropping Irrelevant Data:** Irrelevant columns such as 'Unnamed: 0' and 'overview' are dropped from the dataset -__movies.drop()___

**5. Data Standardization**

Data types and formats are standardized for consistency and usability:

- The 'release_date' column is converted to datetime objects ___pd.to_datetime()___

- The 'original_language' column is converted to uppercase for uniformity ___.str.upper()___

**6. Feature Engineering**

A new feature, _'weighted_rating'_, is added to the dataset, calculated by multiplying 'vote_average' and 'vote_count' ***movies['weighted_rating'] = movies['vote_average'] * movies['vote_count']***

**7. New Dataset**

The cleaned and engineered dataset is saved as a new CSV file named [movies.csv](https://github.com/d-kod/movie_analysis/blob/main/code/movies.csv)

**8.  Exploratory Data Analysis (EDA)**

**8.1. Movie Performance Trends**
- **Distribution of Movie Ratings**
  Analyzed  the distribution of *vote_average* frequency of the movies as shown below:

  ![Alt Text](https://github.com/d-kod/movie_analysis/blob/main/analysis_graphs/distribution_of_movie_ratings.png?raw=true)
  

We analyzed the distribution of _vote_average_ and _popularity_ to understand how movies are generally received.

* The average _vote_average_ across all movies is around [Your Average Score], with a noticeable number of highly-rated films despite a long tail of lower-rated ones.
* Popularity scores vary widely, indicating a few highly popular movies and many with lower engagement.


