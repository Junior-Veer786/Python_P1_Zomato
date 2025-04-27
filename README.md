# Python_Project_1
# Zomato Restaurant Rating Analysis Project

## Project Overview

**Project Title**: Zomato Restaurant Rating Analysis  
**Dataset**: Zomato Dataset

This project is designed to demonstrate Python data analysis skills and techniques typically used by data analysts to explore, clean, and analyze restaurant data. The project involves setting up a clean dataset, performing exploratory data analysis (EDA), and answering specific business questions through visualizations and insights. This project is ideal for those who are starting their journey in data analysis and want to build a solid foundation in Python, Pandas, and Data Visualization.

## Objectives

- **Set up the Zomato dataset**: Load and clean the Zomato restaurant data.
- **Data Cleaning**: Remove unnecessary columns, handle missing values, and eliminate duplicates.
- **Exploratory Data Analysis (EDA)**: Perform basic exploratory data analysis to understand restaurant ratings, cost trends, and customer preferences.
- **Business Analysis**: Use analysis and visualization to answer specific business questions and derive insights from the restaurant data.

## Project Structure

### 1. Data Setup

- **Data Loading**: The project starts by importing the Zomato dataset into a Pandas DataFrame.
- **Basic Exploration**: Initial inspection using `head()`, `info()`, and `describe()` methods to understand the dataset.

```python
import pandas as pd

df = pd.read_csv('zomato.csv')
df.head()
df.info()
df.describe()
```

### 2. Data Cleaning

- **Dropping Irrelevant Columns**: Columns like `url`, `phone`, `menu_item`, `reviews_list`, and `dish_liked` are dropped to simplify the dataset.
- **Handling Missing Values**: Identified and removed rows with null values.
- **Renaming Columns**: Columns are renamed for better readability.
- **Removing Duplicates**: Ensured the dataset has no duplicate entries.

```python
df.drop(['url', 'phone', 'menu_item', 'reviews_list', 'dish_liked'], axis=1, inplace=True)
df.dropna(inplace=True)
df.drop_duplicates(inplace=True)
df.columns
```

### 3. Data Exploration & Cleaning

- **City-wise Restaurant Count**: Identify cities with the most restaurants.
- **Restaurant Type Analysis**: Examine the most popular types of restaurants.
- **Cuisines Analysis**: Find the most offered cuisines.
- **Cost Analysis**: Understand the distribution of the average cost for two.
- **Rating Distribution**: Analyze how restaurant ratings are distributed.
- **Online Order & Table Booking Analysis**: Study the impact of online order availability and table booking on ratings.

```python
import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10,6))
sns.countplot(x='online_order', data=df)
plt.title('Online Order Availability')
plt.show()
```

### 4. Data Analysis & Findings

The following Python code snippets were developed to answer specific business questions:

**Restaurant count by city:**

```python
df['location'].value_counts().head(10)
```

**Top restaurant types:**

```python
df['rest_type'].value_counts().head(10)
```

**Most popular cuisines:**

```python
df['cuisines'].value_counts().head(10)
```

**Distribution of average cost for two:**

```python
plt.figure(figsize=(10,6))
sns.histplot(df['approx_cost(for two people)'], bins=30, kde=True)
plt.title('Cost Distribution')
plt.show()
```

**Impact of online order on ratings:**

```python
sns.boxplot(x='online_order', y='rate', data=df)
plt.title('Online Order vs Rating')
plt.show()
```

**Table booking availability and ratings:**

```python
sns.boxplot(x='book_table', y='rate', data=df)
plt.title('Table Booking vs Rating')
plt.show()
```

**Top locations with highest number of restaurants:**

```python
top_locations = df['location'].value_counts().head(10)
top_locations.plot(kind='bar', figsize=(10,6))
plt.title('Top Locations with Most Restaurants')
plt.show()
```

## Findings

- **Restaurant Distribution**: Bangalore, Delhi, and Mumbai have the highest number of restaurants listed.
- **Cuisine Popularity**: North Indian, Chinese, and Fast Food are the most popular cuisines among customers.
- **Cost Trends**: Most restaurants fall in the moderate pricing category between ₹300 to ₹800.
- **Online Ordering**: Restaurants offering online ordering tend to have slightly better ratings.
- **Table Booking**: Table booking is more common among restaurants with higher ratings.
- **Ratings Insights**: Majority of the restaurants are rated between 3.0 to 4.5.

## Reports

- **Restaurant Summary**: Overview of restaurant types, cuisines, and their frequencies.
- **Cost and Rating Analysis**: Distribution of costs and their relation to restaurant ratings.
- **Customer Behavior Analysis**: Insights into customer preferences for online ordering and table booking.
- **Top Locations**: Identification of areas with the highest restaurant density.

## Conclusion

This project serves as a comprehensive introduction to Python-based data analysis, covering data cleaning, exploratory data analysis, and visualization. The insights gained from the Zomato data help understand the trends in restaurant ratings, customer preferences, and pricing strategies. It highlights how data-driven decisions can enhance customer satisfaction and business performance in the food industry.

## Author - Junior Veer

Thank you World
