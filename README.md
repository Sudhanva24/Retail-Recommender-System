# Retailrocket Recommender System

## Dataset
https://www.kaggle.com/datasets/retailrocket/ecommerce-dataset

## Aim:
Build a Reccommender systems to reccommend items to users based on user activity

## Constraints:
Due to huge volume of dataset we worked with sampled version of data

## Content Based Reccommender System

In the fist notebook we have used the content based approach where we first formed the user item rating dataframe. we have assigned 3 for view,4 for addtocart and 5 for transaction,
Then using the item properties dataset we concatenated the properties and used tfidf to vectorize them to form item properties
Then to form user vectors in the same space we took the weighted sum of the item vectors as per the rating assigned by the users and then normalized them.
To reccommend items to users we calculated the cosine similarity between the user and item vectors and then reccommend accordingly

Using this Method we got a Root Mean Sqaure error of 1.84 .
The results were not as expected may be because the property values were hashed and hard to interpret while assigning the minimum document and maximum document frequency values

## Collaberative Filtering

In the second notebook we have used collaberative filtering aaproach. Again due to memory constraints we had to limit the users and item data to a large extent
We formed the **utility matrix** then filled the missing values with 0.
We used two approached for matrix factorization
1. Singular Value Decomposition
2. Weighted alternating Least Squares (WALS)

SVD with 50 components gave a better result with a RMSE of just 0.3 . While WALS gave 0.8 as the RMSE value.

Hence we decided to go with the vectors produced by SVD

