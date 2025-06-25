# Data-cleaning-Task_1
This repository is for Data cleaning on messy data file


📁 Dataset

		File used: raw_messy_dataset.csv
		Output file: Cleaned Data (CSV)

🔧 Libraries Used
		
		import pandas as pd
		import numpy as np
		import seaborn as sns
		import matplotlib.pyplot as plt
📝 Steps Performed
1. 📥 Load the Dataset

		df = pd.read_csv("raw_messy_dataset.csv")
		Read the CSV file into a pandas DataFrame for processing.


3. 🔍 Initial Inspection
		
		df.info()
		Use info() to check column types, null values, and overall structure.

5. ❌ Remove Duplicate Rows

		df.duplicated().sum()
		df.drop_duplicates(inplace=True)
		Identify and remove duplicate rows to ensure data accuracy.

7. 🧓 Age Column Cleaning
   
		Convert to numeric, replace invalids with NaN, and fill missing values with median.
		df["Age"] = pd.to_numeric(df["Age"], errors="coerce")
		df["Age"].fillna(df["Age"].median(), inplace=True)
		Convert to numeric and fill missing values using the median.

9. ⚧ Gender Standardization

		Replace inconsistent labels (like 'M', 'F', or blanks) with Male, Female, and None.
		df['Gender'] = df['Gender'].replace({'M': 'Male', 'F': 'Female', ' ': 'None'})
		Replace short or empty entries like 'M', 'F', or blanks with full labels like 'Male', 'Female', and 'None'.


11. 📧 Handle Missing Emails
	
		df['Email'].fillna("-", inplace=True)
			Fill missing email entries with a placeholder "-".

13. 📅 Date Column Formatting
	
		df['Join_Date'] = pd.to_datetime(df['Join_Date'], errors='coerce')
		Convert Join_Date to datetime format.

15. 💸 Salary Column Cleaning
		
		df["Salary"] = pd.to_numeric(df["Salary"], errors="coerce")
		Convert Salary column to numeric, invalid entries become NaN.

17. 🏢 Department Column Imputation
    
		df["Department"].fillna(df["Department"].mode()[0], inplace=True)
		Fill missing department values with the most frequent department.


19. 💾 Save Cleaned Data
	
		df.to_csv("Cleaned Data")
		Cleaned dataset saved as: Cleaned Data (CSV file)

✅ Output
Cleaned dataset saved as: Cleaned Data (CSV file)
Cleaned and well-structured dataset: cleaned_dataset.csv
Issues like missing values, mixed types, and inconsistent formatting are resolved.


