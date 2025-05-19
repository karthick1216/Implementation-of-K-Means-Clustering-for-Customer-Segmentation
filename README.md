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

## Program:

```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KARTHICK S
RegisterNumber: 212224230114
```

```
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv('/content/Mall_Customers (1).csv')
data.head()
```
## Output:
![image](https://github.com/user-attachments/assets/a88324c4-8175-4c6c-a7f5-7d73c4a5b801)

```
data.info()
```
## Output:
![image](https://github.com/user-attachments/assets/dd05249f-7aa9-4fc2-be6a-cd23a830c17c)

```
data.isnull().sum()
```
## Output:
![image](https://github.com/user-attachments/assets/df75ed1d-efed-496b-8620-cbf7d80b9172)

```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)


plt.plot(range(1,11),wcss)
plt.title('The Elbow Method')
plt.xlabel('Number of clusters')
plt.ylabel('WCSS')
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/ef965bbd-9392-46b3-8ef5-2ff6a7102346)
```

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:]) 
y_pred
```
## Output:
![image](https://github.com/user-attachments/assets/7cb4c9a4-e064-4057-adfe-c38c6cf353a0)
```

data["clusters"]=y_pred
df0=data[data["clusters"]==0]
df1=data[data["clusters"]==1]
df2=data[data["clusters"]==2]
df3=data[data["clusters"]==3]
df4=data[data["clusters"]==4]


plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],color="red")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],color="blue")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],color="green")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],color="yellow")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],color="black")
```
## Output:
![image](https://github.com/user-attachments/assets/712b3861-4a92-4026-a6fd-4d9a24dd4935)

## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
