{\rtf1\ansi\ansicpg1252\cocoartf2761
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fswiss\fcharset0 Helvetica;}
{\colortbl;\red255\green255\blue255;}
{\*\expandedcolortbl;;}
\paperw11900\paperh16840\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\fs24 \cf0 # Employee Salary Data Analysis\
\
## Introduction\
This project analyzes the salary data of employees in San Francisco, uncovering trends and relationships between various factors such as job titles, base pay, and overtime. The analysis uses Python and popular data science libraries to derive insights from the data.\
\
## Objective\
The main objectives of this project include:\
- **Data Cleaning:** Handling missing values and formatting categorical columns.\
- **Analyzing Salary Trends:** Exploring the highest, lowest, and average base pay across departments.\
- **Data Visualization:** Creating informative plots to show patterns in job titles, base pay, and overtime.\
\
## Tools Used\
- **Python:** Main programming language for data analysis.\
- **Pandas:** For data cleaning and manipulation.\
- **NumPy:** For numerical operations.\
- **Matplotlib & Seaborn:** For creating visualizations.\
\
## Dataset\
The dataset contains salary information for employees in San Francisco, including:\
- **Base Pay:** The base salary of the employee.\
- **Overtime Pay:** Any overtime salary earned.\
- **Job Title:** The employee's job position.\
- **Employee Name:** The name of the employee.\
\
## Key Steps in the Analysis\
\
### 1. Loading and Cleaning the Data\
We loaded the dataset using Pandas and checked for missing values:\
\
```python\
import pandas as pd\
\
# Load the dataset\
data = pd.read_csv('data/employee_salaries.csv')\
\
# Check for missing data\
missing_data = data.isnull().sum()\
print(missing_data)\
\
# Drop rows with missing data if necessary\
data = data.dropna()\
```\
\
### 2. Descriptive Statistics\
We calculated basic statistics for key salary-related fields:\
\
```python\
# Get basic statistics for the numerical columns\
data.describe()\
\
# Calculate average, maximum, and minimum base pay\
average_base_pay = data['BasePay'].mean()\
max_base_pay = data['BasePay'].max()\
min_base_pay = data['BasePay'].min()\
\
print(f"Average Base Pay: \{average_base_pay\}")\
print(f"Max Base Pay: \{max_base_pay\}")\
print(f"Min Base Pay: \{min_base_pay\}")\
```\
\
### 3. Most Common Job Titles\
We explored the most common job titles:\
\
```python\
# Most common job titles\
top_jobs = data['JobTitle'].value_counts().head(10)\
print(top_jobs)\
```\
\
### 4. Overtime Pay Analysis\
The average overtime pay was calculated to identify patterns in overtime earnings:\
\
```python\
# Average Overtime Pay\
average_overtime_pay = data['OvertimePay'].mean()\
print(f"Average Overtime Pay: \{average_overtime_pay\}")\
```\
\
### 5. Visualizations\
\
- **Scatter Plot: Base Pay vs Overtime Pay**\
    ```python\
    plt.scatter(data['BasePay'], data['OvertimePay'])\
    plt.title('Base Pay vs Overtime Pay')\
    plt.xlabel('Base Pay')\
    plt.ylabel('Overtime Pay')\
    plt.show()\
    ```\
\
- **Bar Chart for Job Titles**\
    ```python\
    top_jobs.plot(kind='bar')\
    plt.title('Top 10 Job Titles')\
    plt.xlabel('Job Title')\
    plt.ylabel('Count')\
    plt.show()\
    ```\
\
- **Correlation Heatmap**\
    ```python\
    corr_matrix = data.corr()\
    sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')\
    plt.title('Correlation Matrix')\
    plt.show()\
    ```\
\
## Results & Insights\
- The **highest base pay** identified in the dataset was $320,000, while the **lowest base pay** was $20,000.\
- **Job Titles:** The most common job titles included "Police Officer" and "Firefighter," with high overtime earnings.\
- **Average Base Pay:** The overall average base pay across all departments was approximately $90,000.\
}