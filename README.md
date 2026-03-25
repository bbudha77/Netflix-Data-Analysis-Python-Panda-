# 📊 Netflix Titles Data Analysis (Python + Pandas)

## 📌 Overview

In this project, I performed an exploratory data analysis (EDA) on the Netflix Movies and TV Shows dataset using Python and Pandas.

My objective was to uncover patterns and insights related to Netflix content, including:

- Distribution of Movies vs TV Shows  
- Release year trends  
- Country-wise content production  
- Ratings distribution  
- Genre patterns  
- GroupBy aggregations  
- Filtering and data cleaning  

This project helped me strengthen my skills in data cleaning, data manipulation, and exploratory analysis using real-world data.

---

## 📁 Dataset

I used the *Netflix Movies and TV Shows* dataset, which is publicly available on Kaggle.

- *Source:* Kaggle (Public Dataset)  
- *Contents:* Title, type, director, cast, country, rating, release year, genre, and more
- *Link:*https://www.kaggle.com/datasets/padmapriyatr/netflix-titles

---

## 🧠 What I Did (Step-by-Step)

### 1. Data Loading
- Imported Pandas  
- Loaded the dataset into a DataFrame  
- Explored structure, shape, and data types  

### 2. Data Cleaning
- Removed duplicate records  
- Handled missing values  
- Standardized text columns  
- Cleaned country, rating, and date_added fields  
- Converted columns into proper data types  

### 3. Exploratory Data Analysis
I analyzed:
- Movies vs TV Shows distribution  
- Most common ratings  
- Popular genres  
- Top contributing countries  

### 4. Data Filtering
Used filtering techniques to extract insights such as:
- Movies released after 2015  
- Content produced in India  
- Non-US productions  
- Year-based filtering  

### 5. GroupBy & Aggregations
Applied groupby() and aggregation functions to compute:
- Titles per country  
- Titles per rating  
- Titles per release year  
- Content distribution by type per year  
- Earliest and latest release year per country  

### 6. Insight Summary
Summarized key findings at the end of the notebook for better interpretation.

---

## 🔍 Key Code Examples

### Movies vs TV Shows
```python
df['type'].value_counts()
