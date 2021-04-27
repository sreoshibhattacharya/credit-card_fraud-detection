# credit-card_fraud-detection
#Importing the necessary packages and libraries
import pandas as pd 
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import datetime
import mathdf[df['Amount']]

#magic functions for In- Notebook Display
%matplotlib inline
#importing the dataset
df = pd.read_csv("creditcard.csv")
#to show a greater number of rows and columns of the data (to increase the limitation of data shown)
pd.set_option('display.max_rows',100)
pd.set_option('display.max_columns',100)
import inspect
#setting the maximum of rows and columns shown to 500
pd.set_option('display.max_rows',500)
pd.set_option('display.max_rows',500)
df['Class'].value_counts(normalize = True)
#tocheck whether the maximum value is an outlier or not
df['Amount'].max()
df[df[('Amount')]>20000]
#removing the outlier:
#finding the index of the outlier
df[df['Amount']>20000].index.values[0]
#dropping the outlier
df=df.drop(df[df['Amount']>20000].index.values[0])
#resetting the dataset after removal of the outlier
df.reset_index(drop= True , inplace = True)
now checking the description
df['Amount'].describe()
df.boxplot(column=['Amount'])
#creating a function to return the index of outliers
def indices_of_outliers(x):
    q1,q3 = np.percentile(x,[25,75])
    iqr=q3-q1 #interquartile range 
    lower_bound = q1-(iqr*1.5) #interquartile range outlier detection formula
    upper_bound = q3+(iqr*1.5)
    return np.where((x>upper_bound) | (x<lower_bound))
indices_of_outliers(df['Amount'])
list(indices_of_outliers(df['Amount']))
df[df['Amount']==0]
inspect.getfullargspec(pd.value_counts)   
df[df['Amount']]
df.shape
df['categorical']= 'a'
df['categorical'].describe(include = 'all')










