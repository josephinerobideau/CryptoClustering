# Challange 11 - CryptoClustering
-------

## Overview and agenda for clustering
1. Import required libraries and dependencies
- pandas
  - Used for all data-related tasks (ex. data manipulation)
- KMeans
  - A class within sklearn.cluster used to determine the number of clusters needed for the KMeans algorithm
- PCA
  - A class within sklearn.decomposition used for identifying the variance of the clusters
- StandardScaler
  - Used to enhance model performance
2. Prepare the data
- Use StandardScaler to normalize the data from the CSV file
- Create DF with scaled data only
- Set the coin ID column as index
3. Find the best value for K using the original scaled DataFrame
- Create a list for K ranging from 1 - 11
- Create an empty list for inertia
- Create a for loop to compute the inertia with each possible value for K
  - Create a KMeans model using the loop counter for the n_clusters
  - Fit the model to the data using the scaler DataFrame
  - Append the model.inertia_ to the inertia list
- Create a dictionary with the data to plot the elbow curve
  - Put elbow data in a DF
  - Plot elbow data, and find best K value
  ![89ee24d8-35c6-408d-bd79-0fda7e08c73e](https://github.com/josephinerobideau/CryptoClustering/assets/143913881/543e9002-d2ee-414f-87c7-216c1bf9e24d)
4. Cluster Cryptocurrencies with K-means using the original scaled data
- Initialize the K-Means model using the best value for K
- Fit the model with the scaled data
- Predict the clusters to group the cryptocurrencies using the scaled data
  - View the array of clusters
- Copy DF
- Add a new column to DF with predicted clusters
  - Display sample data and create a scatter plot
    - x = price_change_percentage_24h
    - y = price_change_percentage_7d
    - c = crypto cluster
    ![778e09ae-0243-4de0-a66d-7ba0962087eb](https://github.com/josephinerobideau/CryptoClustering/assets/143913881/cddcbceb-fd9b-4e2a-85ce-c342fba9bafb)
5. Optimize clusters with principle component analysis
- Create PCA model instance
  - components = 3
- Use fit transform on the original scaled DF, and view
- Get explained variance ratio
- Create new DF with PCA data
6. Find the best value for K using the PCA data
- Create a list for K ranging from 1 - 11
- Create an empty list for inertia
- Create a for loop to compute the inertia with each possible value for K
  - Create a KMeans model using the loop counter for the n_clusters
  - Fit the model to the data using the PCA DataFrame
  - Append the model.inertia_ to the inertia list
- Create a dictionary with the data to plot the elbow curve
  - Put elbow data in a DF
  - Plot elbow data, and find best K value
![d7274719-243f-499e-a79c-fdae12c5be37](https://github.com/josephinerobideau/CryptoClustering/assets/143913881/aa6fa019-8c2e-4f16-a7fc-3d396b8f918b)
7. Cluster Cryptocurrencies with K-means using the PCA data
- Initialize the K-Means model using the best value for K
- Fit the model with the PCA data
- Predict the clusters to group the cryptocurrencies using the PCA data
  - View the array of clusters
- Copy DF
- Add a new column to DF with predicted clusters
  - Display sample data and create a scatter plot
    - x = PCA1
    - y = PCA2
    - c = crypto cluster
![7ebbb55c-1bc0-4c72-af7a-163366651b66](https://github.com/josephinerobideau/CryptoClustering/assets/143913881/6410c8bc-1321-4bfe-be39-bee1da351788)
8. Determine the weights of each feature on each principle component analysis
- Use the columns from the original scaled DataFrame as the index, set variable as pca_component_weights
- View pca_component_weights
  ![CB821C80-D956-48AD-B228-36AB4C90AABF_4_5005_c](https://github.com/josephinerobideau/CryptoClustering/assets/143913881/2d350c63-edf4-46c5-82e3-e367305f9d12)
-----------
### Additional sources
#### Sources like ChatGPT, Xpert learning assistant, AskBCS, Google, Youtube, and Columbia provided tutoring were used for clarification, and debugging if/where needed.







  
