# K-Means exercise: 
Amelia Herrera Briceño
melinnicri@gmail.com
November, 2023.

<p align="center"><img src="https://github.com/melinnicri/K-Means_exercise/blob/main/images/fake.png"></p>

## Purpose of the Data Science project: 
The purpose of counterfeit bill detection is to prevent the circulation of counterfeit bills, which can be used to commit fraud and other crimes. As for actual banknotes, data collection can help authorities identify patterns and trends in cash use, which can be useful for public policy formulation and decision-making.

The K-means algorithm is a cluster analysis (unsupervised learning) technique used to group similar observations into groups or clusters. The goal is to discover patterns and structures in the data that are not evident to the naked eye. The algorithm searches for a fixed number of clusters (encoding) in the data set and assigns each observation to the closest cluster. The technique is used in a variety of fields, such as data mining, bioinformatics, image classification and customer segmentation, in this case, from counterfeit bills.

Data description (data found in ["Nuevo_Billete.ipynb"](https://github.com/melinnicri/K-Means_exercise/blob/main/Nuevo_Billete_again.ipynb) and [DB](https://github.com/melinnicri/K-Means_exercise/blob/main/Backnotes.csv) attached): A general statistical description before applying standardization or the K-Means model: V1, variance of the transformed images and V2, skewness of the transformed images, we have 1372 data each, with a mean of V1, 0.433 ± 2.842 and V2, 1.922 ± 5.869 (± is standard deviation of the mean of V1, and V2, this means, how far are the data from the mean, V2 is move twice as far away from V1). 75% of the data (are less than these values), V2 (6,814) is double V1 (2,821). The minimum for V1 is -7.042 and for V2 is -13.773; the maximum for V1 is 6,824 and for V2 is 12,951.

## Methods: 
How was the data analyzed? The data were first standardized and cleaned (ETL) before applying K-Means model (EDA; unsupervised classification), so the new statistical description is as follows:

<p align="center"><img src="https://github.com/melinnicri/K-Means_exercise/blob/main/images/Columns.png"></p>

The elbow in the K-means algorithm refers to the technique used to determine the optimal number of clusters. The elbow rule involves plotting the sum of squared errors (SSE) as a function of the number of clusters. SSE is a measure of the quality of clusters. The lower the SSE, the better the clustering. The graph will look like a downward curve that resembles an arm with an elbow. The point at which the curve begins to flatten is called the elbow. This point indicates the optimal number of clusters for the K-means model, as shown below in the following graph:


<p align="center"><img src="https://github.com/melinnicri/K-Means_exercise/blob/main/images/Encoding.png"/>
  <br/> **Graph number 1: Number of clusters (k=2).** {: style="font-size: 80%; text-align: center;"} </span></p>


Based on the Graph number 1, it appears that the optimal value of k is 2. However, it is important to note that the optimal value of k can vary depending on the data set and the specific problem you are trying to solve. Therefore, it is a good idea to experiment with different values of k and evaluate the results to determine the best value for your specific use case.

In other words, the model is significant and the predictor variables have a significant effect on the clusters in 2 clusters (the smallest variability distance in this grouping wins).

The variance decreases for two clusters (variability is less), so we choose to keep 2 clusters instead of 3 clusters (graphics not shown).
Summary of results:
Variance of each group:
Cluster 0, Column V1: 0.410; Column V2: 0.231;
Cluster 1, Column V1: 0.436; Column V2: 0.593.
Mean of the variances:
Column V1 (both clusters, 0 and 1): 0.320;
Column V2 (both clusters): 0.514.
Combined variance:
Column V1 (both clusters, 0 and 1): 244.768;
Column V2 (both clusters, 0 and 1): 260.271.
Sum of squares between groups: 8.022.
Sum of squares within the groups: 1558.290.
F-statistic: 7.052, p-value: 0.008.
Mean of each group (± standard deviation):
Cluster 0, Column V1: -0.850 ± 0.641; Column V2: -0.631 ± 0.901;
Cluster 1, Column V1: 0.655 ± 0.683; Column V2: 0.486 ± 0.776.
T-statistic: -1.084e-15, p-value: 0.999.

Graph number 2: k=2, the two final groups.

Therefore, there are two columns of data (approximately 1300 data) about images of fake and real banknotes, the model used to know well about images as distinction patterns is KMeans, which groups the data by similarity (the means are marked with a cross and the data are close to this mean) and this is how we obtain two groupings well defined (Graph number 2), which can then be extrapolated for new data. Through the F and p Test, the model is significant and the predictor variables have a significant effect on the clusters. ..._@v
