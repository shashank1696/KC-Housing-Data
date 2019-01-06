# KC-Housing-Data
Clustering Analysis of housing data by checking the other attributes using KMeans Algorithm

## Description
k-means attempts to identify a user specified k(<N) number of clusters from a set of N d-dimensional real valued vectors. The algorithm proceeds by attempting to minimize the sum of squared distances from a cluster center, to the cluster members. The canonical algorithm proceeds in three phases:

1) Initialise k random centroids (cluster centers);
2) Assign data points to nearest cluster according to distance metric (typically Euclidean distance);
3) Update the centroids to the mean of the members of the cluster;
4) Repeat steps 2 & 3 until the assignments from step 2 do not change.

The output of the algorithm is a cluster assignment for each data point, and a final level of "distortion". The algorithm does not produce a provably optimal solution, and initial cluster centers may cause the algorithm to get stuck in a locally optimum solution that is clearly sub-optimal.

Much research has focused on:
- Selecting initial cluster centers. K-Means++ is a well known method, and is included in this implementation, the algorithm is outlined in the following sub-section.
- Computing distances, i.e. using measures other than Euclidean.

## K-Means++
Rather than initialize random centroids as in step 1 above, k-means++ probabilistically spreads out the initial centroids to avoid poor initial configuration, the algorithm is:

1) Choose first centroid randomly.
2) For each data point x, compute the distance d(x), from x to the nearest centroid that has already been chosen.
3) Select a data point to be the next centroid using a weighted probability proportional to d(x)2.

This technique gives favor to data points which are not near another initial centroids, and uses a selection policy that is reminiscent of roulette wheel (or fitness proportionate) selection that is often used in genetic algorithms.

## Features :
1) Runs multiple clustering attempts to find optimal solution 
   (single runs are susceptible to falling into non-optimal local minima)
2) Initializes centroids via k-means++ algorithm, for faster convergence
3) Calculates silhouette score for evaluation
4) Option to scale data before clustering, so that output isn't biased by different feature scales
5) Works with high-dimensional data

## Steps :
1)
2)
3) 

## library :
1) os
2) pandas
3) numpy
4) matplotlib.pyplot
5) sklearn - sklearn.preprocessing, sklearn.cluster, sklearn.metrics
6) from scipy.spatial.distance import cdist
7) cluster_profiles
