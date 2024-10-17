# EX8-Implementation of Hierarchical Clustering using linkage methods
## DATE:
## AIM:
To implement Hierarchical Clustering using single and complete linkage method

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
step 1 : Ensure your data is organized properly. Each row represents a data point, and each column represents a feature.

step2: Use one of the linkage methods (e.g., single, complete, average, or ward) to calculate the distance between clusters and generate the linkage matrix.

step3: A dendrogram helps visualize the hierarchical structure and merge process of clusters.

step4 : Decide the number of clusters by cutting the dendrogram at a certain height or by specifying a maximum distance. This step gives the final cluster assignments.

## Program:
```
/*
Program to implement Hierarchical Clustering using single and complete linkage method
Developed by: MADHANKUMAR J
RegisterNumber:  2305001016
*/
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage, fcluster # Changed 'dendogram' to 'dendrogram'
from sklearn.preprocessing import StandardScaler

df=pd.read_csv('/content/Hclus_EX8.csv')
df.head()

X=df[['StudentID','Marks']].values
X


#Perform hierarchical clustering (agglomerative)
Z=linkage(X, method='complete')

#Plot dendogram
plt.figure(figsize=(5,2))
plt.title("Dendogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()

#Cut the dendrogram to form clusters(let's say we want 5 clusters)
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters

#Scatter plot with different colors for each cluster
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()


Z=linkage(X, method='single')

#Plot dendogram
plt.figure(figsize=(5,2))
plt.title("Dendogram for Student Segmentation")
labels=range(1,len(df)+1)
dendrogram(Z,labels=labels)
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()


#Cut the dendrogram to form clusters(let's say we want 5 clusters)
max_clusters=2
clusters=fcluster(Z,max_clusters,criterion='maxclust')
clusters


#Scatter plot with different colors for each cluster
plt.figure(figsize=(5,2))
plt.scatter(X[:,0],X[:,1],c=clusters,cmap='rainbow',s=100)
plt.title("Student segmented (Hierarchical Clustering)")
plt.xlabel("Student ID")
plt.ylabel("Marks")
plt.show()

```

## Output:

![image](https://github.com/user-attachments/assets/2846c337-7c82-4d6d-b5f9-8885f9966280)

![image](https://github.com/user-attachments/assets/5a036a3e-339c-471e-8682-356c1f8b5bb4)

![image](https://github.com/user-attachments/assets/61abe137-3978-470f-8ae9-934bbce9c366)

![image](https://github.com/user-attachments/assets/22e71f01-9d04-44e7-ab36-a5f4ff8a9bc7)

![image](https://github.com/user-attachments/assets/257e5f42-b14a-4fb1-9495-54bd0d9a63b7)

![image](https://github.com/user-attachments/assets/9f147aa9-cb60-4172-818d-98b2f9cc0927)

![image](https://github.com/user-attachments/assets/321f124e-15d1-4d76-bc83-87c6e9d1e4d0)

![image](https://github.com/user-attachments/assets/41fa7a46-77fc-4636-b3c1-655955ce3f41)









## Result:
Thus the implementation of Hierarchical Clustering using single and complete linkage method in python programming and verified successfully.
