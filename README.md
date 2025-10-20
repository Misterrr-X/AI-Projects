#importing necessary libraries
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

#Loading csv file
df = pd.read_csv("online_fraud_detection.csv")

#Top 5 records of the data
df.head() 

#Bottom 5 records of the data.
df.tail()

#columns of the data
df.columns 

#To get concise summary of the data.
df.info() 

#To get unique values in step column
df['step'].unique() 

#To get sum of null values in the data
df.isna().sum() 

#To get the dimension of the data (rows and columns)
df.shape 

#To get unique values from type column
df['type'].unique() 

#This tells counts of each value in the column
df['type'].value_counts() 

type=df['type'].value_counts() 

transaction=type.index 

quantity = type.values 

#High-level interface module,allows you to create charts with minimal code
import plotly.express as px 

px.pie(df,values=quantity,names=transaction,hole=0.4,title='Distribution of transaction type')

#To drop null values, if any.
df=df.dropna() 

