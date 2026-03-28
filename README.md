# CarFeatures_EDA_Encoding
This is the basic data analysis and the encoding project 

🚗 Car Features Data Preprocessing Project
📌 Overview

This project focuses on data preprocessing of a car dataset where all features (columns) are converted into numerical format.
This is an essential step in Machine Learning because models require numerical input to perform computations.

🎯 Objective
Clean the dataset
Handle missing values
Convert categorical data into numerical form
Prepare the dataset for Machine Learning models
📂 Dataset Description

The dataset contains various car attributes such as:

Make (Brand)
Model
Year
Engine HP
Engine Cylinders
Transmission Type
Fuel Type
Driven Wheels
Market Category
Vehicle Size
Vehicle Style
Highway MPG
City MPG
MSRP (Price)
⚙️ Technologies Used
Python 🐍
Pandas
NumPy
Scikit-learn
🔍 Project Workflow
1. Data Loading
Loaded dataset using Pandas
import pandas as pd
df = pd.read_csv("cars.csv")
2. Handling Missing Values
Filled null values using:
Mean (for numerical columns)
Mode (for categorical columns)
df['Engine HP'].fillna(df['Engine HP'].mean(), inplace=True)
df['Engine Cylinders'].fillna(df['Engine Cylinders'].median(), inplace=True)
3. Removing Duplicates
df.drop_duplicates(inplace=True)
4. Converting Categorical Columns to Numerical
🔹 Label Encoding

Used for ordinal data

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()
df['Transmission Type'] = le.fit_transform(df['Transmission Type'])
🔹 One-Hot Encoding

Used for nominal data

df = pd.get_dummies(df, columns=['Fuel Type', 'Driven Wheels', 'Vehicle Size'])
5. Final Dataset
All columns are now numerical
Ready for Machine Learning models
print(df.info())
