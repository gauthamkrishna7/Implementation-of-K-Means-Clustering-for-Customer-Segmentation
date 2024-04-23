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
Developed by: HIRUTHIK SUDHAKAR
RegisterNumber:  212223240054
*/
```
```python

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
![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/1af1baf8-ff03-4418-8954-d016511424a5)


### 2.DATA.INF0():
![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/8aea2495-1396-48a5-8c82-1e370c2f1ac0)


### 3.DATA.ISNULL().SUM():

![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/c2d37c17-6599-4fe7-bda8-1aa62751cd38)


### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/082a0349-0b0a-4b5d-a216-84b730ada6dc)


### 5.K-MEANS CLUSTERING:
![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/ca848331-3981-42e6-a228-2bf605ea646b)

### 6.Y_PRED ARRAY:
![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/2d12beab-4254-4295-8331-f41137f9583e)






### 7.CUSTOMER SEGMENT:

![image](https://github.com/HIRU-VIRU/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145972122/feee15df-c7a4-414e-8f76-3ea295d2c6a4)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
