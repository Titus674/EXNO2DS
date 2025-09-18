### Name: Titus Ratna Kumar Karivella 
### RegNo: 212224230292

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
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```

<img width="1399" height="795" alt="image" src="https://github.com/user-attachments/assets/328d6184-eb51-4eec-b7b2-6e745b37d29c" />

```
df.info()
```
<img width="985" height="480" alt="image" src="https://github.com/user-attachments/assets/618ce233-cf04-45be-9d34-c3d912e6bfa1" />


```
df.descripe()
```

<img width="1076" height="423" alt="image" src="https://github.com/user-attachments/assets/8b0f8d12-0187-4e87-91f8-9a43c52dc19e" />


```
df.dtypes
```


<img width="985" height="621" alt="image" src="https://github.com/user-attachments/assets/4804dc66-caa0-4841-bd6f-2ee0ad36673f" />


```
df.shape
```
<img width="1137" height="98" alt="image" src="https://github.com/user-attachments/assets/95796b84-c25b-4245-8e48-3decdfe23755" />

```
df.value_counts()
```

<img width="1390" height="773" alt="image" src="https://github.com/user-attachments/assets/e5131ff8-da76-47b6-91fe-7ce0c2553c52" />


```
df['Age'].value_counts()
```
<img width="1243" height="659" alt="image" src="https://github.com/user-attachments/assets/047bcd59-b330-4612-b9ad-c14345bdbf72" />


```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1416" height="711" alt="image" src="https://github.com/user-attachments/assets/d52e8d99-a082-4717-9c3e-3d86697b25c8" />


```
df.nunique()
```

<img width="1202" height="577" alt="image" src="https://github.com/user-attachments/assets/828050d4-5943-4d81-b336-a321437323f2" />


```
sns.countplot(data=df,x='Survived')
```

<img width="1174" height="633" alt="image" src="https://github.com/user-attachments/assets/8e954754-492f-4b88-856e-65c58a7f618b" />


```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1393" height="725" alt="image" src="https://github.com/user-attachments/assets/eee1bcf8-e0ba-4812-82fa-f08602e5cc62" />


```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="1418" height="699" alt="image" src="https://github.com/user-attachments/assets/d971ca56-b441-4a7f-88eb-e49968b42ea8" />


```
df.boxplot(column="Age",by="Survived")
```

<img width="1291" height="663" alt="image" src="https://github.com/user-attachments/assets/16d00205-5db4-4caf-a9f9-a15a1582ef16" />


```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="1249" height="639" alt="image" src="https://github.com/user-attachments/assets/fd0e63db-4ff3-428f-b6e2-a3caffd3753f" />


```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="1257" height="660" alt="image" src="https://github.com/user-attachments/assets/17e5e302-e629-4da5-9b04-23cf3c60c0fe" />


```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="1258" height="616" alt="image" src="https://github.com/user-attachments/assets/44aee8de-1736-4d3d-aeb3-5ba0c36f1daf" />


```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```

<img width="1398" height="713" alt="image" src="https://github.com/user-attachments/assets/d83b27bf-3ce0-45e9-92fa-9b538a1419cf" />


```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```

<img width="1397" height="704" alt="image" src="https://github.com/user-attachments/assets/53fbc9e0-b12b-480a-b2ae-653d66281053" />


```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="1418" height="655" alt="image" src="https://github.com/user-attachments/assets/f18d0336-4a9b-49fe-9b35-cee61611d82f" />


```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

<img width="1370" height="628" alt="image" src="https://github.com/user-attachments/assets/a0608474-6b02-4d9f-908a-e0d40d8f9471" />


        
# RESULT

   Thus the data analysis has been implemented succesfully.
