# EXNO:2
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
REG NO: 212224110045
NAME: A PRANEYA
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

```
dt=pd.read_csv("/content/titanic_dataset (2).csv")
dt
```
![Screenshot 2025-04-18 103445](https://github.com/user-attachments/assets/7b1bf72f-6593-49f8-992b-c22e26536263)

```
dt.info()
```
![Screenshot 2025-04-18 103454](https://github.com/user-attachments/assets/6ffa37d3-c5fc-48a2-aa61-e2ba9e6e9fbd)

```
dt.shape
```
![Screenshot 2025-04-18 103501](https://github.com/user-attachments/assets/eb2c6898-fd07-4f23-9b14-36639ab4cd7d)

```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![Screenshot 2025-04-18 103507](https://github.com/user-attachments/assets/e9e86753-f04d-436d-9b97-ed4f52fb0141)

```
dt.nunique()
```
![Screenshot 2025-04-18 103514](https://github.com/user-attachments/assets/63022df6-2c3e-4f80-999e-e78e1922ba27)

```
dt["Survived"].value_counts()
```
![Screenshot 2025-04-18 103521](https://github.com/user-attachments/assets/546afeda-e784-49bb-a185-3ceb057c2a2e)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![Screenshot 2025-04-18 103527](https://github.com/user-attachments/assets/3c0233b5-2b5a-4bb9-8434-f16428c97460)

```
sns.countplot(data=dt,x="Survived")
```
![Screenshot 2025-04-18 103540](https://github.com/user-attachments/assets/9f08f2fb-d29a-4b62-97e0-b40882cd7bd8)

```
dt
```
![Screenshot 2025-04-18 103556](https://github.com/user-attachments/assets/e5e64276-02f4-4896-bbca-a4459abf8cc4)

```
dt.Pclass.unique()
```
![Screenshot 2025-04-18 103603](https://github.com/user-attachments/assets/1b83e9cc-7f10-4eeb-974a-fccb79a69ef2)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![Screenshot 2025-04-18 103619](https://github.com/user-attachments/assets/5189989c-079a-4a64-aada-34aaf79d22b1)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=0.7)
```
![Screenshot 2025-04-18 103634](https://github.com/user-attachments/assets/01902bf2-9d16-49ae-860e-ad6c0d16f18a)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![Screenshot 2025-04-18 103644](https://github.com/user-attachments/assets/6415a2e7-80c0-48cd-bbef-723bf60174dd)

```
dt.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-04-18 103652](https://github.com/user-attachments/assets/583bd0aa-c924-4538-a664-fdb6a4cac2e9)

```
sns.scatterplot(x=dt['Age'],y=dt['Fare'])
```
![Screenshot 2025-04-18 103701](https://github.com/user-attachments/assets/c1dc70a5-5d28-4066-9946-c760308f9d31)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![Screenshot 2025-04-18 103712](https://github.com/user-attachments/assets/0b6aca8b-3bbf-4062-bc75-4840e212c740)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![Screenshot 2025-04-18 103721](https://github.com/user-attachments/assets/f32fde9f-f2e8-4d5c-9bf4-6393cae467b1)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-04-18 103733](https://github.com/user-attachments/assets/718fb310-fc49-47bb-ad43-dba2a9164a6c)

```
numeric_features = dt.select_dtypes(include=np.number)
corr = numeric_features.corr()
sns.heatmap(corr, annot=True)
```
![Screenshot 2025-04-18 140831](https://github.com/user-attachments/assets/cbdce494-2ceb-447a-81bc-e1878bbce805)

```
sns.pairplot(dt)
```
![Screenshot 2025-04-18 103745](https://github.com/user-attachments/assets/0e9f7b74-de91-41ec-83c1-c51e13055ada)


# RESULT
Thus we have performed Exploratory Data Analysis on the given data set successfully.
