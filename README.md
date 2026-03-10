# BLENDED LEARNING
# Implementation of Principal Component Analysis (PCA) for Dimensionality Reduction on Energy Data

## AIM:
To implement Principal Component Analysis (PCA) to reduce the dimensionality of the energy data.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import Libraries: Load pandas, sklearn, matplotlib, and seaborn for data handling and plotting.
2. Load Data: Read the dataset from HeightsWeights.csv into a DataFrame.
3. Data Inspection: Use .head() to verify the dataset structure and column names.
4. Feature Selection: Extract 'Height' and 'Weight' columns for the analysis.
5. Pre-Visualization: Create a scatter plot to show the raw data distribution.
6. Standardization: Scale the features using StandardScaler to ensure zero mean and unit variance.
7. PCA Initialization: Set up the PCA model with 2 principal components.
8. Fit & Transform: Apply PCA to the scaled data to reduce its dimensionality.
9. Variance Analysis: Check the explained_variance_ratio_ to see the impact of each component.
10. Post-Visualization: Plot the resulting Principal Components (PC1 vs PC2) to visualize the reduced data.

## Program:
```
/*
Program to implement Principal Component Analysis (PCA) for dimensionality reduction on the energy data.
Developed by: Sanjeev Kumar K
RegisterNumber:  25012334

import pandas as pd
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
import matplotlib.pyplot as plt
import seaborn as sns
data=pd.read_csv("HeightsWeights.csv")
print("First 5 rows of the dataset:")
print(data.head())
x = data[['Height(Inches)','Weight(Pounds)']]
plt.figure(figsize=(6,5))
sns.scatterplot(x='Height(Inches)',y='Weight(Pounds)',data=data)
plt.title("Original Data Distribution")
plt.show()
scaler = StandardScaler()
x_scaled =  scaler.fit_transform(x)
pca = PCA(n_components=2)
x_pca = pca.fit_transform(x_scaled)
print("Explained Variance Ratio:",pca.explained_variance_ratio_)
pca_df = pd.DataFrame(x_pca,columns=['PC1','PC2'])
plt.figure(figsize=(6,5))
sns.scatterplot(x='PC1',y='PC2',data=pca_df)
plt.title("PCA Projection of Height and Weight")
plt.xlabel("Principal Component 1")
plt.ylabel("Principal Component 2")
plt.show()

*/
```

## Output:
![alt text](<Screenshot 2026-03-10 224059.png>) 
![alt text](<Screenshot 2026-03-10 224108.png>) 
![alt text](<Screenshot 2026-03-10 224119.png>)

## Result:
Thus, Principal Component Analysis (PCA) was successfully implemented to reduce the dimensionality of the energy dataset.
