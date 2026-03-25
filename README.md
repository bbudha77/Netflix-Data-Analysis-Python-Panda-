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

## 🔍 Key Code Examples and Outputs

### 📌 1. Movies vs TV Shows

```python
df['type'].value_counts()



*Output*

type
Movie      5943
TV Show     230
Name: count, dtype: int64
```
---

### 📌 2. Top 10 Countries Producing Netflix Titles

```python
df['country'].value_counts().head(10)


*Output*

country
United States     2048
India              890
Unknown            422
United Kingdom     212
Canada             119
Spain              106
Egypt               90
Nigeria             90
Japan               85
France              81
Name: count, dtype: int64

```
---

### 📌 3. Ratings Distribution

```python
df['rating'].value_counts().head(10)


*Output*

rating
TV-MA    2117
TV-14    1457
R         795
TV-PG     538
PG-13     489
PG        286
TV-Y7     132
TV-G      118
TV-Y      112
NR         75
Name: count, dtype: int64
```
---

### 📌 4. Titles Released Per Year

```python
df.groupby('release_year')['title'].count().sort_values(ascending=False).head(10)


*Output*

release_year
2017    773
2018    760
2016    653
2019    629
2020    548
2015    400
2021    297
2014    267
2013    225
2012    175
Name: title, dtype: int64
```
---

### 📌 5. Titles Per Year by Type (Movie vs TV Show)

```python
df.groupby(['release_year', 'type'])['title'].count().head(10)


*Output*

release_year  type   
1942          Movie      2
1943          Movie      3
1944          Movie      3
1945          Movie      3
1946          Movie      1
              TV Show    1
1947          Movie      1
1954          Movie      2
1955          Movie      3
1956          Movie      2
1958          Movie      3
1959          Movie      1
1960          Movie      4
1961          Movie      1
1962          Movie      3
1963          Movie      1
1964          Movie      2
1965          Movie      2
1966          Movie      1
1967          Movie      4
Name: title, dtype: int64

```
---

### 📌 6. Min, Max and Mean Release Year by Country
```python
df.groupby('country').agg({
'title': 'count',
'release_year': ['min', 'max']   
}).sort_values(('title','count'), ascending = False).head(10)

*Output*

	title	release_year
count	min	max
country			
United States	2048	1942	2021
India	890	1959	2021
Unknown	422	1960	2021
United Kingdom	212	1975	2021
Canada	119	1998	2020
Spain	106	2008	2021
Nigeria	90	2003	2021
Egypt	90	1954	2020
Japan	85	1979	2021
France	81	1974	2021

```


## 📈 Key Summary of Insights

- Netflix has significantly more *Movies* than TV Shows.
- *TV‑MA* is the most common rating across the platform.
- The *United States, **India, and the **United Kingdom* produce the highest number of titles.
- Content production increased sharply after *2015*, showing Netflix’s global expansion.
- Genres such as *Dramas, **Comedies, and **International Movies* dominate the catalog.
- Groupby analysis reveals clear patterns in content growth and country‑level contributions.
- Filtering operations helped identify trends such as:
  - Movies released after 2015  
  - Titles produced in India  
  - Non‑US content  
  - Year‑wise and type‑wise distribution  

---

## 🛠️ Tools & Technologies Used

- *Python*
- *Pandas*
- *Jupyter Notebook*
- *Data Cleaning & Wrangling*
- *Exploratory Data Analysis (EDA)*
- *Groupby & Aggregations*
- *Markdown Documentation*

---
