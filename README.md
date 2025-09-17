# Name: Adharsh Vidyardh U

# Reg no:212224230007

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

 import numpy as np
 import pandas as pd
 data=pd.read_csv("/content/SAMPLEIDS.csv")
 data

<img width="1101" height="812" alt="Screenshot 2025-09-17 154311" src="https://github.com/user-attachments/assets/57ef8bcb-efa6-4127-96ce-e5bdbf4d83ff" />

data.head(4)
  
<img width="1022" height="269" alt="Screenshot 2025-09-17 154338" src="https://github.com/user-attachments/assets/0d80f2ed-30c3-4ab9-86d9-9015dc02af5f" />

data.tail(7)

<img width="1048" height="348" alt="Screenshot 2025-09-17 154344" src="https://github.com/user-attachments/assets/11cb0666-16a2-48af-a715-1e4e658155d2" />

data.isnull()

<img width="942" height="772" alt="Screenshot 2025-09-17 154429" src="https://github.com/user-attachments/assets/bed8fd1c-746f-4d0d-b9bf-77640e2021e5" />

data.notnull()

<img width="951" height="791" alt="Screenshot 2025-09-17 154437" src="https://github.com/user-attachments/assets/5dba8e11-36b8-49a8-b5d2-7a252cfd9fed" />


data.isnull().sum()


<img width="449" height="362" alt="Screenshot 2025-09-17 154442" src="https://github.com/user-attachments/assets/43e1588b-1e20-4813-b23e-de9a2ab1debb" />

data.isnull().any()

<img width="475" height="347" alt="Screenshot 2025-09-17 155242" src="https://github.com/user-attachments/assets/aee8f6dd-1701-45ff-9942-3af9064fa918" />


data.dropna(axis=1)

<img width="688" height="780" alt="Screenshot 2025-09-17 155307" src="https://github.com/user-attachments/assets/a1c0a246-2af5-44b2-a382-0201436f6bc1" />

data.dropna(axis=0)

<img width="1016" height="594" alt="Screenshot 2025-09-17 155323" src="https://github.com/user-attachments/assets/0836e270-31f7-4be6-9fdd-0daad20c7d9e" />

data.fillna(0)

<img width="1017" height="778" alt="Screenshot 2025-09-17 155412" src="https://github.com/user-attachments/assets/5430c369-ef53-4ee5-9b03-12e889253665" />

data.fillna(method="ffill")

<img width="1279" height="783" alt="Screenshot 2025-09-17 155447" src="https://github.com/user-attachments/assets/d90ce2c7-2d6c-4b41-8093-5af34dcf50d9" />

data.bfill()

<img width="1035" height="788" alt="Screenshot 2025-09-17 155506" src="https://github.com/user-attachments/assets/9b53873e-edca-4c3b-a62e-575d6e25df54" />

data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})

<img width="1008" height="776" alt="Screenshot 2025-09-17 155524" src="https://github.com/user-attachments/assets/cf35c916-d30f-469e-ba01-ba70b92d55ae" />

ir=pd.read_csv("/content/iris.csv")
ir

<img width="778" height="527" alt="Screenshot 2025-09-17 155559" src="https://github.com/user-attachments/assets/1612745c-6259-49ef-92e1-3836dd94d66b" />

ir.describe()

<img width="731" height="375" alt="Screenshot 2025-09-17 155615" src="https://github.com/user-attachments/assets/29039321-982e-48ff-ae1b-3d94bdf4ef9f" />

import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)

<img width="904" height="671" alt="Screenshot 2025-09-17 155710" src="https://github.com/user-attachments/assets/dff2aa85-c7f5-4338-aef4-e56f00960d42" />

 q1=ir.sepal_width.quantile(0.25)
 q3=ir.sepal_width.quantile(0.75)
 iqr=q3-q1
 print(iqr)

 <img width="520" height="153" alt="Screenshot 2025-09-17 155749" src="https://github.com/user-attachments/assets/1058650b-33dc-494e-9978-16aa723c57b9" />


rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']

<img width="843" height="203" alt="Screenshot 2025-09-17 155821" src="https://github.com/user-attachments/assets/8676d100-2747-45e6-9b0b-8281d2e7edf1" />


rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid

<img width="881" height="309" alt="Screenshot 2025-09-17 155844" src="https://github.com/user-attachments/assets/12817cef-ba83-4bc1-b87c-86b40f35997a" />

rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']

<img width="814" height="351" alt="Screenshot 2025-09-17 155907" src="https://github.com/user-attachments/assets/5a8994a3-8480-40e8-9ddd-e12a461cc7cd" />

import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z

<img width="885" height="401" alt="Screenshot 2025-09-17 160156" src="https://github.com/user-attachments/assets/886f3e54-f52c-4a50-9171-2b13eb5a6041" />

# Result
Thus the programs are executed successfully      
