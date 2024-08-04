# Sales_Analysis
## Overview
The goal of this project is to improve customer experience by analyzing sales data to increase sales revenue. We will use Python and its popular libraries such as `Pandas`, `NumPy`, and `Matplotlib` to analyze the sales data and gain insights.
## Features
- `Data Cleaning`: Clean and preprocess the sales data to remove any inconsistencies or missing values.
- `Data Analysis`: Analyze the sales data to identify trends, patterns, and correlations.
- `Visualization`: Visualize the sales data to gain insights and make informed decisions.
## Pre-requisites
- Python: Python 3.x installed on your system.
- Pandas: `Pandas` library installed (pip install pandas).
- NumPy: `NumPy` library installed (pip install numpy).
- Matplotlib: `Matplotlib` library installed (pip install matplotlib).
- Sales Data: A CSV file containing sales data.
## Usage
- Import Libraries: Import the required libraries.
- Load Data: Load the sales data from the CSV file.
- Clean Data: `Clean` and preprocess the sales data.
- Analyze Data: `Analyze` the sales data to identify trends, patterns, and correlations.
- Visualize Data: `Visualize` the sales data to gain insights.
- Provide Recommendations: Provide recommendations to improve customer experience and increase sales revenue.
## Code Explanation
### Import Libraries
```ruby
'import' pandas 'as' pd
'import' numpy 'as' np
'import' matplotlib.pyplot 'as' plt
```
### Load Data (from CSV file)
```ruby
df = pd.read_csv('Diwali Sales Data.csv', encoding= 'unicode_escape')
```
### Clean Data
- Drop unnecessary data(blank columns)
  ```ruby
  df.drop(['Status', 'unnamed1'], axis=1, inplace=True)
  ```
  - Check for null values
  ```ruby
  pd.isnull(df).sum()
  ```
- Drop null values
```ruby
df.dropna(inplace=True)
```
- Change data type
```ruby
df['Amount'] = df['Amount'].astype('int')
```
### Analyze Data
- Calculate highest and the lowest numbers using the following(Age,	Orders,	Amount) using `describe` function 
```ruby
df[['Age', 'Orders', 'Amount']].describe()
```
- Calculate total amount/sales from top 10 states
```ruby
sales_state = df.groupby(['State'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False).head(10)
```
- Calculate most buyers from different age groups
```ruby
sales_age = df.groupby(['Age Group'], as_index=False)['Amount'].sum().sort_values(by='Amount', ascending=False)
```
### Visualize Data
- Plot major gender purchasing power
```ruby
sns.barplot(data = sales_state, x = 'Marital_Status',y= 'Amount', hue='Gender')
<Axes: xlabel='Marital_Status', ylabel='Amount'>
```
- Plot major occupations
```ruby
sns.barplot(data = sales_state, x = 'Occupation',y= 'Amount', hue='Occupation')
<Axes: xlabel='Occupation', ylabel='Amount'>
```
