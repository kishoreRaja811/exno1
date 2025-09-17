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

<img width="1229" height="844" alt="image" src="https://github.com/user-attachments/assets/041a177d-6c68-48d9-a818-22e07c0ecea9" />

data.head(4)

<img width="1229" height="387" alt="image" src="https://github.com/user-attachments/assets/a39462bf-b2f4-4476-ac35-e91ed0a88255" />

data.tail(4)

<img width="1377" height="290" alt="image" src="https://github.com/user-attachments/assets/3e785d41-abf3-4685-bbf6-1e3e17cd1422" />

data.isnull()

<img width="1544" height="712" alt="image" src="https://github.com/user-attachments/assets/996e228c-42a1-491c-921e-fffd77512040" />

data.notnull()

<img width="1192" height="757" alt="image" src="https://github.com/user-attachments/assets/c4816f0f-3731-45cf-95d6-f23e7938ffb4" />

data.isnull().sum()

<img width="1414" height="626" alt="image" src="https://github.com/user-attachments/assets/2b7dc62b-0ef5-4e58-900f-161e8eddfedf" />

data.isnull().any()

<img width="1566" height="615" alt="image" src="https://github.com/user-attachments/assets/7391b13b-3aa8-4483-af2b-fc3f7b4014e9" />

data.dropna(axis=1)

<img width="1244" height="753" alt="image" src="https://github.com/user-attachments/assets/0bc763cf-c3b3-49b0-969c-8bab11e845cd" />

data.dropna(axis=0)

<img width="1329" height="628" alt="image" src="https://github.com/user-attachments/assets/ec6719ed-5603-460e-bf79-650e1825e292" />

data.fillna(0)

<img width="1370" height="739" alt="image" src="https://github.com/user-attachments/assets/b4a5173f-19bf-4469-9e0a-484c2e506fe8" />

data.fillna(method="ffill")

<img width="1789" height="735" alt="image" src="https://github.com/user-attachments/assets/d6b98dfd-9416-40d8-99b9-809ef1fb00ff" />

data.bfill()

<img width="1309" height="848" alt="image" src="https://github.com/user-attachments/assets/89afc3cb-e07a-47d4-b54d-d9d3adf86c08" />

data.fillna({'REGNO':1,'NAME':'Hari'})

<img width="1411" height="748" alt="image" src="https://github.com/user-attachments/assets/f8a3cdf4-1871-4a8c-9f6a-b62f91a68fef" />

irr=pd.read_csv("/content/iris.csv")
irr

<img width="1203" height="582" alt="image" src="https://github.com/user-attachments/assets/0e4cb238-be6e-4e53-aa0d-b68323874aac" />

irr.describe()

<img width="891" height="454" alt="image" src="https://github.com/user-attachments/assets/e7d602e6-d849-4267-9f50-cec19cbf1171" />

import seaborn as sns
sns.boxplot(x="sepal_length",data=irr)

<img width="1020" height="660" alt="image" src="https://github.com/user-attachments/assets/e3671419-88bc-46bc-b57e-4e210c649b90" />

q1=irr.sepal_width.quantile(0.25)
 q3=irr.sepal_width.quantile(0.75)
 iqr=q3-q1
 print(iqr)

 <img width="952" height="191" alt="image" src="https://github.com/user-attachments/assets/68c152ce-730c-4050-91bb-632697d59a59" />

  rid=irr[((irr.sepal_width<(q1-1.5*iqr))|(irr.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']

<img width="919" height="326" alt="image" src="https://github.com/user-attachments/assets/f306516a-e9f2-48da-b37a-376ae8b6d061" />

rid=irr[~((irr.sepal_width<(q1-1.5*iqr))|(irr.sepal_width>(q3+1.5*iqr)))]
 rid

 <img width="1015" height="561" alt="image" src="https://github.com/user-attachments/assets/606a3293-9086-4d8e-bf28-2a6afd0eb6f8" />

 rid=irr[((irr.sepal_width>(q1-1.5*iqr))&(irr.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']

<img width="878" height="585" alt="image" src="https://github.com/user-attachments/assets/95c0d2b2-f766-4987-9d16-0413d913f5ce" />

import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(irr.sepal_width))
z

<img width="1079" height="798" alt="image" src="https://github.com/user-attachments/assets/c50fe385-2f98-43f7-9ca1-946fd7c9536d" />

a=irr[z>3]
a

<img width="862" height="239" alt="image" src="https://github.com/user-attachments/assets/81043840-62a7-4140-975f-cfd8e1af5e80" />




# Result
   Thus the programs are executed successfully
