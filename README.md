# KC-Housing-Data
Clustering Analysis of housing data by checking the other attributes/variables which have to be considered using KMeans Algorithm.

## Description:
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

This technique gives favor to data points which are not near another initial centroids..

## Features :
1) Runs multiple clustering attempts to find optimal solution 
   (single runs are susceptible to falling into non-optimal local minima)
2) Initializes centroids via k-means++ algorithm, for faster convergence
3) Calculates silhouette score for evaluation
4) Option to scale data before clustering, so that output isn't biased by different feature scales
5) Works with high-dimensional data 

## Variables:
1)  Id(Integer)
2)  date(Date)
3)  price(Float) - Price of the house
4)  bedrooms(Integer) - Number of Bedrooms
5)  bathrooms(Integer) - Number of Bathrooms
6)  sqft_living(Integer) - Square feet area of living area
7)  sqft_lot(Integer) - Square feet area of parking Layout
8)  floors(Float) - Number of Floors
9)  waterfront(Binary) - Whether waterfront is there or not
10) view(Integer) - Number of Views
11) grade(Integer) - Grades
12) sqft_above(Integer)
13) sqft_basement(Integer) - Square feet area off basement
14) yr_built(Integer) - Year the house is built
15) yr_renovated(Integer) - Year the house is renovated
16) zipcode(Integer) - zipcode os the house
17) lat : Latitude of the house
18) lon : Longitude of the house
19) sqft_living15(Integer)
20) sqft_lot15(Integer)

## library:
1) os
2) pandas
3) numpy
4) matplotlib.pyplot
5) sklearn - sklearn.preprocessing, sklearn.cluster, sklearn.metrics
6) from scipy.spatial.distance import cdist
7) cluster_profiles

## Elbow curve:
![elbow_curve_kc_housinf](https://user-images.githubusercontent.com/44108439/50799621-c8215200-1302-11e9-8f7e-ed70beb19d02.png)
- WSS: Weighted Sum Statistic
- With the help of Elbow curve, we can decide on the value of k. In this case, we can take the value of k as 8.
## Conclusions: 
- Silhoutte score for k= 8 is 0.290830730293
- Silhoutte score for k= 9 is 0.284943550666
- Silhoutte score for k= 10 is 0.280298178657
- From of the above Silhoutte scores, we can decide on the k value as 8. 
- Therefore, the Accuracy for kmeans cluster analysis is 29% i.e., when Silhoutte score for k=8.
