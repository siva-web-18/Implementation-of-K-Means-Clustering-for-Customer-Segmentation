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
Developed by: Siva R
RegisterNumber:  212225100050
*/
```
```

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
![K Means Clustering for Customer Segmentation](sam.png)
<img width="647" height="221" alt="image" src="https://github.com/user-attachments/assets/60d59ec4-fe1f-4ab9-a0c7-7e6d1544f95c" />
<img width="620" height="272" alt="image" src="https://github.com/user-attachments/assets/64e44625-eaa1-4ad6-8fae-e3aae2657f1b" />
<img width="467" height="149" alt="image" src="https://github.com/user-attachments/assets/b234b51f-863b-4761-9223-91964b4151e6" />
<img width="897" height="614" alt="image" src="https://github.com/user-attachments/assets/5bff4010-d263-4077-b441-5ad087d8d5eb" />
<img width="385" height="146" alt="image" src="https://github.com/user-attachments/assets/fc034a34-611e-4330-9053-309b793bbd95" />
<img width="880" height="237" alt="image" src="https://github.com/user-attachments/assets/cbadf8f5-da3e-4c43-8a1f-c892769c9237" />
<img width="939" height="592" alt="image" src="https://github.com/user-attachments/assets/ea7fe615-5fab-4891-aeaf-e357a754edf8" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
