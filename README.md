# RECOMMENDATION-SYSTEM

*COMPANY* = CODTECH IT SOLUTIONS

*NAME* = G DEVA DHEERAJ REDDY

*INTERN ID*= CT04DF2074

*DOMAIN*=MACHINE LEARNING

*DURATION*=4 WEEKS

*MENTOR* =NEELA SANTOSH

Movie Recommendation System Using Matrix Factorization
This notebook presents a collaborative filtering approach to building a movie recommendation system using the MovieLens 100k dataset. The method is based on matrix factorization trained using Stochastic Gradient Descent (SGD). It provides personalized movie recommendations for users based on their past ratings and similarities with other users.

1. Data Loading and Preprocessing
The dataset used comes from the MovieLens 100k repository, containing 100,000 ratings from 943 users on 1,682 movies. The file u.data is loaded using pandas and contains four columns: userId, movieId, rating, and timestamp. The timestamp is dropped as it is not needed for recommendation tasks.

Both userId and movieId are converted into categorical variables. The categories are then converted to numerical indices (e.g., user_index and movie_index), which are essential for matrix operations in collaborative filtering.

2. Train-Test Split
The data is split into a training set (80%) and a test set (20%) using train_test_split. This division allows the system to learn patterns from the training data and then evaluate performance on unseen data.

3. Matrix Factorization via SGD
Matrix factorization is a technique used to decompose the large sparse rating matrix (user × movie) into two lower-dimensional matrices:

P: User-feature matrix (size: users × K)

Q: Movie-feature matrix (size: movies × K)

Each user and movie is represented by a vector in a K-dimensional latent space. These matrices are initialized randomly and iteratively updated using the SGD optimization technique. The loss function minimized is the squared error between predicted and actual ratings, regularized by a penalty term to avoid overfitting.

The function train_mf() implements this training over multiple epochs, updating P and Q after each user-movie interaction.

4. Prediction and Evaluation
Once training is complete, the full rating matrix is reconstructed using the dot product of P and Q. The model then evaluates its performance on the test set using two metrics:

Root Mean Squared Error (RMSE): Measures the average squared difference between predicted and true ratings.

Mean Absolute Error (MAE): Measures the average absolute difference.

These metrics give an idea of how close the predictions are to actual user ratings.

5. Generating Recommendations
The notebook defines a function recommend_top_n(user_id, N) that recommends top-N movies for a specific user. It:

Retrieves predicted ratings for the given user.

Masks already rated movies to avoid recommending them again.

Selects the top-N highest-rated unseen movies.

Retrieves movie titles from the u.item file to display human-readable recommendations.

This function is demonstrated for user_id=10, producing a list of 5 recommended movies.

*OUTPUT*=

