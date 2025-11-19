# Exno:1
Data Cleaning Process
# Name : B.sanjai Ganth
# Reg No: 212224230244

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
# Program
```
import pandas as pd
data = pd.read_csv("SAMPLEIDS.csv")
data
```
# Output

<img width="844" height="673" alt="image" src="https://github.com/user-attachments/assets/061b25bc-76f0-4708-9230-ccc59d56f3ab" />


# Program
```
data.head()
```
# Output
<img width="811" height="196" alt="image" src="https://github.com/user-attachments/assets/876acfbd-5263-4b9a-a719-41174fc88af8" />

# Program
```
data.tail()
```
# Output
<img width="853" height="205" alt="image" src="https://github.com/user-attachments/assets/1a00a6c6-fbbf-4d7f-9cd1-d368878191e4" />

# Program
```
data.head(3)
```
# Output
<img width="796" height="148" alt="image" src="https://github.com/user-attachments/assets/ef09c79d-d8dc-48e5-b788-d903dc0323a4" />

# Program
```
data.tail(2)
```
# Output
<img width="795" height="105" alt="image" src="https://github.com/user-attachments/assets/4bfbb8fe-c156-4e41-9da4-18f251d1b0ca" />

# Program
```
data.isnull()
```
# Output
<img width="696" height="677" alt="image" src="https://github.com/user-attachments/assets/5f900ffd-da80-45a2-92b2-18d7b27ace1e" />

# Program
```
data.notnull()
```
# Output
<img width="688" height="675" alt="image" src="https://github.com/user-attachments/assets/fbb74743-d29a-4a4b-bae4-2f0c44fb55d0" />

# Program
```
data.isnull().sum()
```
# Output
<img width="189" height="239" alt="image" src="https://github.com/user-attachments/assets/e797f3d6-5576-49d1-aa2b-128056f30400" />

# Program
```
data.isnull().any()
```
# Output
<img width="230" height="244" alt="image" src="https://github.com/user-attachments/assets/5d161e21-b01b-4f81-9b8a-b7dc6730cd33" />
# Program
```
data.dropna(axis=0)
```
# Output
<img width="816" height="446" alt="image" src="https://github.com/user-attachments/assets/28ffbe65-7fac-40f7-a5c5-33b8359154ff" />

# Program
```
data.dropna(axis=1)
```
# Output
<img width="302" height="664" alt="image" src="https://github.com/user-attachments/assets/454e058c-b943-4ae9-922b-19c9b6e34e63" />

# Program
```
data.dropna()
```
# Output
<img width="812" height="439" alt="image" src="https://github.com/user-attachments/assets/186a0a7d-c056-4972-94f7-6bc0c2c34718" />

# Program
```
data.fillna(5)
```
# Output
<img width="797" height="686" alt="image" src="https://github.com/user-attachments/assets/a2bf50ba-cf02-4c88-9def-edf215eefab3" />

# Program
```
data.fillna(method = 'ffill')
```
# Output
<img width="823" height="681" alt="image" src="https://github.com/user-attachments/assets/f31c45b3-f812-47a2-8afc-5b0e93690f1b" />

# Program
```
data.fillna(method = 'bfill')
```
# Output
<img width="796" height="677" alt="image" src="https://github.com/user-attachments/assets/7360fbcc-e8d8-42ee-b919-6bc78c50e73a" />

# Program
```
data.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALLEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
# Output
<img width="806" height="679" alt="image" src="https://github.com/user-attachments/assets/90486d0b-5007-4358-a8ba-e47a3cfb0228" />

# Program
```
import pandas as pd
data2 = pd.read_csv("iris (1).csv")
data2
```
# Output
<img width="575" height="410" alt="image" src="https://github.com/user-attachments/assets/ba53095a-fcd6-42ba-80f9-4696217984df" />

# Program
```
data2.describe()
```
# Output
<img width="498" height="292" alt="image" src="https://github.com/user-attachments/assets/fdcd769f-64c0-4312-9c02-36e93f6b51cc" />

# Program
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=data2)
```
# Output
<img width="626" height="464" alt="image" src="https://github.com/user-attachments/assets/281990cc-8e27-4475-8dcd-bbfe1c166731" />

# Program
```
q1 = data2.sepal_width.quantile(0.25) 
q3 = data2.sepal_width.quantile(0.75) 
iqr = q3-q1
print(iqr)
```
# Output
<img width="879" height="31" alt="image" src="https://github.com/user-attachments/assets/2aed3ca9-91ac-487f-8347-9daad89c57c7" />

# Program
```
range = data2[((data2.sepal_width<(q1-1.5*iqr))|(data2.sepal_width>(q3+1.5*iqr)))]
range['sepal_width']
```
# Output
<img width="321" height="101" alt="image" src="https://github.com/user-attachments/assets/b66c9521-224c-4182-859b-7946ce593b48" />

# Program
```
range = data2[~((data2.sepal_width<(q1-1.5*iqr))|(data2.sepal_width>(q3+1.5*iqr)))]
range['sepal_width']
```
# Output
<img width="539" height="215" alt="image" src="https://github.com/user-attachments/assets/2dbc8c5f-1433-4abf-89b0-8925c8bbed6a" />

# Program
```
sns.boxplot(x='sepal_width',data=range)
```
# Output
<img width="665" height="466" alt="image" src="https://github.com/user-attachments/assets/4efe83fd-f6d8-4914-8616-58c66f248226" />

# Program
```
import numpy as np
import scipy.stats as stats
z = np.abs(stats.zscore(data2['sepal_width']))
z
```
# Output
<img width="454" height="249" alt="image" src="https://github.com/user-attachments/assets/3ac53314-6d33-4a6a-b990-f7a457ff7b61" />



# Result
          Thus, we have read the given data and performed data cleaning and saved the cleaned data to a file successfully.
