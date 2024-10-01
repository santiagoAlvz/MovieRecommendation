# MovieRecommendation
MovieRecommendation is an recommendation engine for movies built using the ![MovieLens Dataset](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset). It takes a movie as an input, and returns a list of the movies in the dataset that are most similar to it.

![image](https://github.com/user-attachments/assets/9bdb8640-57cd-42ab-b4dd-4c506c538187)


## Used Tools
This project is developed in Python, using the following libraries:
- Pandas
- Numpy
- Pyplot
- Seaborn
- Scikit-Learn
- Fuzzywuzzy

## Data
This engine is trained on data from the ![MovieLens Dataset](https://www.kaggle.com/datasets/grouplens/movielens-20m-dataset), more specifically, on the `movie.csv` and `rating.csv` files of the dataset. This files must be downloaded in the root folder for the model to train appropiately. The fields from considered into the dataset insights visualizations are the

- Title
- Genre(s)
- Release year
- Rating

of each movie.

![image](https://github.com/user-attachments/assets/704d91c1-c384-45be-b642-60f70c3d626b)

## Model and Recommendations
We've tried two approaches for generating movie recommendations.

### Collaborative Filtering
The first approach is to use the **k-Nearest Neighbors** algorithm to identify similar movies. This is performed by creating a utility matrix that relates movies and users with the rating given to each film, ignoring the rest of the movie attributes. This works based on the premise that if a user has rated two movies highly, it makes sense to use one of the movies as a recommendation for the other. A downside to this approach is that movies are required to have enough ratings for the predictions to be accurate (cold-start problem).

### Content-based filtering
The second approach consists in using **cosine similarity** on a matrix composed by the movie genres. This avoids the need for having enough reviews, but may have less sophisticated results than collaborative filtering.

## Performance
Below are the perfomance metrics for both approaches

![image](https://github.com/user-attachments/assets/669b5f27-833b-497a-9559-b1a87753c605)

While these metrics suggest excellent performance, it's important to consider the following:
1. **Overfitting:** Perfect scores might indicate overfitting, especially if the evaluation was done on a small or non-representative test set. Ensure that the evaluation is performed on a sufficiently large and diverse dataset.
2. **Real-World Performance:** Metrics calculated on historical data might not fully capture real-world performance. Consider conducting online evaluations (e.g., A/B testing) to validate these results with actual user interactions.
3. **Generalization:** Ensure that the model generalizes well to new users and items, particularly addressing the cold-start problem.

