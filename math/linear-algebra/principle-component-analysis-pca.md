# Principle Component Analysis \(PCA\)

**Principal Component Analysis**\(PCA\) is a method for reducing the _dimensionality_ of data. It is the process of finding the principal components of a dataset with m-columns \(features\) and projecting it into a subspace with fewer columns, whilst retaining the essence of the original data.

The first principal component of a dataset is the direction along the dataset with the highest variation. In the example shown below, the orange arrow points into the direction with the largest variance.

![](../../.gitbook/assets/pca_directions.png)

### Steps to find PCA

1. Collect the data
2. Normalize the data
3. Calculate the covariance matrix
4. Find the eigenvalues and eigenvectors of the covariance matrix
5. Use the principal components to transform the data - Reduce the dimensionality of the data 

Link:

* [Principle Component Analysis](https://www.python-course.eu/principal_component_analysis.php)
* [How to Calculate Principal Component Analysis \(PCA\) from Scratch in Python](https://machinelearningmastery.com/calculate-principal-component-analysis-scratch-python/)

