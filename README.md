# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program 

## Program:
```

/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: S.ROSELIN MARY JOVITA
RegisterNumber: 212222230122
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/Mall_Customers (1).csv")

data.info()

data.head()

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

km =  KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"]= y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c ="purple",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c ="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c ="LightBlue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c ="Maroon",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c ="pink",label="cluster4")
plt.legend()
plt.title("CUSTOMER SEGMENTS")

```

## Output:

### data.head()

![Screenshot 2023-10-31 090135](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/fb696524-2830-487d-8d20-61d8494b6c77)

### data.info()

![Screenshot 2023-10-31 091107](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/2622fa37-5331-4822-a95b-9d6e537f7dec)

### data.isnull.sum() function

![Screenshot 2023-10-31 090537](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/90d57385-9931-4fda-a358-8f67c7902129)

### Elbow method graph

![Screenshot 2023-10-31 090553](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/f8411f76-bdc1-46a0-9f27-9dcada6dc922)

### K-Means cluster

![Screenshot 2023-10-31 090630](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/5eee3fc8-c1b4-490e-ab41-9ce0a8f3358d)

### Y_prediction

![Screenshot 2023-10-31 090650](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/12fbd14b-fcc2-4434-9ab9-af51cbb8817d)

### customer segments graph

![Screenshot 2023-10-31 090701](https://github.com/Roselinjovita/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119104296/7eb11e6a-bbb9-4827-9068-c63e9b1c39dc)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
