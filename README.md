# House-Price-Prediction-and-Data-Cleaning
Machine Learning data preprocessing pipeline for Bengaluru house price prediction. Cleans raw housing dataset, handles missing values, processes total square footage, removes outliers, and saves a clean dataset for further modeling. Includes exploratory analysis and visualizations.
### video number 1 machine learning project
import pandas as pd
import numpy as np
from matplotlib import pyplot as plt
%matplotlib inline
import matplotlib
matplotlib.rcParams["figure.figsize"] = (20,10)

df1 = pd.read_csv(r"C:\Users\muham\OneDrive\Desktop\BHP\Bengaluru_House_Data.csv")
df1.head()

df1.shape

df1.groupby('area_type')['area_type'].agg('count')

df2 = df1.drop(['availability','balcony','area_type','society'],axis='columns')
df2.head()

df2.isnull().sum()

df3 = df2.dropna()
df3.isnull().sum()

df3.shape

df3['size'].unique()

df3['bhk'] = df3['size'].apply(lambda x: int(x.split(' ')[0]))

df3.head()

df3['bhk'].unique()

df3[df3.bhk>20]

df.total_sqft.unique()

def is_float(x):
   try:
       float(x)
   except:
       return False
   return True

df3[~df3['total_sqft'].apply(is_float)].head(10)


def convert_sqft_to_num(x):
    tokens = x.split('-')
    if len(tokens) == 2:
        return (float(tokens[0])+float(tokens[1]))/2
    try:
        return float(x)
    except:
        return None

convert_sqft_to_num('2166')


convert_sqft_to_num('34.46Sq. Meter')


df4 = df3.copy()
df4['total_sqft'] = df4['total_sqft'].apply(convert_sqft_to_num)
df.head(10)









