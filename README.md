# Cryptocurrencies
Jupyter Notebook
Cryptocurrencies

Project Overview

Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

Purpose

The Data on which we are working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what we are looking for, so we have decided to use unsupervised learning. To group the cryptocurrencies, team decided on a clustering algorithm and then we will use data visualizations to share findings with the board.

Requirements

Preprocessing the Data for PCA
Reducing Data Dimensions Using PCA
Clustering Cryptocurrencies Using K-means
Visualizing Cryptocurrencies Results
Resources

Data Source: crypto_data.csv
Software: Jupyter Notebook
Languages: Python
Libraries: Scikit-learn, Pandas, Plotly
Results

To use unsupervised machine learning models on the data, the data needs to be processed to fit the machine learning models.

1: Preprocessing the Data

Before using data on unsupervised ML algorithms, the data needs to be preprocessed to avoid errors and to ensure that, we are getting the right results.
There are three steps to pre-process the data:
Data selection - We need to check on data availability, missing data, and what data can be removed,
Data processing - We need to organize the data by formatting, cleaning, sampling and
Data transformation - We need transform data into a simple format for storage and future use, such as a CSV, spreadsheet, or database file.
Requirements for dataset:

Null values and missing data:

Unsupervised learning models can't handle null values or missing data.
Drop null or missing values or decide and drop the entire column.
Datatype: All data has to be converted to numerical data type.

Duplicates: Remove duplicates, it may lead to errors.

Scaled values:

Data has been manipulated to ensure that the variance between the numbers won't skew results.
The unscaled value can lead to messy graphs.
It is important to understand when to scale and normalize data.
For example, if four columns of data are single digits, and the fifth column is in the millions, we would need to scale the fifth column to align the other four.
2: Reducing Data Dimensions Using PCA

Having too many features in the dataset when working with unsupervised ML can cause overfitting.

To avoid this, we can use process of reducing features also known as dimensionality reduction.

There are two options for coping with too many features:

Feature elimination It removes a good number of features, so the model won't be run using every column.

Feature extraction It combines all features into a new set that is ordered by how well they predict our original variable.

PCA

It is a statistical technique to speed up machine learning algorithms when the number of input features (or dimensions) is too high.

PCA reduces the number of dimensions by transforming a large set of variables into a smaller one that contains most of the information in the original large set.

The first step in PCA is to standardize these features by using the StandardScaler library.
After the data has been standardized use PCA to reduce the number of features (argument of n_components) to get a smaller set of dimensions called principal components.
These new components are new main dimensions of variation that contain most of the information in the original dataset.
explained_variance_ratio tells how much information can be attributed to each principal component.
For example, the first principal component contains 72.77% of the variance and the second contains 23.03%. Together, they contain 95.80% of the information.
3: Clustering Cryptocurrencies Using K-means and finding the Best Value using Elbow Curve

Clustering is a type of unsupervised learning that groups data points together.

K-means

It is an unsupervised learning algorithm used to identify and solve clustering issues.
K represents how many clusters there will be. These clusters are then determined by the means of all the points that will belong to the cluster.
The K-means algorithm groups the data into K clusters, where belonging to a cluster is based on some similarity or distance measure to a centroid.
The centroid is found by taking the mean of all the x values in a cluster, and the mean of all the y values in a cluster.
Elbow curve

It is an easy method for determining the best number for K-means.
To create the elbow curve, two values are needed
a list of K values and
a list of inertia values.
Loop through 10 values for K, for example and determine the inertia: range (1, 11).
Inertia

It is one of the most common objective functions to use when creating an elbow curve.
The inertia is measuring the amount of variation in the dataset.
Inertia is the objective function to plot K values against.
4: Visualizing Cryptocurrencies Results and Interpretation

Visualizing the clusters helps to graphically understand how they are arranged.

3D graph and PCA visualization

For 3D visualization we used 3D scatter plot with Plotly Express.
3 principal components (on x, y and z axis), that were created with PCA algorithm are plotted on the graph.
These 3 components contain most of the information in the original large set.
As we can see form the graph, cryptocurrency is clustered in 4 groups with similar characteristics.
When hover over the specific element the graph shows label with Coin Name and its Algorithm.


Figure 1: Cryptocurrencies clustered in 4 main groups.

2D visualization and correlation between Total Coins Supply and Total Coins Mined

For 2D visualization we used hvPlot - A graphing library that allows deeper exploration of the data.
This graph has Total Coins Supply on y-axis and Total Coins Mined on x-axis.
From the graph we can see correlation between those two components.
Different colors indicate different classes that crypto coins belong to.
When hover over the specific element the graph shows label with Coin Name and its Class.


Figure 2: Correlation between Total Coins Supply and Total Coins Mined.

Interactive Table

To create interactive table, we used hvplot library.
When clicked on the header, the values in that columns are sorted.
This interactive table is ideal to see what tradable coins are on the market,
Algorithms used and can be easily sorted by in ascending or descending order.


Figure 3: Interactive table of tradable crypto coins.
