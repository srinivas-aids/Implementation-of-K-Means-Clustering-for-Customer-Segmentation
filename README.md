# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import the necessary packages using import statement.
2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3.Import KMeans and use for loop to cluster the data.
4.Predict the cluster and plot data graphs.
5.Print the outputs and end the program
## Program:
~~~
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: u.srinivas
RegisterNumber:  212221230108
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head(
data.info())
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
*/
```
~~~

## Output:
##DATA HEAD:

![1](https://user-images.githubusercontent.com/93427183/173176309-ba7abc3f-1932-43c6-8976-28a4c571fed9.png)


##DATA INFO:

![2](https://user-images.githubusercontent.com/93427183/173176312-2d7a8099-3648-439f-9efc-32893e1d0277.png)

##NULL SUM:


![3](https://user-images.githubusercontent.com/93427183/173176315-284518aa-6c2b-4ccf-b52c-8a7eb748d52d.png)


##PLOT-ELBOW METHOS:



![4](https://user-images.githubusercontent.com/93427183/173176316-d30f3dfb-545f-4f08-a7b9-9701b29583eb.png)

CLUSTER:


![5](https://user-images.githubusercontent.com/93427183/173176320-bd0f594c-0e37-4b39-8465-267b7d1dd18b.png)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
