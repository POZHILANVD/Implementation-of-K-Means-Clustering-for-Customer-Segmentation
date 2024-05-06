# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import pandas and matplot libraries.

2.import Kmeans algorithm to solve customer segmentation.

3.Using the for loop cluster the given data

4.Predict the output and plot data graphs.

5.Display the outputs
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 
RegisterNumber:  
*/

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```

## Output:
#### 1.DATA.HEAD():
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/d35b4a6b-9a0b-477d-864d-c7bdb68fa854)
#### 2.DATA.INF0():
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/74112410-0e34-43af-a090-b66b320aed5d)
#### 3.DATA.ISNULL().SUM():
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/61bdfd0e-0b72-43b9-8a0d-f98abb522a31)
#### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/8421bc24-c20e-443e-8435-7c666f191eef)
#### 5.K-MEANS CLUSTERING:
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/f655ce4c-9ea7-4b86-9c38-a1b865ea4dd1)
#### 6.Y_PRED ARRAY:
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/9579fb20-5a35-4184-9137-6a20b5f10a74)
#### 7.CUSTOMER SEGMENT:
![image](https://github.com/POZHILANVD/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/144870498/cb29fade-eab7-42c4-9dc1-5b9c8c4b449d)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
