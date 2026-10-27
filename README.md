# Movie Recommendation System

A content-based movie recommendation system built with Python, scikit-learn, and Streamlit. Select a movie and get five similar recommendations with posters.

## Features

- Recommends 5 similar movies based on plot, genres, keywords, cast, and director
- Fetches movie posters using the TMDB API
- Simple web interface built with Streamlit

## How It Works

1. Merge the TMDB movies and credits datasets
2. Extract genres, keywords, top 3 cast members, and the director
3. Combine them with the movie overview into a single `tags` column
4. Convert text to vectors using `CountVectorizer` (5000 features, English stop words removed)
5. Compute `cosine_similarity` between all movies
6. Return the 5 most similar movies for the selected title

## Tech Stack

Python, Pandas, NumPy, scikit-learn, Streamlit, Requests, TMDB API

## Dataset

[TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata) (`tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`)

## Setup

1. Clone the repository
```
git clone https://github.com/komalsahu407/movie-recommendation-system.git
cd movie-recommendation-system
```
2. Install dependencies
```
pip install -r requirements.txt
```
3. Download the dataset from Kaggle and place both CSV files in the project folder
4. Run the notebook to generate `movie_list.pkl` and `similarity.pkl`
5. Add your TMDB API key in `app.py` (`API_KEY`). A free key is available at [themoviedb.org](https://www.themoviedb.org/settings/api)
6. Start the app
```
streamlit run app.py
```

## Project Structure

```
├── app.py              # Streamlit app
├── movie_recommender.ipynb   # Data processing and model building
├── requirements.txt
└── README.md
```

## Future Improvements

- Hybrid recommendations using user ratings
- Evaluation metrics for recommendation quality
- Review sentiment analysis for recommended movies

