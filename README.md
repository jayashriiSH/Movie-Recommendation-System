# Movie Recommendation System

## **AIM OF THE TASK**

This is a Movie Recommendation System built using Python. The system suggests movies similar to the one you like based on features like genres, keywords, cast, crew, and overview of the movies.

## **DATASET USED**

We used the TMDb 5000 Movie Dataset available on Kaggle. It contains two main CSV files:

tmdb_5000_movies.csv – Contains movie details like title, genres, keywords, overview, revenue, runtime, and more.

tmdb_5000_credits.csv – Contains credits information like cast and crew for each movie.

## **Feature Selection**

Selected only important columns like title, overview, genres, keywords, cast, crew, tagline, spoken_languages, vote_average, and production_companies.

Converted JSON-like strings in columns (genres, keywords, cast, crew) to Python lists.
Extracted top 3 cast members and the director for each movie.
Cleaned the data by removing spaces and converting text to lowercase.
Creating a Combined 'Tags' Column
All the important textual features were combined into a single column called tags, which contains:

1) Movie overview
2) Genres
3) Keywords
4) Top cast
5) Director
This column is then converted into a single string for each movie to prepare for vectorization.

## **Text Vectorization**

Used CountVectorizer from Scikit-learn to convert text into numerical vectors.
Limited the vocabulary to 5000 words and removed English stop words.
Each movie is now represented as a 5000-dimensional vector.

 ## **Calculating Similarity**
Calculated cosine similarity between all movie vectors.
Cosine similarity gives a score between 0 and 1 showing how similar two movies are.
Higher score is more similar movies.

## output
**Recommending Movies**

Input a movie title to get recommendations.
System finds the movie’s vector and compares it with all other movies.
Returns the top 10 movies with the highest similarity scores (excluding the input movie).
