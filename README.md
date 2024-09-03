# EXNO2DS
# AIM:
  To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT

```
import pandas as pd
df=pd.read_csv('/content/titanic_dataset.csv')
df
```
![image](https://github.com/user-attachments/assets/3fc8c2b7-f2ec-485a-ad5f-5a388467aef4)
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/4bdc45c2-469e-4ce7-946c-37c5a94db330)
```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/d452b5f5-7dfd-46e4-a3f6-87d8242a7ded)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/7cfafa01-d198-4ad9-ab7f-e3382f997480)
```
df.info()
```
![image](https://github.com/user-attachments/assets/4e72bf0f-9121-4e5a-bd29-b80ee2707926)
```
df.shape
```
![image](https://github.com/user-attachments/assets/be7071cf-c11a-4c1a-9b1b-e81524ef7c7b)
```
df.set_index("PassengerId",inplace=True)
df
```
![image](https://github.com/user-attachments/assets/c3059a8d-a60e-432f-8896-72f4c9c671e7)

## CATEGORICAL DATA ANALYSIS
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/df235ddd-a9e7-440b-9a42-de9d85bc1fa3)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/c94f788a-1ccf-41fa-8aea-3c867bce3ce0)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/8f784a26-566d-4374-8861-c3a0f5d486bc)
```
import matplotlib.pyplot as plt
import seaborn as sns
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/96f77cbb-2280-40f3-9c1f-b6874289111c)
```
df
```
![image](https://github.com/user-attachments/assets/63e55354-234b-4db9-ad98-fec5df696a4d)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/48188e4a-a8c2-41fb-a68d-9f62bafc628c)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/0c371f21-c55c-4198-922c-67d9cc79219b)
```
sns.catplot(x='Survived',hue='Gender',data=df,kind='count')
```
![image](https://github.com/user-attachments/assets/24724709-fa51-4298-8cfc-34399b2395ac)
```
sns.catplot(data=df,col='Survived',x='Gender',hue='Pclass',kind='count')
```
![image](https://github.com/user-attachments/assets/8373d0da-9135-4e68-a9bf-127e21c3d517)

## RESULT
       This process helps in effective data cleaning, outlier detection, and exploratory data analysis (EDA).
 
