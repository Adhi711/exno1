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


data.isnull().sum()


<img width="449" height="362" alt="Screenshot 2025-09-17 154442" src="https://github.com/user-attachments/assets/43e1588b-1e20-4813-b23e-de9a2ab1debb" />

data.isnull().any()



data.dropna(axis=1)

   

data.dropna(axis=0)


![Uploading Screenshot 2025-09-17 155323.png…]()












            <<include your coding and its corressponding output screen shots here>>
# Result
          <<include your Result here>>
