# Ex-01_DS_Data_Cleansing
### Date:
## AIM:
To read the given data and perform data cleaning and save the cleaned data to a file. 

## Explanation:
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

## ALGORITHM:
### STEP 1:
Read the given Data.
### STEP 2:
Get the information about the data.
### STEP 3:
Remove the null values from the data.
### STEP 4:
Save the Clean data to the file.

## CODE: 
```python
import numpy as np
import pandas as pd
df=pd.read_csv("/content/Data_set.csv")
df
df.head(10)
df.info()
df.isnull()
df.isnull().sum()
df['show_name']=df['show_name'].fillna(df['aired_on'].mode()[0])
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['aired_on'].mode()[0])
df.head()

df['rating']=df['rating'].fillna(df['rating'].mean())
df['current_overall_rank']=df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df.head()

df['watchers']=df['watchers'].fillna(df['watchers'].median())
df.head()

df.info()
df.isnull().sum()
```
## OUTPUT:
### NON NULL BEFORE:
![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex01/assets/94164665/c629dc29-3212-47ac-91a9-1b6a1bfe5952)
### MODE:
![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex01/assets/94164665/830d648d-a080-4f21-9cd6-4e1983f08e60)

### MEAN:
![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex01/assets/94164665/0c0f21df-6c30-46ec-a164-037e193f616c)

### MEDIAN:
![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex01/assets/94164665/8c84cc0d-d5d6-4c15-b251-3702a25b8cfd)

### NON NULL AFTER:
![image](https://github.com/NITHISH74/ODD2023-Datascience-Ex01/assets/94164665/d86cfa65-49c2-4b61-9f9c-a1087da370e1)

## RESULT:
Thus,the given data is read, cleaned and the cleaned data is saved into the file successfully.
