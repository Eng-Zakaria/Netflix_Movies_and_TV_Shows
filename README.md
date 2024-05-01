## Netflix Movies and TV Shows Recommendation System

### Introduction
The Netflix Movies and TV Shows Recommendation System is a Python-based project designed to provide personalized recommendations for Netflix users. Leveraging machine learning techniques, it analyzes user preferences and viewing history to suggest relevant movies and TV shows.

### Getting Started
To use the recommendation system, follow the steps below:

1. **Installation**: Ensure you have Python installed on your system. Additionally, install the required libraries by running:
   ```bash
   pip install numpy pandas matplotlib scikit-learn
   ```

2. **Download Dataset**: Download the dataset `netflix_titles.csv` containing Netflix movies and TV shows information.

3. **Import the Project**: Import the necessary packages and load the dataset:
   ```python
   import numpy as np
   import pandas as pd
   import warnings
   from datetime import datetime
   from sklearn.feature_extraction.text import TfidfVectorizer
   from sklearn.metrics.pairwise import cosine_similarity

   # Suppress warnings
   warnings.filterwarnings('ignore')

   # Read the dataframe
   df = pd.read_csv('netflix_titles.csv', encoding='latin1')
   ```

### Data Preprocessing
The dataset is preprocessed to handle missing values and format data appropriately:

- Unwanted columns are removed.
- Missing values in the `director`, `cast`, `country`, and `date_added` columns are filled.
- Movies and TV shows are separated into different dataframes.
- Duration is standardized for movies.

### Feature Engineering
Feature engineering involves combining relevant text columns into a single feature column for similarity calculation:

- For movies and TV shows, relevant text columns (`cast`, `director`, `country`, `listed_in`, `description`) are combined.
- TF-IDF vectorization is applied to convert text data into numerical vectors.
- Cosine similarity is computed between the TF-IDF matrices to measure similarity between titles.

### Recommendation Generation
The recommendation system provides functions to generate movie and TV show recommendations based on similarity scores:

- For movies, the `recommend_movies()` function takes a title as input and returns similar movie titles.
- For TV shows, the `recommend_shows()` function takes a title as input and returns similar TV show titles.

### Example Usage
```python
# Generate movie recommendations
recommendation = recommend_movies('My Little Pony: A New Generation')
print(recommendation)
```

### Conclusion
The Netflix Movies and TV Shows Recommendation System offers a seamless way to discover new content based on user preferences. By leveraging machine learning techniques, it provides personalized recommendations, enhancing the user experience on the platform.
