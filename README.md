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
REGISTER NO:212224230044
NAME: CHARUKESH S
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("drive/MyDrive/heights.csv")
print(df)
```
![image](https://github.com/user-attachments/assets/e4c16790-5456-42b8-885d-37b9747379d0)
```
pd.DataFrame(df)
```
![image](https://github.com/user-attachments/assets/6e16ac9d-c13e-4269-a115-fdcbd14352da)
```
sns.boxplot(data=df)
```
![image](https://github.com/user-attachments/assets/a6ecc828-17c1-476b-a0da-143c5a8010ba)
```
sns.scatterplot(data=df)
```
![image](https://github.com/user-attachments/assets/56090097-5ee0-43e3-91b5-b4222d6156fb)

```
q1=df['height'].quantile(0.25)
q3=df['height'].quantile(0.75)
iqr=q3-q1
print(iqr)
```
![image](https://github.com/user-attachments/assets/7a0f9af0-f299-4bd2-9c25-3105b9dfc12e)
```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
print(lower_bound)
```
![image](https://github.com/user-attachments/assets/2b644049-b297-446f-8000-2da070f2b8f2)
```
print(upper_bound)
```
![image](https://github.com/user-attachments/assets/0cab238a-8e86-416f-a7bb-6367de8b6529)
```
outliers= df[(df['height']<lower_bound) | (df['height']>upper_bound)]
print(outliers)
```
![image](https://github.com/user-attachments/assets/70e32d0a-bd1b-4180-bbc8-d591fb4a1be7)
```
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
```
![image](https://github.com/user-attachments/assets/f5673602-661e-4112-a292-9d92de9f6513)
```
new=df[(df['height']>lower_bound) & (df['height']<upper_bound)]
print(new)
```
![image](https://github.com/user-attachments/assets/fd48d00d-6df4-476c-87a3-7bcd2b328085)
```
sns.boxplot(data=new)
```
![image](https://github.com/user-attachments/assets/b9afb823-2b20-4b79-984c-44ad7f89029d)
```
sns.scatterplot(data=new)
```
![image](https://github.com/user-attachments/assets/1bdc9853-9160-4ee8-a37b-1c8b511d1cfd)

# Result
Thus the given data is read and removed the outliers by detecting using IQR and Z-score method
