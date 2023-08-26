# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE and OUTPUT

import pandas as pd

df=pd.read_csv('SAMPLEDS.csv')
df


![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/52e96803-1f79-4540-a285-b2bf137a9ee1)

df.shape


![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/4dbac47e-39d3-41a9-bf26-85eba5bdb704)

df.head()

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/45b1a32f-7f7a-4c90-ad5d-b1562cf7627d)

df.tail()



df.describe()

 ![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/e00c1c52-e04f-438c-a54f-220a07e341c5)

df.info()
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/955afe63-cdc5-4806-ba3c-0c3da0add215)

df.isnull().sum(*)

df.dropna(how='any')


n=df.dropna(how='any')
n.shape

df.dropna(how="all")#if all the values in rows are null

tot=df.dropna(subset=['TOTAL','M1','M2','M3','M4'],how='any')
tot

df.fillna(0)

df


df.fillna(method='ffill')

df.fillna(method='bfill')

df.interpolate()

mn=df.TOTAL.mean()
mn
df.TOTAL.fillna(mn,inplace=True)
df

l=df.M1.interpolate()
l
df.M1.fillna(l,inplace=True)


df

med=df.M2.median()
med

df.M2.fillna(med,inplace=True)
df

m=df.M3.mode()
m

df.M3.fillna(m,inplace=True)
df

n=df.M4.mode()
n

s=df.M4.fillna(n,inplace=True)


df

df.duplicated()

df.drop_duplicates(inplace=True)
df

df['cd']=pd.to_datetime(df['DOB'])
df

for x in df.index:
  if df.loc[x,'AVG']>100:
    df.drop(x,inplace=True)
df

df.drop(['DOB'],axis=1)

