# Forecasting MercadoLibre

`I use Facebook's forecasting tool (Prophet) and MercadoLibre time-series data (search traffic) for analysis. Specifically, I want to find out if the ability to predict search traffic translates into the ability to successfully trade the stock.`

---

## Description

This project performs a time-series analysis on MercadoLibre's search traffic data and closing prices. Search traffic is imported from a CSV that contains search data from Google Trends. First I analyze whether or not there are patterns in the time series data, and whether seasonality has any affect on mercadoLibre's popularity. Next, I used close prices to generate hourly returns and volatility data for the same period as the search traffic data and analyzed whether or not their were any useful correlations. If so, there may be an opportunity to use search traffic to successfully trade MercadoLibre stock. Lastly, I used Facebook's forecasting tool, Prophet, to generate a prediction for both search traffic and quarterly revenues for the company 90 days into the future.

---

## Technologies

This project leverages python 3.7 with the following packages:

* [pandas](https://github.com/pandas-dev/pandas) - For reading data into a DataFrame.

* [hvplot](https://pypi.org/project/hvplot/) - For embedding interactive plots in the application.

* [numpy](https://pypi.org/project/numpy/) - For scientific computing in Python.

* [pystan](https://pypi.org/project/pystan/) - A Python interface to Stan, a platform for statistical modeling and high-performance statistical computation.

* [fbprophet](https://pypi.org/project/fbprophet/) - For automatic time-series forecasting.

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

![Correlation: Traffic, Returns, and Volatility](correlation_table.png)
`Principle Component Analysis, or PCA, is a machine learning function that performs dimensionality reduction. It takes several features (columns) from a DataFrame and clusters them into fewer "principle components" that represent the overall variation of the original features. The "expalined variance ratio" measures how much of the original data variance is condensed into the principle components. Using PCA, this program took 7 features from our DataFrame and condensed them into 3 principle components shown in the list, above. These components contained 38.9%, 29.2%, and 20.8% of the original features' variance, respectively. Ultimately, the 3 components collectively represent almost 89% of the original 7 data features' variance!`

![Forecasting Search Traffic](forecast_traffic.png)
`The elbow curve is a heuristic that helps determine optimal k, which represents the number of clusters for a dataset. The KMeans algorithm is an unsupervised learning technique in which data is separated into clusters based on their likeness in order to minimize inertia. Inertia is a measurement of the average distance from a centroid for all the datapoints within a cluster. The smaller the inertia, the smaller the spread of data in the cluster, and the more alike each datapoint is. The optimal number of clusters is subjective but it is found at the "elbow" of the curve and is generally acheived when inertia shows minimal change for each additional cluster. In our project, the original data has an elbow at k = 3 or 4, while the PCA data more distinctly shows an optimal k value of 4.`

![Forecasting Quarterly Revenue](forecast_revenue.png)
`By using fewer features through PCA, the KMeans algorithm is able to create more optimal clusters than it did with the original data. In the PCA scatter plot, each cluster has distinct boundaries from one another and an overall decrease in inertia. The orignal data used the same k value of 4, but the clusters were more spread out from their centroids and some were partially overlapped with other clusters. Comparing the scatter plots confirms that using PCA is helpful when analyzing the differences for each cryptocurrency token's behavior. With this information it's possible to diversify an investment portfolio by selecting coins from a range of different clusters.`

---

## Contributors

Elliot Lozano

[E-mail](elliotlozano95@gmail.com)

---

## License

MIT


