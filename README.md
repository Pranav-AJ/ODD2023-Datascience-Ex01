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

df.shape


df.head()

df.tail()

df.describe()

df.info()

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
