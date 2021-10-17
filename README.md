# Forecasting MercadoLibre

`I use Facebook's forecasting tool (Prophet) and MercadoLibre time-series data (search traffic) for analysis. Specifically, I want to find out if the ability to predict search traffic translates into the ability to successfully trade the stock.`

---

## Description



---

## Technologies

This project leverages python 3.7 with the following packages:

* [pandas](https://github.com/pandas-dev/pandas) - For reading data into a DataFrame.

* [hvplot](https://pypi.org/project/hvplot/) - For embedding interactive plots in the application.

* [pathlib](https://pypi.org/project/pathlib2/) - For object-oriented file paths.

* [scikit-learn](https://pypi.org/project/scikit-learn/) - A set of python modules for machine learning and data mining.

* [KMeans](https://scikit-learn.org/stable/modules/clustering.html#k-means) - An algorithm that clusters data into groups to decrease the inertia of the dataset.

* [PCA](https://scikit-learn.org/stable/modules/unsupervised_reduction.html#pca-principal-component-analysis) - For unsupervised dimensionality reduction that generates principle components which sufficiently represent the variance of the various original features.

* [StandardScaler](https://scikit-learn.org/stable/modules/preprocessing.html#standardization-or-mean-removal-and-variance-scaling) - A way to normalize numeric data in a DataFrame.

---

## Installation Guide

Before running the application first install the following dependencies in a Google Colab file:

```python
  pip install pandas
  pip install hvplot
  pip install fbprophet
  pip install numpy
  pip install datetime
  pip install pystan
```

---

## Usage

To use the Forecasting MercadoLibre application:

1. Locally clone the time_series_forecasting_search_traffic repository from GitHub using the following link:

```python
git clone https://github.com/elliotlozano/time_series_forecasting_search_traffic.git
```

2. Run the [Forecasting MercadoLibre](forecasting_net_prophet.ipynb) program.

3. Examine the plots and review the commentary describing the significance of the results.

---

## Findings

The following visuals help summarize the findings:

![Explained Variance Ratios](explained_variance_ratios.png)
`Principle Component Analysis, or PCA, is a machine learning function that performs dimensionality reduction. It takes several features (columns) from a DataFrame and clusters them into fewer "principle components" that represent the overall variation of the original features. The "expalined variance ratio" measures how much of the original data variance is condensed into the principle components. Using PCA, this program took 7 features from our DataFrame and condensed them into 3 principle components shown in the list, above. These components contained 38.9%, 29.2%, and 20.8% of the original features' variance, respectively. Ultimately, the 3 components collectively represent almost 89% of the original 7 data features' variance!`

![Finding Optimal k](optimal_k_values.png)
`The elbow curve is a heuristic that helps determine optimal k, which represents the number of clusters for a dataset. The KMeans algorithm is an unsupervised learning technique in which data is separated into clusters based on their likeness in order to minimize inertia. Inertia is a measurement of the average distance from a centroid for all the datapoints within a cluster. The smaller the inertia, the smaller the spread of data in the cluster, and the more alike each datapoint is. The optimal number of clusters is subjective but it is found at the "elbow" of the curve and is generally acheived when inertia shows minimal change for each additional cluster. In our project, the original data has an elbow at k = 3 or 4, while the PCA data more distinctly shows an optimal k value of 4.`

![CLuster Analysis](cluster_scatter_plots.png)
`By using fewer features through PCA, the KMeans algorithm is able to create more optimal clusters than it did with the original data. In the PCA scatter plot, each cluster has distinct boundaries from one another and an overall decrease in inertia. The orignal data used the same k value of 4, but the clusters were more spread out from their centroids and some were partially overlapped with other clusters. Comparing the scatter plots confirms that using PCA is helpful when analyzing the differences for each cryptocurrency token's behavior. With this information it's possible to diversify an investment portfolio by selecting coins from a range of different clusters.`

---

## Contributors

Elliot Lozano

[E-mail](elliotlozano95@gmail.com)

---

## License

MIT


