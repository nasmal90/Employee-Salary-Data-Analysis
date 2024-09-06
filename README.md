# 📊 Employee Salary Data Analysis

## 📝 Introduction
This project delves into the salary data of employees in San Francisco, analyzing trends and relationships between job titles, base pay, overtime, and other factors. By leveraging Python and popular data science libraries, the analysis uncovers key insights from the data to help understand salary patterns.

## 🎯 Objective
The main objectives of this project include:
- 🔄 **Data Cleaning**: Handling missing values and formatting categorical data.
- 📈 **Salary Trends Analysis**: Identifying the highest, lowest, and average base pay across various departments.
- 📊 **Data Visualization**: Creating interactive visualizations to highlight patterns in salary, overtime, and job titles.

## 🔧 Tools Used
- **Python**: The core language used for data analysis.
- **Pandas**: For data manipulation and cleaning.
- **NumPy**: For numerical computations.
- **Matplotlib & Seaborn**: For creating insightful visualizations.

## 📂 Dataset Overview
The dataset provides key salary information for employees in San Francisco, including:
- **Base Pay**: The base salary earned by the employee.
- **Overtime Pay**: Additional salary from overtime work.
- **Job Title**: The role or designation of the employee.
- **Employee Name**: Identifying information for each employee.

---

## 🚀 Key Steps in the Analysis

### 1️⃣ Loading and Cleaning the Data
The dataset is loaded into a Pandas DataFrame, followed by handling missing data to ensure clean, usable information.

```python
import pandas as pd

# Load the dataset
data = pd.read_csv('data/employee_salaries.csv')

# Checking for missing data
missing_data = data.isnull().sum()
print(missing_data)

# Dropping rows with missing data
data_cleaned = data.dropna()
```
### 2️⃣ Descriptive Statistics
We calculate basic statistics to better understand the distribution of salary data.
```
# Descriptive statistics for numerical columns
data_cleaned.describe()

# Calculating base pay metrics
average_base_pay = data_cleaned['BasePay'].mean()
max_base_pay = data_cleaned['BasePay'].max()
min_base_pay = data_cleaned['BasePay'].min()

print(f"Average Base Pay: ${average_base_pay}")
print(f"Max Base Pay: ${max_base_pay}")
print(f"Min Base Pay: ${min_base_pay}")
```
### 3️⃣ Most Common Job Titles
We examine the most frequent job titles to identify prevalent roles.
```
# Top 10 most common job titles
top_jobs = data_cleaned['JobTitle'].value_counts().head(10)
print(top_jobs)
```
### 4️⃣ Overtime Pay Analysis
We analyze overtime earnings to observe patterns in additional income.
```
# Calculating the average overtime pay
average_overtime_pay = data_cleaned['OvertimePay'].mean()
print(f"Average Overtime Pay: ${average_overtime_pay}")
```
### 5️⃣ Data Visualizations
We visualize salary trends using plots.

📉 Scatter Plot: Base Pay vs Overtime Pay
```
import matplotlib.pyplot as plt

plt.scatter(data_cleaned['BasePay'], data_cleaned['OvertimePay'])
plt.title('Base Pay vs Overtime Pay')
plt.xlabel('Base Pay ($)')
plt.ylabel('Overtime Pay ($)')
plt.show()
```
📊 Bar Chart: Top 10 Job Titles
```
top_jobs.plot(kind='bar', color='skyblue')
plt.title('Top 10 Job Titles')
plt.xlabel('Job Title')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.show()
```
🔥 Correlation Heatmap
```
import seaborn as sns

corr_matrix = data_cleaned.corr()
sns.heatmap(corr_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Matrix')
plt.show()
```
## 📈  Results & Insights
- Highest Base Pay: 💰 The highest base pay recorded is $320,000.
- Lowest Base Pay: 🔻 The lowest base pay recorded is $20,000.
- Most Common Job Titles: "Police Officer" and "Firefighter" are among the most frequent job titles, with high overtime earnings.
- Average Base Pay: The overall average base pay is approximately $90,000, revealing disparities between job titles and departments.
## 🔮 Future Enhancements
- Potential improvements for this project include:
- Analysis of Additional Factors: Expanding the dataset to analyze benefits, bonuses, and total compensation.
- Predictive Modeling: Building machine learning models to predict future salary trends based on job titles and pay history.
- Interactive Dashboards: Utilizing libraries like Plotly or Dash for a dynamic, user-friendly visualization experience.
