# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset
2.check for null values
3.Import kmeans and fit it to the dataset
4.Plot the graph using elbow method
5.Print the predicted array
6.Plot the customer segments



## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:A.ARUVI. 
RegisterNumber: 212222230014. 
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
### 1.DATA.HEAD():
![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/68643141-4915-44dd-ba12-7895531199bb)

### 2.DATA.INF0():
![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/f10cd051-92cb-4bd6-81ea-08c1b363afb2)

### 3.DATA.ISNULL().SUM():

![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/7b1cef19-6779-45b2-a40e-58a431fa1da4)

### 4.PLOT USING ELBOW METHOD:

![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/96d5b3ca-8cd9-4a5d-89dd-997c2b46df3e)

### 5.K-MEANS CLUSTERING:

![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/4bab3c6f-30f2-4dbb-b92d-c2e96468fcfc)

### 6.Y_PRED ARRAY:

![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/1aee4148-221e-46ca-a85f-e3de49c29e9f)

### 7.CUSTOMER SEGMENT:

![image](https://github.com/Anandanaruvi/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/120443233/0fdd6f0c-0162-4919-af16-0dbfa53165f8)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
