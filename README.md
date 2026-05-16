# python-pandas-numpy-analysis
Python program using Pandas and NumPy to load CSV datasets, clean missing values, calculate summary statistics, and perform simple data analysis.
#Name,Math,Science,English
Deepak,85,90,88
Rahul,78,,82
Sneha,92,89,95
Kiran,70,75,
import pandas as pd
import numpy as np

# Load CSV dataset
data = pd.read_csv("students.csv")

print("Original Dataset:\n")
print(data)

# Cleaning missing values
data.fillna(data.mean(numeric_only=True), inplace=True)

print("\nDataset After Cleaning Missing Values:\n")
print(data)

# Summary Statistics
print("\nSummary Statistics:\n")
print(data.describe())

# Simple Data Analysis
print("\nAverage Math Marks:", np.mean(data["Math"]))
print("Highest Science Marks:", np.max(data["Science"]))
print("Lowest English Marks:", np.min(data["English"]))

# Add Total Marks Column
data["Total"] = data["Math"] + data["Science"] + data["English"]

print("\nDataset With Total Marks:\n")
print(data)
