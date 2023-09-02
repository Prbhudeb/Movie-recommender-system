# Movie-recommender-system

Data Import and Preprocessing:-
->The code begins by importing necessary libraries, including NumPy and Pandas, to work with data efficiently.
->Two CSV files, 'tmdb_5000_movies.csv' and 'tmdb_5000_credits.csv,' are read into Pandas DataFrames, containing movie information and credits data.
->These DataFrames are merged based on the 'title' column, combining movie details and credits into a single dataset for analysis.

Feature Extraction:-
->The script focuses on extracting relevant features from the dataset, which are crucial for building a recommendation system.
->The 'genres,' 'keywords,' 'cast,' and 'crew' columns contain information about the movie's genre, keywords, cast members, and crew.
->Python's ast.literal_eval is used to convert string representations of lists and dictionaries in these columns into actual Python objects.

Text Data Processing:-
->Several functions are defined to process and transform text data:
->convert: Extracts the names of genres and keywords.
->convert2: Extracts the names of cast members, limiting the count to 3.
->fetch_director: Extracts the name of the movie's director.
->The 'overview' column is tokenized by splitting words.
->All text columns are cleaned by removing spaces and transforming them into lists of words.

Tag Generation:-
->A new column 'tag' is created, which combines information from 'overview,' 'genres,' 'keywords,' 'cast,' and 'crew' into a single list of words, representing the essence of each movie.

Text Vectorization:-
->The 'tag' column is further processed by converting it into lowercase and then applying Count Vectorization using Scikit-Learn's CountVectorizer. This converts the textual data into numerical features.

Stemming:-
->A stemming function (stem) is defined to reduce words to their root form. However, this function is defined but not applied in the provided code.

Cosine Similarity:-
->Cosine Similarity is calculated between movie vectors, resulting from the Count Vectorization. It quantifies the similarity between movies based on their tags.
->The similarity matrix is computed, which measures the similarity between each pair of movies.

Recommendation Function:-
->A recommendation function called recommend is defined to provide movie recommendations.
->Given a movie title as input, the function finds the index of the movie in the dataset.
->It calculates the cosine similarity between the input movie and all other movies.


The top 5 similar movies are selected and displayed as recommendations.
Overall, this code demonstrates a content-based movie recommendation system that processes and analyzes movie data, extracts relevant features, and uses text vectorization and similarity calculations to recommend movies based on their content. It showcases skills in data preprocessing, natural language processing, and recommendation system development.
