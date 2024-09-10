# EXNO2DS
# NAME: HAMZA FAROOQUE
# REG.NO: 212223040054
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

## CODING AND OUTPUT:
```
import pandas as pd
df= pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/af4a5e71-49c4-45bc-9a32-b860a674789a)
```
df.info()
```

![image](https://github.com/user-attachments/assets/f628b22c-b2ae-41d4-a6f4-4db38467a5bd)

```
df.set_index("PassengerId",inplace=True) df.describe()
```

![image](https://github.com/user-attachments/assets/d05c3e62-e2b0-42a8-a077-2fce29932353)
```
df.nunique()
```

![image](https://github.com/user-attachments/assets/3237f89f-bc91-46cf-b7e5-fd03e3aa028b)
```
per=(df['Survived'].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/d0b227f8-eebe-47de-a826-459cf8478734)
```
sns.countplot(x='Survived',data=df)
```

![image](https://github.com/user-attachments/assets/861ffb48-109d-46a7-8b03-f7fe0e9620ee)
```
sns.countplot(x='Sex',data=df)
```

![image](https://github.com/user-attachments/assets/fd5fdacf-7a57-4007-8732-84c523983780)
 ```
df
```

![image](https://github.com/user-attachments/assets/1ea18637-7b0b-4f23-9985-152059941917)
```
df.Pclass.unique()
Output: array([1, 3, 2])
```
```
df.rename(columns={'Sex':'Gender'},inplace=True)
```

![image](https://github.com/user-attachments/assets/1ab3c305-6843-4b3c-8b8c-71a4c259b7f8)
  
```
sns.catplot(x='Gender',col='Survived',data=df,kind='count',height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/88e3cdb0-523b-4768-90da-33cce7adf7e9)
```
sns.catplot(x='Survived',hue='Gender',data=df,kind='count')
```

![image](https://github.com/user-attachments/assets/a360c1d5-0392-4675-b4c3-d7bc5964d2b6)
```
df.boxplot(column='Age',by='Survived')
```

![image](https://github.com/user-attachments/assets/7b53fc52-3bbf-4386-829b-9af4918763e4)
```
sns.scatterplot(x='Age',y='Fare',data=df)
```

![image](https://github.com/user-attachments/assets/17a8067c-1d4c-4f64-8aea-16d3693f3936)
```
sns.jointplot(x='Age',y='Fare',data=df)
#
```

![image](https://github.com/user-attachments/assets/50314a1d-bf45-4eac-8f1c-c9ad1445397b)
```
fig,ax1= plt.subplots(figsize=(8,5))
sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df,ax=ax1)
```

![image](https://github.com/user-attachments/assets/483df819-cc50-4b5b-885c-4bf70db888cf)
```
sns.catplot(x='Gender',col='Survived',hue='Pclass',data=df,kind='count')
```

![image](https://github.com/user-attachments/assets/ea0439f1-03d3-4dc6-938c-8ee5589477a1)
```
ndf = df.select_dtypes(include=['number'])
cr= ndf.corr()
sns.heatmap(cr, annot=True)
```

![image](https://github.com/user-attachments/assets/561452f1-6717-4366-bdc7-fe28ecf27f66)
```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/5416da2c-df72-49ec-8517-77e34b1fe8b2)

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
