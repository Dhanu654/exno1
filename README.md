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
~~~
import pandas as pd
df=pd.read_csv("Data_set.csv")
~~~~
~~~
df.info()
~~~
![Screenshot 2024-04-01 093911](https://github.com/Dhanu654/exno1/assets/148514965/4eccc611-6842-4d41-a930-60270e8b9caa)
~~~
df.describe()[ ]
~~~
![Screenshot 2024-04-01 094103](https://github.com/Dhanu654/exno1/assets/148514965/68dd0997-4349-4419-a2ef-353fcaa0dc74)
~~~
df.head(10)
~~~
![Screenshot 2024-04-01 094216](https://github.com/Dhanu654/exno1/assets/148514965/db66e922-2567-4f3e-814c-9d5aca2048a8)
~~~
df.tail(5)
~~~
![Screenshot 2024-04-01 094303](https://github.com/Dhanu654/exno1/assets/148514965/f9c2d08e-3c27-4397-b106-026716aa1da0)
~~~

df.isnull()
~~~
![Screenshot 2024-04-01 094318](https://github.com/Dhanu654/exno1/assets/148514965/0bd70101-1a72-4754-8d4e-5a6a202dd32e)
~~~
df.notnull()
~~~
![Screenshot 2024-04-01 094734](https://github.com/Dhanu654/exno1/assets/148514965/df1bfa42-dcb5-4126-acab-a062655958a7)

~~~
df.dropna(axis=1)
~~~
![Screenshot 2024-04-01 094743](https://github.com/Dhanu654/exno1/assets/148514965/26116d0f-dd90-4ccb-91d0-68790cf8d828)

~~~
df.dropna(axis=0)
~~~
![Screenshot 2024-04-01 094758](https://github.com/Dhanu654/exno1/assets/148514965/a6f51d15-973f-488b-81da-0b2254a4dbb7)
~~~

dfs=df[df['num_episodes']<16]
dfs
~~~
![Screenshot 2024-04-01 094810](https://github.com/Dhanu654/exno1/assets/148514965/1468390e-019c-4b13-b696-3e5ea0734601)

~~~
dfs=df[df['show_name'].str.startswith(('A','C'))&(df['num_episodes']>16)]
dfs
~~~
![Screenshot 2024-04-01 094829](https://github.com/Dhanu654/exno1/assets/148514965/bb5799eb-e0b1-4c25-8ee2-df3bf6ce748e)

~~~
df.iloc[:3]
~~~
![Screenshot 2024-04-01 094839](https://github.com/Dhanu654/exno1/assets/148514965/0f4f939f-9005-4e6f-a356-204fd0b93d42)

~~~
df.iloc[0:4,1:4]
~~~
![Screenshot 2024-04-01 094846](https://github.com/Dhanu654/exno1/assets/148514965/9737688d-b172-4afe-8cc4-92e343b544b8)

~~~
df.iloc[[1,3,5],[1,3]]
~~~
![Screenshot 2024-04-01 094854](https://github.com/Dhanu654/exno1/assets/148514965/8f95a428-d07f-4e6d-b56d-05b422e1c503)


~~~
df.fillna(0)
~~~
![Screenshot 2024-04-01 102251](https://github.com/Dhanu654/exno1/assets/148514965/191c72c4-c7a2-4ee0-a579-3d4df719c5af)

~~~
df.fillna(method="ffill")
~~~
![Screenshot 2024-04-01 102310](https://github.com/Dhanu654/exno1/assets/148514965/81e979e2-ad20-4ff5-8f06-bc44a2b831fd)


~~~
df.fillna(method="bfill")
~~~
![Screenshot 2024-04-01 102323](https://github.com/Dhanu654/exno1/assets/148514965/afffddd5-8624-4194-92f0-182d52e83235)


~~~
df['num_episodes'].fillna(value=df['num_episodes'].mean())
~~~
![Screenshot 2024-04-01 102335](https://github.com/Dhanu654/exno1/assets/148514965/63464dd6-7803-49de-b2e7-7848192e139a)


~~~
df['num_episodes'].fillna(value=df['num_episodes'].mean(),inplace=True)
df
~~~
![Screenshot 2024-04-01 102349](https://github.com/Dhanu654/exno1/assets/148514965/0f76a949-0c8c-44ea-84e4-b0387e165647)


~~~
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
~~~
![Screenshot 2024-04-01 102417](https://github.com/Dhanu654/exno1/assets/148514965/f0a9c815-bf51-404f-9c8a-20c724c97c92)

~~~
df.shape
~~~
![Screenshot 2024-04-01 102426](https://github.com/Dhanu654/exno1/assets/148514965/430a606e-71d1-4377-acb4-df0429b8d99c)

~~~
df.describe()
~~~
![Screenshot 2024-04-01 102434](https://github.com/Dhanu654/exno1/assets/148514965/3f013e06-b6c7-4114-9353-48562bda288e)

~~~
df.info()
~~~
![Screenshot 2024-04-01 102442](https://github.com/Dhanu654/exno1/assets/148514965/5711b6b2-97cf-4f14-ba11-697efa4737d5)

~~~
Used to count of all the null values in a column.
~~~
~~~
df.isnull().sum()
~~~
![Screenshot 2024-04-01 102450](https://github.com/Dhanu654/exno1/assets/148514965/abaa0e35-14c8-46fa-b8a1-0532ca7d8dad)

~~~
df.nunique()
~~~
![Screenshot 2024-04-01 102456](https://github.com/Dhanu654/exno1/assets/148514965/2866826d-2829-467a-b447-133997d4806e)

~~~
df['GENDER'].value_counts()
~~~
![Screenshot 2024-04-01 102649](https://github.com/Dhanu654/exno1/assets/148514965/0b51dd2b-c5e2-4585-9256-ac4ee59f08fb)
~~~
df.dropna(how='any').shape
~~~
![Screenshot 2024-04-01 102655](https://github.com/Dhanu654/exno1/assets/148514965/22d941f1-9c6c-4192-9077-316e70cd6c02)

~~~
x=df.dropna(how='any')
x
~~~
![Screenshot 2024-04-01 102705](https://github.com/Dhanu654/exno1/assets/148514965/2b0713cc-5d2a-43c8-8aef-3675c6187adb)

~~~
df.dropna(how='all').shape
~~~
![Screenshot 2024-04-01 102712](https://github.com/Dhanu654/exno1/assets/148514965/dc08a236-ebef-41df-b20c-111ab4416043)
~~~
x2=df.dropna(how='all')
x2
~~~


~~~
Total=df.dropna(subset=['TOTAL'],how='any')
Total
~~~

~~~
df.dropna(subset=['TOTAL'],how='any').shape
~~~
![Screenshot 2024-04-01 102755](https://github.com/Dhanu654/exno1/assets/148514965/4e1142e3-034e-42cf-bcf8-f747fcc5269d)

~~~
Total=df.dropna(subset=['M1','M2','M3','M4'],how='any')
Total
~~~
![Screenshot 2024-04-01 102806](https://github.com/Dhanu654/exno1/assets/148514965/306986de-f188-47a5-a851-c791144983dd)

~~~
df.dropna(subset=['M1','M2','M3','M4'],how='any').shape
~~~
![Screenshot 2024-04-01 110918](https://github.com/Dhanu654/exno1/assets/148514965/d02e2da7-891f-44ae-93ff-a86d82e6daf4)

~~~
d1=df.fillna(0)
d1
~~~
![Screenshot 2024-04-01 110936](https://github.com/Dhanu654/exno1/assets/148514965/97ba4865-221d-4df4-9ace-5f9174f19cc2)

~~~
d2=df.fillna(method='ffill')
d2
~~~
![Screenshot 2024-04-01 110949](https://github.com/Dhanu654/exno1/assets/148514965/4c1d514c-f537-4a07-93d7-b5c751cbb427)

~~~
d3=df.fillna(method='bfill')
d3
~~~
![Screenshot 2024-04-01 111007](https://github.com/Dhanu654/exno1/assets/148514965/ed6174b7-877e-433a-9e4e-138ad6fd4505)

~~~
df.interpolate()
~~~
![Screenshot 2024-04-01 111018](https://github.com/Dhanu654/exno1/assets/148514965/4f39e955-ec2f-44c8-ad52-ae5e1a078e89)

~~~
mn=df.TOTAL.mean()
mn
~~~
![Screenshot 2024-04-01 111026](https://github.com/Dhanu654/exno1/assets/148514965/2f9ceb2f-9237-4966-b275-e8797a52c9a1)

~~~
d5=df.TOTAL.fillna(mn,inplace=False)
d5
~~~
![Screenshot 2024-04-01 111033](https://github.com/Dhanu654/exno1/assets/148514965/d8ea43e8-4b37-4ed6-9808-012dbaee0b44)

~~~
d6=df.isnull()
d6
~~~
![Screenshot 2024-04-01 111041](https://github.com/Dhanu654/exno1/assets/148514965/eea7ee34-48b7-435e-92dd-1e8b1b241e4a)

~~~
d6=df.notnull()
d6
~~~
![Screenshot 2024-04-01 111051](https://github.com/Dhanu654/exno1/assets/148514965/a78345c7-3ade-4223-b87f-5cfb20803744)

~~~
delete=df.dropna()
delete
~~~
![Screenshot 2024-04-01 111100](https://github.com/Dhanu654/exno1/assets/148514965/1978f639-d876-498e-9aa7-2c34558b99b9)

~~~
df.head(5)
~~~

![Screenshot 2024-04-01 111124](https://github.com/Dhanu654/exno1/assets/148514965/32611fe7-2c8c-4151-b73d-de6c123836c8)

~~~
df.tail(6)
~~~
![Screenshot 2024-04-01 111131](https://github.com/Dhanu654/exno1/assets/148514965/3aac17c8-ae32-40b1-a635-57cd7f110502)

~~~
duplicate=df.duplicated()
duplicate

~~~
![Screenshot 2024-04-01 111138](https://github.com/Dhanu654/exno1/assets/148514965/4c8fe50d-eb5f-4b68-9301-7fe9df3ebae4)

~~~
dup=df.drop_duplicates(inplace=False)
dup
~~~
![Screenshot 2024-04-01 111148](https://github.com/Dhanu654/exno1/assets/148514965/010173e1-078b-4efa-8c23-442e0f18921f)

~~~
df['DOB']
~~~
![Screenshot 2024-04-01 111156](https://github.com/Dhanu654/exno1/assets/148514965/e2969d21-fc08-4f4b-8b5b-d54e24abc43c)

~~~
x=pd.to_datetime(df['DOB'])
x
~~~
![Screenshot 2024-04-01 111204](https://github.com/Dhanu654/exno1/assets/148514965/a3d0371c-f889-4623-81fb-d772a715c40f)

~~~
df['DOB']=pd.to_datetime(df['DOB'])
df
~~~
![Screenshot 2024-04-01 111214](https://github.com/Dhanu654/exno1/assets/148514965/07d54a87-04ad-432b-960f-3ad058ff7d1e)


~~~
df.iloc[0:4,1:4]
~~~

![Screenshot 2024-04-01 111224](https://github.com/Dhanu654/exno1/assets/148514965/b9e923ef-0e05-44cb-b7f3-9579af7f6ca5)
~~~
df.iloc[[1,3,5],[1,3]]
~~~
![Screenshot 2024-04-01 111230](https://github.com/Dhanu654/exno1/assets/148514965/6610c435-87a8-47d0-aa1d-917cadd0def5)

~~~
df.iloc[:4]
~~~
![Screenshot 2024-04-01 111240](https://github.com/Dhanu654/exno1/assets/148514965/9cc1fde7-1b73-45c0-922c-1e9f47f97532)

~~~
df.dropna(axis=0)
~~~
![Screenshot 2024-04-01 111248](https://github.com/Dhanu654/exno1/assets/148514965/cc7a0b71-b1ed-4a91-ab77-66b9f99cdfda)

~~~
df.dropna(axis=1)
~~~
![Screenshot 2024-04-01 111258](https://github.com/Dhanu654/exno1/assets/148514965/ce44a5ed-3de7-4c32-a1f3-77819b0a41d5)

~~~
df.groupby('TOTAL').max()
~~~
![Screenshot 2024-04-01 111307](https://github.com/Dhanu654/exno1/assets/148514965/3570bdf3-7ce3-4cb1-9b80-ed5fc45cddd9)
~~~
df.filter(like='NAME')
~~~
![Screenshot 2024-04-01 112847](https://github.com/Dhanu654/exno1/assets/148514965/5fc2e4ca-885c-40c4-bb5e-75b21936dbe4)
![Screenshot 2024-04-01 112853](https://github.com/Dhanu654/exno1/assets/148514965/f445ece0-0dfe-422d-afba-0f39fab23c89)

~~~
df.dtypes
~~~
![Screenshot 2024-04-01 112900](https://github.com/Dhanu654/exno1/assets/148514965/85db63dd-4e12-4f8e-b7d7-9fb8c1edd48d)

~~~
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
~~~
![Screenshot 2024-04-01 112909](https://github.com/Dhanu654/exno1/assets/148514965/157bc1b4-b8bc-4563-addd-7ab5b7e4ca5a)

~~~
df.dropna(inplace=True)
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
~~~
![Screenshot 2024-04-01 112918](https://github.com/Dhanu654/exno1/assets/148514965/b04d69a6-0aad-4a62-ab87-33aaea27cd8b)

~~~
import numpy as np
import seaborn as sns
from scipy import stats
df=pd.read_csv("heights.csv")
dfimport pandas as pd

~~~
![Screenshot 2024-04-01 112931](https://github.com/Dhanu654/exno1/assets/148514965/a067cac1-be98-4dc7-8ed8-46b2e1536d4c)

~~~
sns.boxplot(data=df)
~~~
![Screenshot 2024-04-01 112951](https://github.com/Dhanu654/exno1/assets/148514965/bef65e8b-a734-4332-b6a6-c6c41cbdae58)

~~~
sns.scatterplot(data=df)
~~~
![Screenshot 2024-04-01 113008](https://github.com/Dhanu654/exno1/assets/148514965/6246d6c8-9a3a-41db-9a17-0fd4ab9ef06d)

~~~
max=df['height'].quantile(0.75)
max
~~~
![Screenshot 2024-04-01 113017](https://github.com/Dhanu654/exno1/assets/148514965/35ca02b8-6e55-4c10-b387-7db40bed1c9a)

~~~
min=df['height'].quantile(0.25)
min
~~~
![Screenshot 2024-04-01 113023](https://github.com/Dhanu654/exno1/assets/148514965/2eec7d08-fa58-4432-aad4-6f37fb6945c3)

~~~
iqr=max-min
iqr
~~~
![Screenshot 2024-04-01 113029](https://github.com/Dhanu654/exno1/assets/148514965/dac4ee89-ee06-49ae-a3f7-0aa3dc9b8df0)

~~~
dq=df[((df['height']>=min)&(df['height']<=max))]
dq
~~~
![Screenshot 2024-04-01 113035](https://github.com/Dhanu654/exno1/assets/148514965/71741f82-0605-4db1-a494-c2a463a7eeef)

~~~
sns.boxplot(data=dq)
~~~
![Screenshot 2024-04-01 113044](https://github.com/Dhanu654/exno1/assets/148514965/eaa4c56c-9acc-4401-a724-b9c45a1fe65c)

~~~
low=min-1.5*iqr
low
~~~
![Screenshot 2024-04-01 113054](https://github.com/Dhanu654/exno1/assets/148514965/e5ee9f5a-159c-4566-af1d-9a69624115cf)

~~~
high=max+1.5*iqr
high
~~~
![Screenshot 2024-04-01 113058](https://github.com/Dhanu654/exno1/assets/148514965/90921cd3-09cc-4fa2-972e-0106c09915ac)

~~~
qm=df[((df['height']>=low)&(df['height']<=high))]
qm
~~~
![Screenshot 2024-04-01 113150](https://github.com/Dhanu654/exno1/assets/148514965/ccfce265-63ec-4f5f-8ea0-4a6b4d24f0e5)

~~~
sns.boxplot(data=qm)
~~~
![Screenshot 2024-04-01 113158](https://github.com/Dhanu654/exno1/assets/148514965/9b288a31-8bdd-428b-9a49-e9a7e89e6ad5)










# Result
Thus the output for the data cleaning process is successfully verified.
