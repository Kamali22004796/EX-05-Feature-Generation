# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE

Program Developed: KAMALI.E
Register number:212222110015

# data.csv:
~~~
import pandas as pd
df=pd.read_csv("data.csv")
df

#feature generation
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()


df1["City"] = ohe.fit_transform(df1[["City"]])

temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])

edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
~~~
# data.csv output 

![Screenshot 2023-04-16 083053](https://user-images.githubusercontent.com/120567837/232263967-1fb83d04-6e89-47db-b178-261a243463e0.png)

![Screenshot 2023-04-16 083239](https://user-images.githubusercontent.com/120567837/232263982-7b2b0818-08f5-45cd-b33d-c852a7deabba.png)

![Screenshot 2023-04-16 083318](https://user-images.githubusercontent.com/120567837/232264006-b0b437f3-3211-4adc-8a65-3598181d4bd2.png)

![Screenshot 2023-04-16 083352](https://user-images.githubusercontent.com/120567837/232264033-ae592dec-0e19-4dc0-93ba-fdec7785a134.png)

![Screenshot 2023-04-16 083506](https://user-images.githubusercontent.com/120567837/232264064-d5d7eafd-23be-4ce2-b1db-c8ace5385cce.png)

![Screenshot 2023-04-16 083544](https://user-images.githubusercontent.com/120567837/232264085-0818cec4-31d5-423f-a180-bdc4117b242f.png)

![Screenshot 2023-04-16 083622](https://user-images.githubusercontent.com/120567837/232264102-9b4f0b5a-918b-4434-8a14-63ff9b85eb64.png)

# encoding.csv code:

~~~
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df

#feature generation
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])

df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
~~~

# encoding.csv output:

![Screenshot 2023-04-16 093357](https://user-images.githubusercontent.com/120567837/232265828-ffe582ac-9d18-45bd-8427-e0d283c947b4.png)

![Screenshot 2023-04-16 093457](https://user-images.githubusercontent.com/120567837/232265865-b380328d-933b-49f6-835d-6c578ad88c87.png)

![Screenshot 2023-04-16 093516](https://user-images.githubusercontent.com/120567837/232265873-4c745748-7aec-44ee-ba5f-9ffc1ca60497.png)

![Screenshot 2023-04-16 093717](https://user-images.githubusercontent.com/120567837/232265918-d7dd3abf-96ae-4e31-85e9-85e7fc69bcab.png)

![Screenshot 2023-04-16 093735](https://user-images.githubusercontent.com/120567837/232265921-2b48a281-99fc-4fd9-893b-aaf93ee6a138.png)

![Screenshot 2023-04-16 093754](https://user-images.githubusercontent.com/120567837/232265923-990f1d78-bf0f-4eb5-8f28-b83460cd7ab5.png)

![Screenshot 2023-04-16 093815](https://user-images.githubusercontent.com/120567837/232265927-48467529-19a6-4923-823b-3b52f7380442.png)

# Tiatanic.csv Code:

import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df

#removing unwanted data
df.drop("Name",axis=1,inplace=True)
df.drop("Ticket",axis=1,inplace=True)
df.drop("Cabin",axis=1,inplace=True)

#data cleaning
df.isnull().sum()

df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])

df.isnull().sum()

df

#feature encoding
from category_encoders import BinaryEncoder
be=BinaryEncoder()
df["Sex"]=be.fit_transform(df[["Sex"]])
ndf=be.fit_transform(df["Sex"])
ndf

df1=df.copy()
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
embark=['S','C','Q']
e1=OrdinalEncoder(categories=[embark])
df1['Embarked'] = e1.fit_transform(df[['Embarked']])
df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df5

# Titanic.csv Output:

![Screenshot 2023-04-16 094121](https://user-images.githubusercontent.com/120567837/232266067-1f5d6e2a-28ec-40c0-8a0b-41ce1d56e06e.png)

![Screenshot 2023-04-16 094142](https://user-images.githubusercontent.com/120567837/232266070-77856a92-5b8e-4325-ab5a-3a86981033df.png)

![Screenshot 2023-04-16 094159](https://user-images.githubusercontent.com/120567837/232266087-6516fb69-5ac4-484e-abb3-e3b256fa0a9c.png)

![Screenshot 2023-04-16 094219](https://user-images.githubusercontent.com/120567837/232266092-bc520153-e35c-4050-9f3c-2e6e667260a3.png)

![Screenshot 2023-04-16 094238](https://user-images.githubusercontent.com/120567837/232266096-1638ef95-150e-4e67-9f87-40a9dcb22006.png)

![Screenshot 2023-04-16 094256](https://user-images.githubusercontent.com/120567837/232266099-e8b01e49-074d-488c-a0e6-b23e3eabc77a.png)

![Screenshot 2023-04-16 094319](https://user-images.githubusercontent.com/120567837/232266103-b90f36ef-eaba-4388-ae4b-fc01ab17ae56.png)

![Screenshot 2023-04-16 094340](https://user-images.githubusercontent.com/120567837/232266111-4637b4b6-7aeb-4acf-b664-0bedecd13998.png)

# result:

Hence Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully.






