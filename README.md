# Big-Domty

![Screenshot from 2023-05-20 21-50-07](https://github.com/ahmedihabb2/Big-Domty/assets/57008633/2690779c-a718-40a3-90b9-7c8e7d041c0c)


**Big Domty** is a powerful code developed for conducting comprehensive player analysis within the context of FIFA 22, the popular football simulation video game. This code utilizes advanced data processing and statistical techniques to extract valuable insights and provide meaningful information about individual players.

Also **Big Domty** harnesses the power of PySpark, a Python library for distributed data processing, to efficiently handle large-scale player data analysis. By leveraging the distributed computing capabilities of Spark, the code is able to process vast amounts of player data in a parallel and scalable manner.

## Pipeline

![Screenshot from 2023-05-20 21-51-14](https://github.com/ahmedihabb2/Big-Domty/assets/57008633/4973207c-7ae4-4395-8e1e-a22e182ef20f)

## Data Preprocessing
- Drop any unneeded column from the data such as ids and any column with urls.
- Checking for null values in all columns
  - No null values found in all columns.
- Define all categorical columns and perform the following
  - Label Encoder to encode the categorical column to number.
  - One hot Encoder to represent categorical variables as numerical values in a machine learning model.

## EDA
Q1. what are the height, wage, weight and age distribution of players?
Q2. Calculate the number of players whose preferred foot is right and left.
Q3. What attributes that have the max effect on wage of players? (correlation)
Q4. what is the relation between mentality vision of the player and his wage?
Q5. does skill curve of players affected by their age?
Q6. who are the top 20 potential players in the data set?
Q7. How does international reputation affect the the wage?
Q8. what is the distribution of player_positions in the data set for the top 50?
Q9. what is the nationality percentage for the top 50 players?
Q10. what is the nationality of the highest mentality of the top 50 player?
Q11. who are the highest wage players in the top 50 players?

## Regression Models

The numerical features were  scaled using StandardScaler, then assembled into a feature vector using VectorAssembler. 
The categorical features were one-hot encoded, then assembled into a feature vector. 
Finally the numerical and categorical features vectors were assembled into one feature vector
Three models were used
  Linear regression
  Decision Tree regression
  Generalized linear regression
  
## Clustering

-Applied PCA : decreased the number of features to 30 with 95% variance, used the first 3 for proper visualization
- Clustering using MapReduce
- Calculated WCSS to determine the best number of clusters
- Initialize the centroids by picking random k points from the data and mark them as centroids
- The map is responsible for calculating the best cluster for a given point and return (bestcluster , (point , 1))
- The reducer sums the points and their count in order to compute the new centroid
- The mapper compute the new centroids for each cluster
- Use KMeans from pyspark.ml with same number of clusters and compare the results



