# Data-cleaning-Task_1
This repository is for Data cleaning on messy data file

File: raw_messy_dataset.csv

Description: A raw dataset with missing values, inconsistent data formats, and outliers.



1. 📦 Importing Libraries
   
				import pandas as pd
				import numpy as np
				import seaborn as sns
				import matplotlib.pyplot as plt

   		These libraries are essential for data manipulation (pandas, numpy) and visualization (seaborn, matplotlib).

3. 📄 Loading the Dataset

				df = pd.read_csv("raw_messy_dataset.csv")
				Load the messy dataset into a DataFrame.

3. ℹ️ Basic Data Information

				df.info()
				df.describe()
				df.head()
				Initial inspection: types, null values, and summary statistics.

4. 🧼 Handling Missing Values
				Identify null values in the dataset.
				
				Fill or drop them using:
				df['Column_Name'].fillna(value, inplace=True)
				or
				df.dropna(inplace=True)


5. 🗓️ Date Format Standardization
					
					df['Visit Date'] = pd.to_datetime(df['Visit Date'], errors='coerce')
					df['Visit Date'] = df['Visit Date'].dt.strftime('%Y-%m-%d')
					Convert various date formats into a consistent format.

6. 🧹 Cleaning Text/Strings
   
					df['City'] = df['City'].str.strip().str.title()
					Standardize casing and remove extra spaces.

8. 💰 Cleaning Numeric Columns
					df['Treatment Cost'] = pd.to_numeric(df['Treatment Cost'], errors='coerce')
					Convert cost columns to proper numeric types, replacing errors with NaN.

9. 📊 Visualizing the Data
					sns.heatmap(df.isnull())
					plt.show()
					Use heatmaps and other visual tools to inspect data quality.

10. 🧾 Exporting the Cleaned Data
					df.to_csv("cleaned_dataset.csv", index=False)
					Save the final cleaned data for further analysis or use.

✅ Output
Cleaned and well-structured dataset: cleaned_dataset.csv
Issues like missing values, mixed types, and inconsistent formatting are resolved.


