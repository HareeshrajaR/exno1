# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
 ```
```
df.head()
```
```
df.tail()
```
```
df.isnull()
```
```
df.notnull()
```
```
df.fillna(55)
```
```
df.dropna()
```
```
df.isnull().sum()
```
```
df.isnull().any()
```
```
df.dropna()
```
```
df.fillna(0)
```
```
df.fillna(method = 'ffill')
```
```
df.fillna(method = 'bfill')
```
```
df_dropped = df.dropna()
df_dropped
```
```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
```
df.fillna({'GENDER':'MALE','NAME':'HARI','ADDRESS':'CHENNAI','M4':'87.0'})
```
```
iris=pd.read_csv('/content/iris.csv')
iris
```
```
iris.info()
```
```
iris.describe()
```

```
iris.shape
```
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=iris)
```
```
iris.isnull().sum()
```
```
q1=iris.sepal_width.quantile(0.25)
q3=iris.sepal_width.quantile(0.75)
iqr=q3-q1
iqr
```
```
rid=iris[((iris.sepal_width<(q1-1.5*iqr))|(iris.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
```
rid=iris[~((iris.sepal_width<(q1-1.5*iqr))|(iris.sepal_width>(q3+1.5*iqr)))]
rid
```
```
rid=iris[((iris.sepal_width>(q1-1.5*iqr))&(iris.sepal_width<(q3+1.5*iqr)))]
rid
```
```
sns.boxplot(x='sepal_width',data=rid)
```
```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(iris['sepal_width']))
z
```
```
iris=iris[(z<3)]
iris
```
# Result
          <<include your Result here>>
