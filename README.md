House Price Prediction - Data Cleaning and Preprocessing
Overview
This project is the first step in a machine learning pipeline for predicting house prices in Bengaluru, India. It focuses on data cleaning and preprocessing of a real-world dataset containing property details. The goal is to prepare the dataset for building accurate price prediction models by handling missing values, converting data types, and creating new features.

This project is part of a video tutorial series on machine learning projects.

Features
Loads the Bengaluru house price dataset.

Performs exploratory data analysis (EDA) to understand data distribution.

Cleans the data by dropping irrelevant columns and handling missing values.

Extracts new features such as the number of bedrooms (BHK) from textual data.

Converts property size ranges into single numeric values for consistent analysis.

Identifies and removes outliers and erroneous data.

Visualizes data distributions to aid understanding.

Saves the cleaned dataset for downstream machine learning tasks.

How It Works
The script reads the raw dataset from a CSV file.

It drops columns that are not useful for price prediction.

Missing values are removed to ensure data quality.

The 'size' column is processed to extract the number of bedrooms (BHK).

The 'total_sqft' column, which sometimes contains ranges (e.g., "2100-2850"), is converted into an average numeric value.

Data with invalid or inconsistent size entries are removed.

A histogram of the BHK distribution is plotted to visualize the dataset.

Finally, the cleaned dataset is saved as a new CSV file for further use.

Requirements
Python 3.6 or higher

pandas

numpy

matplotlib

Jupyter Notebook or any Python IDE (optional for running interactively)

You can install the required packages via pip:

bash
Copy
Edit
pip install pandas numpy matplotlib
