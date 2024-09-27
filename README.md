# MovieRecommendation
MovieRecommendation is an recommendation engine for movies built using the ![MovieLens Dataset](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset). It takes one or more movies as an input, and returns a list of the movies in the dataset that are most similar to the input movie(s).

![image](https://github.com/user-attachments/assets/f15cbd13-b4aa-429c-9ff5-988e28040213)

![image](https://github.com/user-attachments/assets/fffa15a4-b166-424b-8601-d7e0f025f615)

## Used Tools
This project is developed in Python, using the following libraries:
- Pandas
- Numpy
- Pyplot
- Scikit-Learn
- And Keras (using Tensorflow as a backend)

## Data
This engine is trained on data from the ![MovieLens Dataset](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset), more specifically, on the `movie.csv` and `rating.csv` files of the dataset. This files must be downloaded in the root folder for the model to train appropiately. The fields from considered into the dataset insights visualizations are the

- Title
- Genre(s)
- Release year
- Rating

of each movie. **We're only considering the movies from the dataset with more than 5,000 ratings**, therefore ignoring movies with not enough ratings to provide meaningful relationships with their viewers.
  
![image](https://github.com/user-attachments/assets/bde034bf-61d0-42c1-bf6d-a4c8b0b3d839)

## Model and Recommendations
For making movie recommendations, we're creating a model which takes the user and the movie IDs for a particular rating as `X` (considering them as categorical variables), and the rating given to the movie as `y`. Note that this model isn't generating recommendations by itself, but rather, that the weights of one of the layers of the model are used to deduct the similarity between films, as having users review both of them with high ratings implies a degree of similarity between them.

These weights are then used alongside the ID of the input movie(s) to identify the similarity with all other registered movies (or rather, with their ID). It is worth noting that IDs can be easily converted into the name of the movie they represent.

### Optimization
For obtaining the best performance possible, a `ModelCheckpoint` which saves only the best performing model is used. It considers the model with the lowest loss as the best performing one. This is the lost over training epochs for the model:

![image](https://github.com/user-attachments/assets/bc910617-7cdd-4855-a7d0-9bd57f6d1d99)

