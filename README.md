
# Titanic Data Analysis

This project is a data exploration and visualization analysis of the Titanic dataset, focusing on understanding survival rates based on different features like age, gender, and other relevant attributes.

## Overview

The Titanic dataset provides details about the passengers on the Titanic, such as their age, gender, passenger class, and whether they survived. The purpose of this analysis is to explore the data, visualize patterns, and gain insights into factors that influenced survival rates.

## Dataset

- **Source**: [Titanic Dataset from Kaggle](https://www.kaggle.com/c/titanic/data)
- **File Used**: `gender_submission.csv`

## Requirements

1. **Python Libraries**:
   ```bash
   pip install pandas matplotlib seaborn
   ```

## Steps and Code

1. **Data Loading and Overview**:
   - Load the dataset to understand its structure.
   - Inspect for any missing values and basic statistics.

   ```python
   import pandas as pd

   # Load the dataset
   df = pd.read_csv('/content/gender_submission.csv')
   print(df.head())  # Display first few rows
   print(df.isnull().sum())  # Check for missing values
   print(df.describe())  # Statistical summary of numerical columns
   ```

2. **Data Cleaning**:
   - Remove duplicates if any exist.
   - Handle missing values, either by filling them or dropping rows/columns.

3. **Exploratory Data Analysis (EDA)**:
   - **Survival Count**: Visualize the distribution of survival to understand overall survival rates.
   - **Survival by Gender**: Analyze the survival rate of male and female passengers.
   - **Age Distribution**: Plot the age distribution to examine the age range of passengers.
   - **Correlation Analysis**: Display a heatmap to identify correlations between numerical features.
   - **Pairplot**: Visualize pairwise relationships in the dataset, segmented by survival status.

   ```python
   import matplotlib.pyplot as plt
   import seaborn as sns

   # Survival Count
   sns.countplot(data=df, x='Survived')
   plt.title('Survival Count')
   plt.show()

   # Survival by Gender
   sns.countplot(data=df, x='Sex', hue='Survived')
   plt.title('Survival by Gender')
   plt.show()

   # Age Distribution
   sns.histplot(df['Age'], bins=20, kde=True)
   plt.title('Distribution of Age')
   plt.show()

   # Correlation Heatmap
   sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
   plt.title('Correlation Heatmap')
   plt.show()

   # Pairplot
   sns.pairplot(df, hue='Survived', diag_kind='kde')
   plt.show()
   ```

4. **Insights**:
   - **Basic Statistics**: Provides an overview of the dataset’s structure.
   - **Survival Trends**: Helps identify patterns like higher survival rates for females.
   - **Correlation Heatmap**: Highlights relationships among numerical features, assisting in identifying significant variables.

## Results

- **Overall Survival**: Initial analysis of survival rates shows the general likelihood of survival across the entire dataset.
- **Gender-Based Survival**: Visualization of gender-based survival highlights key patterns, showing a higher survival rate among females.
- **Age Distribution**: Analysis of age demographics helps to determine if age influenced survival.
- **Feature Correlations**: Identifying correlations between features allows for a better understanding of factors that may have influenced survival.

---

