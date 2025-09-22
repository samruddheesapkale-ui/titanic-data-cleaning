# titanic-data-cleaning
Data cleaning and preprocessing of Titanic dataset using Python.

📌 Project Overview
This project focuses on data cleaning and preprocessing of the Titanic dataset. The goal is to transform the raw dataset into a structured and ready-to-use form for analysis and machine learning.
Two cleaned datasets are provided:

1) titanic_cleaned.csv → full version with all features (raw + engineered).

2) titanic_cleaned_slim.csv → slim version with only clean, useful columns (ready for modeling).

🛠️ Steps Performed

1. Data Loading
Loaded the dataset (Titanic-Dataset.csv) into Python using pandas.

2. Cleaning Text Columns
Converted Sex values to lowercase (male, female).
Standardized Embarked values to uppercase (C, Q, S).

3. Handling Missing Values
Age → filled missing values with median age.
Embarked → filled missing values with mode (most frequent value).
Cabin → extracted the deck letter (e.g., C85 → C). Missing decks marked as U (Unknown).

4. Feature Engineering
FamilySize = SibSp + Parch + 1
IsAlone = 1 if passenger has no family, else 0
Title extracted from passenger names (Mr, Mrs, Miss, Master, Rare)
AgeBin created by grouping ages into bins (0–10, 11–20, ..., 60+)

5. Encoding Categorical Variables
Sex → converted to numeric (male=1, female=0).
Applied one-hot encoding to:
Embarked (C, Q, S)
Title
Cabin_deck
AgeBin

6. Outlier Treatment
Detected outliers in Fare using the IQR (Interquartile Range) method.
Applied capping (winsorization): extreme values were replaced with upper/lower IQR bounds.

7. Feature Scaling
Applied StandardScaler (z-score) to numeric features:
Age_filled → Age_z
Fare_capped → Fare_z
FamilySize → FamilySize_z

8. Final Dataset Preparation
Full dataset (titanic_cleaned.csv): contains all original + engineered columns.
Slim dataset (titanic_cleaned_slim.csv): contains only:
PassengerId, Survived, Pclass, Sex_num, Age_filled, Fare_capped, FamilySize, IsAlone, scaled features, and one-hot encodings.
✅ 0 missing values, ready for machine learning.

📂 Files in this Repository
Titanic-Dataset.csv → original raw dataset.
titanic_cleaned.csv → fully cleaned dataset with all features.
titanic_cleaned_slim.csv → slimmed, modeling-ready dataset.
README.md → this file (project documentation).

📊 Quick Insights from Cleaned Data
Sex & Survival → females had higher survival rates.
Pclass & Survival → higher-class passengers (1st class) had higher survival rates.
FamilySize → small families had better survival odds than passengers traveling alone.

🚀 Next Steps

With the cleaned dataset, you can:
Build ML models (e.g., Logistic Regression, Random Forest).
Perform EDA (exploratory data analysis) with plots.
Compare feature importance and survival patterns.

✨ Author: Samruddhee Sapkale
📅 Date: 22=09-2025


