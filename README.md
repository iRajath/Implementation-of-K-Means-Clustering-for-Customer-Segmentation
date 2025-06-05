# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. **Import** the necessary libraries (`pandas`, `matplotlib`, `sklearn.cluster`).
2. **Load** the dataset using `pandas.read_csv()`.
3. **Display** dataset info and check for null values using `info()` and `isnull().sum()`.
4. **Select** appropriate features for clustering (e.g., Annual Income and Spending Score).
5. **Initialize** an empty list to store WCSS (Within-Cluster Sum of Squares).
6. **Loop** through cluster values (1 to 10):
    - Fit K-Means for each `k`
    - Store WCSS using `.inertia_`
7. **Plot** the Elbow Method graph using `matplotlib.pyplot`.
8. **Determine** the optimal number of clusters by observing the "elbow point" on the graph.


## Program:
```py
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Abishek Priyan M 
RegisterNumber:  212224240004
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data

data.info()

data.isnull().sum()

for i in range(1,11):
    Kmeans=KMeans(n_clusters=i,init="k-means++")
    Kmeans.fit(data.iloc[:,3:])
    wcss.append(Kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
plt.show()
y_pred = km.predict(data.iloc[:, 3:])
print(y_pred)

data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c = "red", label = "cluster0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c = "black", label = "cluster1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c = "blue", label = "cluster2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c = "green", label = "cluster3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c = "magenta", label = "cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### Preview of Dataset
![image](https://github.com/user-attachments/assets/6dfeb43c-c02f-4506-8e86-86607758d0f4)

### data.info()
  ![image](https://github.com/user-attachments/assets/c5d73bf4-3935-4fed-9a46-683640d68d6c)

### data.isnull().sum()
![image](https://github.com/user-attachments/assets/2f297d3d-0639-4166-8133-b26afdc6cabe)

### Graph
![image](https://github.com/user-attachments/assets/cc3abfa2-10ab-4617-9e11-998402f6c8d5)

### Y-prediction
![image](https://github.com/user-attachments/assets/658d5ded-7764-4aee-b22e-1c72b547ad4d)

### Customer Segments
![image](https://github.com/user-attachments/assets/db53fe17-261f-4fcd-824a-0f2df628ab9c)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
