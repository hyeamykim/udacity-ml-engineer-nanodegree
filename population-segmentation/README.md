# Population Segmentation

The project is following the footsteps of the AWS blog post on US Population segmentation.\
(https://aws.amazon.com/ko/blogs/machine-learning/analyze-us-census-data-for-population-segmentation-using-amazon-sagemaker/) \
The data on the US population including demographic traits about labor, age, population, etc., collected by the US Census was used.



## Overview of the Notebook
- Data loading and exploration
- Data cleaning and pre-processing
- Dimensionality reduction with PCA
- Feature engineering and data transformation
- Clustering transformed data with k-means
- Extracting trained model attributes and visualizing k clusters

## PCA
Principal Component Analysis (PCA)  was used to reduce the number of features within a dataset while retaining the “principal components”, which are defined as weighted combinations of existing features that:

- Are uncorrelated with one another, so you can treat them as independent features, and
- Account for the largest possible variability in the data

So, the first component will be responsible for the largest variability on the data and the second component for the second-most variability, and so on. 


## K-Means Clustering
K-means clustering was used to perform population segmentation, to group data into similar clusters. 

K-means works as follows:
- Select k, a predetermined number of clusters that you want to form. 
- Select k points (centroids for k clusters) at random locations in feature space. 
- For each point in your training dataset:
 1. find the centroid that the point is closest to
 2. assign that point to that cluster
 3. Then, for each cluster centroid, move that point such that it is in the center of all the points that are were assigned to that cluster in step 2.
 4. Repeat steps 2 and 3 until convergence when points no longer change cluster membership or until some specified number of iterations have been reached.
