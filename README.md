# 🚗 CarFeatures_EDA_Encoding

This project focuses on **basic data analysis and feature encoding** of a car dataset.
It demonstrates how raw data is cleaned and transformed into a fully **numerical dataset** suitable for Machine Learning.

---

## 📌 Overview

The main objective of this project is to preprocess a car dataset by handling missing values and converting all categorical features into numerical format.
This step is essential because Machine Learning algorithms require numerical input for processing and prediction.

---

## 🎯 Objectives

* Clean the dataset
* Handle missing values
* Convert categorical data into numerical form
* Prepare the dataset for Machine Learning models

---

## 📂 Dataset Description

The dataset includes various attributes of cars such as:

* Make (Brand)
* Model
* Year
* Engine HP
* Engine Cylinders
* Transmission Type
* Fuel Type
* Driven Wheels
* Market Category
* Vehicle Size
* Vehicle Style
* Highway MPG
* City MPG
* MSRP (Price)

---

## ⚙️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn

---

## 🔍 Project Workflow

### 1. Data Loading

The dataset is loaded using Pandas for further processing.

```python
import pandas as pd
df = pd.read_csv("cars.csv")
```

---

### 2. Handling Missing Values

Missing values are handled using appropriate statistical techniques:

* Mean for numerical data
* Median where necessary
* Mode for categorical data

```python
df['Engine HP'].fillna(df['Engine HP'].mean(), inplace=True)
df['Engine Cylinders'].fillna(df['Engine Cylinders'].median(), inplace=True)
```

---

### 3. Removing Duplicates

Duplicate records are removed to maintain data quality.

```python
df.drop_duplicates(inplace=True)
```

---

### 4. Converting Categorical Data to Numerical

#### 🔹 Label Encoding

Used for ordinal categorical features.

```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()
df['Transmission Type'] = le.fit_transform(df['Transmission Type'])
```

---

#### 🔹 One-Hot Encoding

Used for nominal categorical features.

```python
df = pd.get_dummies(df, columns=['Fuel Type', 'Driven Wheels', 'Vehicle Size'])
```

---

### 5. Final Dataset

After preprocessing:

* All features are converted into numerical format
* The dataset is clean and structured
* Ready for Machine Learning applications

---

## 🚀 How to Run the Project

1. Clone the repository
2. Install required libraries
3. Run the preprocessing script

---


## 🧠 Key Learnings

* Importance of data preprocessing
* Handling missing values effectively
* Encoding categorical variables
* Preparing real-world datasets for ML

---

## 🔮 Future Scope

* Apply machine learning models for prediction
* Perform exploratory data analysis (EDA) with visualization
* Implement feature scaling and optimization techniques


This project is open-source and available under the MIT License.

---
