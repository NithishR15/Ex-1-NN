<H3>ENTER YOUR NAME:</H3> NITHISH R
<H3>ENTER YOUR REGISTER NO:</H3> 212223040135
<H3>EX. NO.1</H3>
<H3>DATE :25/08/24</H3>
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:
To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:
```python
#import libraries
from google.colab import files
import pandas as pd
import io
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

#Read the dataset from drive
df=pd.read_csv('/content/Churn_Modelling.csv')
df

# Finding Missing Values
print(df.isnull().sum())

#Handling Missing values
df.fillna(df.mean(),inplace=True)
print(df.isnull().sum())

y=df.iloc[:,-1].values
print(y)

#Check for Duplicates
df.duplicated()

#Detect Outliers
df.describe()

#Normalize the dataset
scaler=MinMaxScaler()
df1=pd.DataFrame(scaler.fit_transform(data))
print(df1)

#split the dataset into input and output
x=df.iloc[:, :-1].values
print(x)
y=df.iloc[:,-1].values
print(y)

#splitting the data for training & Testing
X_train ,X_test ,y_train,y_test=train_test_split(x,y,test_size=0.2)

#Print the training data and testing data
print("X_train\n")
print(X_train)
print("\nLenght of X_train ",len(X_train))
print("\nX_test\n")
print(X_test)
print("\nLenght of X_test ",len(X_test))
```


## OUTPUT:
### dataset:
![Screenshot 2024-08-25 222348](https://github.com/user-attachments/assets/3f32590f-123e-47b0-8353-691723bdf46b)


### Finding Missing Values:
![Screenshot 2024-08-25 222402](https://github.com/user-attachments/assets/5d4d6c51-72f4-494c-a0b1-37624421a5c8)

### Handling Missing values:
![Screenshot 2024-08-25 222419](https://github.com/user-attachments/assets/6290ef95-e2ac-474d-9080-85f103021fd9)

### Duplicates:
![Screenshot 2024-08-25 222447](https://github.com/user-attachments/assets/02acdfd1-eed5-45c8-8207-bedbd8b61802)

### Normalize the dataset:
![Screenshot 2024-08-25 222510](https://github.com/user-attachments/assets/3d4d7623-4add-4a8b-86d0-c28bcc36a350)

### split the dataset into input and output:
![Screenshot 2024-08-25 222523](https://github.com/user-attachments/assets/304f94e5-daa6-4299-9f01-e7740aef7ece)

### splitting the data for training & Testing:
![Screenshot 2024-08-25 222535](https://github.com/user-attachments/assets/438efb2a-458b-41f2-a44a-95f3f159d2df)

## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


