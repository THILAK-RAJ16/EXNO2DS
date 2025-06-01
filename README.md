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
Name:Thilak Raj . P
Register No.:212224040353
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```


```
df=pd.read_csv("/content/titanic_dataset (2).csv")
df
```
![image](https://github.com/user-attachments/assets/67026738-5f33-4c53-809b-43b745c57b9f)

```
df.info()
```
![image](https://github.com/user-attachments/assets/649136fe-2d1e-49c1-99cf-aec06c905747)

```
df.set_index("PassengerId",inplace=True)
df
```
![image](https://github.com/user-attachments/assets/44982d84-f5a5-425d-9453-e3e4b9579cf5)

```
df.shape
```
![image](https://github.com/user-attachments/assets/b17a0676-d6df-43fe-9862-0765ca8d18ab)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/c7755123-a8f7-46dd-8b6b-73e3d56c4936)

```
df.head(7)
```
![image](https://github.com/user-attachments/assets/db2a2d9a-21a4-48ce-b524-f198bdba1e22)

```
df.tail(6)
```
![image](https://github.com/user-attachments/assets/ebc21edb-f1df-4059-ad27-2d4c6fd17a69)

```
df.nunique()
```
![image](https://github.com/user-attachments/assets/57c3ea90-eada-4e22-be60-6ec6c9fba75e)

```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/405cb5fc-0fb9-47fa-8ee3-97c1f09a062e)


```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/115d08b5-6561-41bd-9ae4-17ff8bd88206)

```
sns.countplot(x="Survived",data=df)
```
![image](https://github.com/user-attachments/assets/f75de16b-817f-425c-aeb4-b6a463a6fcc9)

```
df
```
![image](https://github.com/user-attachments/assets/6b9204cf-7de0-478e-b2d4-4663b0735d72)

```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/79c25a24-f783-4016-8120-9221a40f7f24)

```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/93ecb7b7-a7a6-4808-9cde-b6fe1abb291b)

```
sns.catplot(x="Gender",col="Survived",data=df,kind="count",height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/14a18036-aa4a-409b-8ed0-0d705b44ebba)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/fc2729f4-5743-4506-a430-febca438eb4f)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/ca2bd3f4-079f-46ab-a0b4-0eb5da592167)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/e1015453-b8f0-46a3-8b33-12d85dbbb408)

```
sns.scatterplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/8d0d0e0e-53f1-43bf-aa86-bd7e30717b57)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/beb2a95a-34ec-452a-a632-2cb06b7dc8a2)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/2c0560ea-ca0a-495b-8658-afdf052c1094)

```
sns.catplot(col="Survived",x="Gender",hue="Pclass",kind="count",data=df)
```
![image](https://github.com/user-attachments/assets/a89746bb-c6d7-42c8-9f2d-2f58bd88b4b0)

```
data=df[['Survived','Pclass','Age','SibSp','Parch','Fare']]
```
![image](https://github.com/user-attachments/assets/4b47cebf-74b8-4acd-a0ed-bd9f8474c1cd)

```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/182ac1f8-e076-4cf0-9d2b-59bfdfce68e8)

# RESULT         
Thus Exploratory Data Analysis is performed on the given data set.
