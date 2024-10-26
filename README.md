# Movie Recommendation Model

This project implements a movie recommendation model based on vectorization, designed to recommend similar movies to users based on selected attributes. By transforming movie features into vectors, the model computes similarity scores between movies to generate recommendations. This approach uses natural language processing  to analyze textual .

The model is built using the following libraries:
pandas, numpy, sklearn, ast and nltk 

## Dataset

WE will be using the famous TMDB movie dataset
The dataset consists primarily of English movies and includes information on:

- **Cast**: Mainly the top 5 actors.
- **Crew**: Information about the director, story and screenplay writer.
- **Genre**: The primary factor in establishing similarity.
- **Overview**: A brief description of the movie, providing view of its theme, plot, and unique elements.

## Feature Engineering

Feature engineering involves transforming the movie dataset into a format suitable for vectorization. This includes:

1. **Textual Vectorization**:
   - We preprocess text-based features (e.g., cast, crew, genre, and overview) to remove stopwords, special characters, and other irrelevant elements.
   - The `nltk` library is used to tokenize and normalize text, converting each feature into a set of keywords or tags.

2. **Tag-Based Representation**:
   - Key tags from **cast**, **crew**, **genre**, and **overview** fields are extracted and combined to create a unique tag profile for each movie.
   - This combined tag profile acts as a representation of each movie’s defining characteristics.

3. **Vectorization**:
   - Using **Count Vectorizer** from `sklearn`, the tag profiles are converted into vectorized form, creating numerical representations for each movie.
   - These vectors encapsulate the essence of each movie based on its content and associated tags.

4. **Similarity Calculation**:
   - Cosine similarity is computed between movie vectors to determine how closely related two movies are based on their tags.
   - The model ranks movies by similarity score, enabling accurate recommendations of movies that align with a user's interest.

## Recommendation Generation

Given a movie, the model identifies and recommends similar movies by calculating similarity scores between the selected movie and all other movies in the dataset. The highest similarity scores correspond to the top 5 recommendations.
