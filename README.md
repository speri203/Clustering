# K-Means Clustering
K-Means clustering on wine sales. Dataset found on Kaggle public datasets (https://www.kaggle.com/zynicide/wine-reviews?rvi=1)

This is a project focused on using K-Means clustering and was implemented using the sklearn module in python. There are two implementations of the K-Means using different datasets. 

- Kmeans_Clustering.ipynb implements K-Means on a randomly generated dataset of 300 points with the make_blobs function found in sklearn.datasets. This function utilizes the Guassian function to randomly generate data points with specified features and centers. For this implementation 2 features and 3 centers were selected with a cluster std of 0.8

    ```python
    x, y = make_blobs(n_samples=300, n_features=2, centers=3, cluster_std=0.8, shuffle=True, random_state=0)
    ```

    Resulting dataset is:

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/blob_unclustered.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/blob_unclustered.png)

    Calculating the inertia (SSE) for 1-10 clusters results in the following

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/blob_elbow.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/blob_elbow.png)

    Based on this it is determined that 3 clusters are required (confirms with the number of centers specified in the blob command)

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/blob_clustered.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/blob_clustered.png)

This project demonstrates how K-Means works and also implements the "Eblow" method to determine the proper number of clusters (wine_kaggle_clustering.ipynb). The dataset used was found on Kaggle and consists of ~150k rows of wine reviews. The headers for the dataset are as follows:

- Entry ID
- Country
- Description
- Designation
- Points
- Price
- Province
- Region 1
- Region 2
- Variety
- Winery

K-Means was utilized to cluster the data based on price/wine score, and price/type of wine.

- Price/Score Graph (outliers were removed using z-scores)

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/price-winescores-nooutliers.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/price-winescores-nooutliers.png)

    After applying SSE calculations, it was determined 2 clusters has the best result

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/cluster-price-winescores.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/cluster-price-winescores.png)

- Type of wine/price

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/variety-price.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/variety-price.png)

    The Elbow method for 1-20 clusters was computed and resulted in the following

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/elbow-variety-price.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/elbow-variety-price.png)

    Again, 2 clusters was selected and resulting classification was graphed with Price vs. Score

    ![K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/cluster-price-winescores-woutliers.png](K-Means%20Clustering%20585284788e824c07a408c3ba02157d17/cluster-price-winescores-woutliers.png)
