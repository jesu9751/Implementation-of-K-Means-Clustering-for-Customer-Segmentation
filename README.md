# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load the customer dataset and select the relevant features such as Annual Income and Spending Score.

2.Choose the number of clusters K and initialize K centroids randomly.

3.Assign each data point to the nearest centroid using Euclidean distance and update the centroids by calculating the mean of each cluster.

4.Repeat Step 3 until the centroids no longer change and display the final clusters for customer segmentation.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Jesu Joyal J
RegisterNumber:212224050154

# K-Means Clustering for Customer Segmentation

import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Load dataset
data = pd.read_csv("C:\\Users\\acer\\Downloads\\Mall_Customers.csv")

# Select features for clustering
X = data[['Annual Income (k$)', 'Spending Score (1-100)']]

# Using Elbow Method to find optimal clusters
wcss = []

for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++', random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)

# Plot Elbow Graph
plt.plot(range(1, 11), wcss)
plt.title("Elbow Method")
plt.xlabel("Number of Clusters")
plt.ylabel("WCSS")
plt.show()

# Apply K-Means
kmeans = KMeans(n_clusters=5, init='k-means++', random_state=42)
y_kmeans = kmeans.fit_predict(X)

# Visualizing the clusters
plt.scatter(X[y_kmeans == 0]['Annual Income (k$)'], X[y_kmeans == 0]['Spending Score (1-100)'], label='Cluster 1')
plt.scatter(X[y_kmeans == 1]['Annual Income (k$)'], X[y_kmeans == 1]['Spending Score (1-100)'], label='Cluster 2')
plt.scatter(X[y_kmeans == 2]['Annual Income (k$)'], X[y_kmeans == 2]['Spending Score (1-100)'], label='Cluster 3')
plt.scatter(X[y_kmeans == 3]['Annual Income (k$)'], X[y_kmeans == 3]['Spending Score (1-100)'], label='Cluster 4')
plt.scatter(X[y_kmeans == 4]['Annual Income (k$)'], X[y_kmeans == 4]['Spending Score (1-100)'], label='Cluster 5')

# Plot Centroids
plt.scatter(kmeans.cluster_centers_[:,0], kmeans.cluster_centers_[:,1],
            s=300, c='yellow', label='Centroids')

plt.title("Customer Segments")
plt.xlabel("Annual Income")
plt.ylabel("Spending Score")
plt.legend()
plt.show()
 
*/
```

## Output:
<img width="598" height="453" alt="image" src="https://github.com/user-attachments/assets/0acb08a4-74de-41c1-897c-a0f9b3c42146" />
<img width="573" height="453" alt="image" src="https://github.com/user-attachments/assets/3ca50a96-dcf0-4ca8-9a3f-73fd73a5749d" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
