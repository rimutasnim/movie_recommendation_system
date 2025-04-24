
# Movie Recommendation System

The explosion of digital content has led to an overwhelming amount of movies available for
viewers. Movie recommendation systems play a crucial role in helping users discover films
tailored to their preferences. This project implements a Movie Recommender System
utilizing various techniques to provide personalized movie suggestions based on user
preferences. The system integrates machine learning algorithms, text similarity measures, and
clustering to recommend movies that best match the user’s search query or favorites. Users
can also manage their list of favorite movies and filter results based on multiple criteria.


## Authors
- [@abdurrazzak](https://github.com/Arian104)
- [@tasnimrimu](https://github.com/rimutasnim)

## Background

In recent years, the entertainment industry has witnessed a rapid increase in the production
and availability of movies driven by advancements in streaming platforms and global
accessibility. With this catalog users often face difficulties in identifying content that aligns
with their preferences. Recommendation systems can have the solution of this critical
circumstance by leveraging machine learning and data analysis to provide personalized
content suggestions. By analyzing user behavior, preferences, and metadata, these systems
enhance user satisfaction, increase engagement, and contribute to the growth of the
entertainment sector. The advent of machine learning is natural language processing (NLP)
and collaborative filtering which has revolutionized recommendation systems. Content-based
and collaborative filtering techniques have become standard practices for personalized
content.
## Objectives

The primary objective of this project is to build a recommendation system where user can get
suggested movies as their preference. Here is the list of what we want to implement:
- Suggests movies based on user preferences or input.
- Top-rated movies according to year, rating or popularity.
- Enhances user experience by providing relevant and personalized suggestions.
- Leverages advanced machine learning techniques for improved accuracy and efficiency.
## Features
- Log in Option
- Search for movies based on titles.
- Add movies to their favorites list.
- Filter recommendations by various criteria (rating, year, genre, etc.).
- View detailed movie information.
- Filtering

## Methodology 

**Design** 

![UML Diagram](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/uml.png?raw=true)

**Data Collection and preprocessing**

Dataset and Loading The project utilizes a movie dataset TMDB_movie_dataset_v11.csv
which contains metadata for a large collection of movies including:

- Title
- Genre
- Release Date
- Vote Average
- Popularity
- Runtime
- Keywords
- Overview

The dataset is pre-processed to ensure data consistency handling missing values and filtering
movies based on the availability of poster images.
- Handling Missing Values: Missing values in the dataset are handled by filtering out rows with missing poster paths and keywords. Other missing data fields such as release_date are handled using NaT (Not a Time) to ignore invalid data.
- Feature Engineering: Extracting useful features such as keywords, genres, and popularity. The release_year feature is extracted from the release_date column and movies are filtered based on this year along with other criteria specified by the user.
- Text Processing: Tokenizing and vectorizing textual data (e.g., keywords and genres) for similarity calculations.
- Normalization: Standardizing numerical features to ensure uniformity.

**Recommendation Techniques**
- ***Text Similarity-Based Recommendations:*** This technique leverages the TF-IDF vectorizer to convert the movie keywords into numerical vectors which are then compared using cosine similarity.
- ***Clustering-Based Recommendations:*** The dataset is clustered using the K-Means clustering algorithm. Features such as vote_average, popularity, and runtime are scaled using StandardScaler, and clustering is performed with 10 clusters. As, K-Means clustering is an unsupervised algorithm that groups movies into clusters based on numerical features like popularity, ratings, and runtime. Each movie is represented as a point in multi-dimensional space and the algorithm assigns movies to clusters by minimizing the distance to the cluster centroids.
- ***Fuzzy Search:*** Fuzzy search is implemented using the fuzzy-wuzzy library, which calculates similarity scores between the search query and movie titles. This helps users find relevant movies even if they misspell the movie title or use partial names.
## Model Implementation
- ***Frameworks and Tools:*** The system is implemented using Google Colab and Python libraries such as Pandas, NumPy, Scikit-learn, and TensorFlow.
- ***User Interface:*** A web-based interface enables users to input preferences and receive recommendations.
## Results

The movie Recommendations system successfully provides personalized movie recommendations based on the following text similarity where movies are recommended
based on the similarity of their keywords to the movies in the user's favorites on the other side clustering movies are grouped based on features like popularity and runtime, and recommendations are made from the same cluster also “top movies” users can also view the highest-rated and most-voted movies.

![login](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/login%20.png?raw=true)

***Users can customize the filter:***


![filter](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/filtering.png?raw=true)

***According to Filtering Options:*** 

Highest-rated movies according to Filtering :

![HIGH](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/highest_rated_mv.png?raw=true)

Most Voted Movies:

![most_voted](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/most_voted_mv.png?raw=true)

Clustered Movies:

![clustered](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/clustered_mv.png?raw=true)

User Interactivity
● Movie Details: Detailed
information, including
posters, genres, ratings, and
overview, is displayed.
![details](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/movie_details.png?raw=true)

● Add to Favourite: Users can add/remove movies to/from their favorites list.
Favorites are stored in a JSON file for persistence.
![fav](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/adding%20_movies_to_favourite.png?raw=true)


After applying the add to favorite option the text similaty-based recommendation
works. By Using Cosine Similarity Recommendation

![cosinesimilarity](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/cosine_result.png?raw=true)

***Fuzzy Search***

![fuzzy1](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/fuzzy_search_result.png?raw=true)
![fuzzy2](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/fuzzy_serch_result2.png?raw=true)
![fuzzy3](https://github.com/Arian104/movie_recommendation_system/blob/main/screenshot/fuzzy_search_result3.png?raw=true)

## Limitation
- As I use Google Colab (free tier) and Streamlit Community it led to limited computational resources, runtime, and concurrent user sessions, leading to slower performance and reduced scalability.
- Colab sessions reset after runtime limits, requiring datasets and files to be reprocessed. Streamlit lacks persistent storage, preventing data from being saved between sessions.
- Both Colab and Streamlit require stable internet. Network issues can disrupt sessions or cause data to be unable to be retrieved from APIs like TMDB.
- The fuzzy matching algorithm for movie searches may yield irrelevant results for ambiguous or misspelled queries.
## Conclusion

This project demonstrates the potential of leveraging machine learning and content-based
filtering for movie recommendations. By addressing existing challenges and expanding
functionality, the system can significantly enhance user experiences in discovering movies
tailored to their preferences. The system integrates multiple recommendation strategies, such
as text similarity, clustering, and popularity-based methods, ensuring diverse
recommendations. With an intuitive user interface built with Streamlit, users can easily
search for movies, filter recommendations, and manage their favorite movies.
