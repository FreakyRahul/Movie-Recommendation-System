# Movie-Recommendation-System
This README file provides an overview of the code and its functionalities.

## Introduction

This code implements a Movie Recommender System using the Streamlit library. The system is based on movie data, including movie titles, overviews, genres, keywords, cast, and crew. The recommendation is made using cosine similarity between movies, and the results are displayed in a Streamlit web application.

## Code Overview

### Data Loading and Preprocessing

- Two datasets, `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`, are loaded into DataFrames (`movies` and `credits`).
- The two DataFrames are merged on the 'title' column to create a single DataFrame.
- Irrelevant columns are dropped, and missing values are removed from the DataFrame.

### Text Processing

- The 'genres', 'keywords', 'cast', and 'crew' columns are processed to extract relevant information.
- The information is converted to lowercase and spaces are removed. Stemming is applied to text data using the Porter Stemmer.
- The processed information is combined into a new 'tags' column.

### Vectorization

- Count Vectorization is applied to convert the 'tags' column into a feature matrix with a maximum of 5000 features.
- Cosine similarity is calculated between movies based on their vectorized tags.

### Movie Recommendation

- A function `recommend(movie)` is defined to provide movie recommendations based on user input.
- The Streamlit web application allows users to select a movie and receive recommendations by clicking the 'Recommend' button.

### Streamlit Web Application

- The Streamlit app, `app.py`, is designed to interactively recommend movies.
- Users can select a movie from the provided dropdown menu and click the 'Recommend' button to see the top 5 recommended movies with their posters.
- Movie posters are fetched using The Movie Database (TMDb) API.

## Instructions

1. Ensure that you have the required libraries installed (`numpy`, `pandas`, `streamlit`, `requests`, `nltk`, and `scikit-learn`).
2. Run the code in the provided order: data loading and preprocessing, text processing, vectorization, and movie recommendation.
3. Execute the Streamlit app using `streamlit run app.py`.
4. In the web application, select a movie from the dropdown menu and click the 'Recommend' button to view the top 5 recommended movies with their posters.

## Additional Notes

- The code includes commented-out sections related to pickling the processed data and similarity matrix. Uncomment and run these sections if you want to save and load these files for future use.
- Ensure you have a valid TMDb API key for fetching movie posters. Update the key in the `fetch_poster` function.

Enjoy exploring and discovering new movies with the recommender system!
