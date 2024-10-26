# ProductRecommendation
A machine learning-based product recommendation system designed to enhance user shopping experiences by providing personalized product suggestions. 

# E-commerce Product Recommendation System

This project is a machine learning-based product recommendation system that provides personalized product recommendations to users based on their browsing and purchase history. It utilizes collaborative filtering and content-based filtering algorithms to analyze user behavior and generate relevant recommendations. The goal is to enhance the overall shopping experience for users and increase sales for e-commerce businesses.

## Table of Contents
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [Approach](#approach)
  - [Rank Based Product Recommendation](#1-rank-based-product-recommendation)
  - [Similarity-Based Collaborative Filtering](#2-similarity-based-collaborative-filtering)
  - [Model-Based Collaborative Filtering](#3-model-based-collaborative-filtering)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Technologies Used
- Python
- Pandas
- NumPy
- Jupyter Notebook
- Scikit-learn

## Dataset
The project utilizes an Amazon dataset on user ratings for electronic products. This dataset does not have any headers, and to avoid biases, each product and user is assigned a unique identifier instead of using their name or any other potentially biased information.

- You can find the [dataset here](https://www.kaggle.com/datasets/vibivij/amazon-electronics-rating-datasetrecommendation/download?datasetVersionNumber=1).
- Many other similar datasets can be found [here](https://jmcauley.ucsd.edu/data/amazon/).

## Approach

### 1) Rank Based Product Recommendation
**Objective:**
- Recommend products with the highest number of ratings.
- Target new customers with the most popular products.
- Solve the Cold Start Problem.

**Outputs:**
- Recommend top 5 products with a minimum of 50/100 ratings/interactions.

**Approach:**
- Calculate the average rating for each product.
- Calculate the total number of ratings for each product.
- Create a DataFrame using these values and sort it by average.
- Write a function to get 'n' top products with the specified minimum number of interactions.

### 2) Similarity-Based Collaborative Filtering
**Objective:**
- Provide personalized and relevant recommendations to users.

**Outputs:**
- Recommend top 5 products based on interactions of similar users.

**Approach:**
- Convert user_id to integer type for convenience.
- Write a function to find similar users based on cosine similarity and extract their similarity scores.
- Create a function to recommend products based on the similar users identified.

### 3) Model-Based Collaborative Filtering
**Objective:**
- Provide personalized recommendations based on past behavior and preferences.

**Outputs:**
- Recommend top 5 products for a particular user.

**Approach:**
- Convert the ratings matrix to a CSR (Compressed Sparse Row) matrix to save memory and computational time.
- Perform singular value decomposition (SVD) on the sparse matrix to reduce dimensionality.
- Calculate the predicted ratings for all users using SVD.
- Store the predicted ratings in a DataFrame and filter it to only include products that the user has not rated.

## Installation
To run the project, clone the repository and install the required packages:

```bash
git clone https://github.com/yourusername/ecommerce-product-recommendation-system.git
cd ecommerce-product-recommendation-system
pip install -r requirements.txt
