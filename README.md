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
```
import pandas as pd
df=pd.read_csv('SAMPLEDS.csv')
df
```

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/52e96803-1f79-4540-a285-b2bf137a9ee1)

df.shape


![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/4dbac47e-39d3-41a9-bf26-85eba5bdb704)

df.head()

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/45b1a32f-7f7a-4c90-ad5d-b1562cf7627d)

df.tail()

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/8c6f8693-7f0f-4eb2-935e-97c181385ff2)

df.describe()

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/e00c1c52-e04f-438c-a54f-220a07e341c5)

df.info()

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/168785a2-6ca0-4a37-8f50-41802884ca3d)

df.isnull().sum(*)

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/39ead6cb-07b7-47ba-ae05-1a70fd028042)

n=df.dropna(how='any')

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/a13c7911-beb2-4982-be4e-f414ab0f3637)

n.shape

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/4f667381-dbed-45e3-8965-cf8232f8a4fe)

df.dropna(how="all")


![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/0558b941-ddc3-442a-a0bf-6361a697d205)
```
tot=df.dropna(subset=['TOTAL','M1','M2','M3','M4'],how='any')
print(tot)
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/57f986ef-a6c3-4fda-9e26-4c57296785f9)

df.fillna(0)

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/88a299a1-d0c3-46b2-b19d-d1cbe3293a1c)

df.fillna(method='ffill')

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/d8d9d773-f5b0-4e15-9ca7-932e2f8c12bd)

df.fillna(method='bfill')

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/83e7def0-09ce-4aba-bfb0-e9edfcf1e4dd)

df.interpolate()

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/e5b04fdc-3e4b-4dcd-a725-535c1fd7393b)
```
mn=df.TOTAL.mean()
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/625541ab-0785-4856-8869-3eef4606f559)

```
l=df.M1.interpolate()
df.M1.fillna(l,inplace=True)
df
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/285392a1-d36f-47d2-b3e4-3bdf3eed33c0)
```
med=df.M2.median()
med
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/68fd85e2-7224-4832-a517-1bc7e2f9967a)
```
df.M2.fillna(med,inplace=True)
df
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/b5da6799-ba73-4c3d-8f31-0130cc261dfd)
```
m=df.M3.mode()
m
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/427c52b8-636e-405f-afb4-77a263e582b2)

df.duplicated()


![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/5c345a49-d666-430d-8aa9-b73b184351a6)
```
df.drop_duplicates(inplace=True)
df
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/1fe722ef-a0e1-421b-83b8-a6ff4ed8f18f)
```
df['cd']=pd.to_datetime(df['DOB'])
df
```
![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/8b4a143c-973a-4e23-9f71-5a8dd23d6110)

```
for x in df.index:
  if df.loc[x,'AVG']>100:
    df.drop(x,inplace=True)
df
```

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/571a24f5-9579-4b90-ad98-11079b95998f)

df.drop(['DOB'],axis=1)

![image](https://github.com/Pranav-AJ/ODD2023-Datascience-Ex01/assets/118904526/fd47f179-664d-4ad2-a364-6081742223c3)


