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
Developed by: GAUTHAM KRISHNA S
RegisterNumber:  212223240036
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
![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/4d9e425c-cc17-4c6b-a39a-aa2bb0e752cb)



### 2.DATA.INF0():
![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/6cbcd431-e331-4f20-bd4b-29589920fba8)


### 3.DATA.ISNULL().SUM():

![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/36f6c6e5-9b76-466e-b4e6-2551ef5c7577)



### 4.PLOT USING ELBOW METHOD:
![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/7d7d4b7c-3d84-4d97-b125-5feec3069372)



### 5.K-MEANS CLUSTERING:
![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/5529b341-0574-4b1c-95ae-a695fda3bca8)



### 6.Y_PRED ARRAY:
![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/3215ec0e-5c5d-4ca5-ad05-534966f6b8da)


### 7.CUSTOMER SEGMENT:

![image](https://github.com/gauthamkrishna7/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/141175025/b212a326-178e-4816-b3b7-de6a4362e6ec)





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
