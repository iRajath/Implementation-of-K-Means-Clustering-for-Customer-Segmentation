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
Developed by: S Rajath
RegisterNumber:  212224240127
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



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
