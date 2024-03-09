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
NAME : HARSHINI S
REG NO : 212221220018

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/c1fa92e2-66a2-47bb-aa7e-0fb839877d5b)

dt.info()

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/1de09be5-b343-471d-bcfb-0fd0766c2ae9)

dt.shape

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/022f6738-7adb-4371-bc45-db4ecfa9af11)

dt.set_index("PassengerId",inplace=True)
dt.describe()

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/d2fa91b3-e3ad-4481-b150-3ad6441d0148)

dt.nunique()

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/0acaaf75-55f9-4e2b-8754-0e15a883f699)

dt["Survived"].value_counts()

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/1038fffc-06a3-479b-b9d0-f81c09cb51b0)

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/861d3528-10db-4d8b-9121-8d613f07b583)

sns.countplot(data=dt,x="Survived")

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/f01fd2a0-cc50-45d3-86e7-a3d0b08ff449)

dt.Pclass.unique()

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/cec8ce9a-5574-4a54-939d-259213f3a430)

dt.rename(columns = {'Sex':'Gender'},inplace=True)
dt

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/500f8437-929d-42b8-bcdc-34cde6165171)

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/1dac0f88-98ed-4c39-9315-16c6d08b7c6d)

sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/a8ded582-54aa-4eb4-b1d0-1b0e0a3fc152)

dt.boxplot(column="Age",by="Survived")

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/2ef251a9-8ebb-4d75-9688-812eb04ba4fc)

sns.scatterplot(x=dt["Age"],y=dt["Fare"])

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/1d0a4dca-7b4c-4e32-85c4-a511330e82cb)

sns.jointplot(x="Age",y="Fare",data=dt)

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/05d5bcf1-835b-413e-8923-9e09a5491a24)

fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/0f1de385-20ec-4291-8f1d-9a78fc7bdd2f)

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/f2f935ce-e020-4f02-b16c-02a61b199ee3)

corr = dt.corr()
sns.heatmap(corr,annot=True)

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/5310c9d5-49fa-4277-8a23-486f4ca2f639)

sns.pairplot(dt)

![image](https://github.com/Harshinisrini1910/EXNO2DS/assets/161415847/8847dc4d-f08a-4979-a97f-0f1d1d6b5ffd)

# RESULT
Thus the Exploratory Data Analysis process is performed successfully on the given data using python code.


