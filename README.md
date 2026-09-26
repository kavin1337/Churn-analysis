# Churn-analysis
Churn analysis using Python, SQLite, Pandas, NumPy, Matplotlib, and Seaborn, covering data cleaning, feature engineering, EDA, KPI analysis, and visualization

📌 Project Overview
This project performs Customer Churn Data Analysis using Python and SQLite. The project covers the complete data analysis workflow, starting from SQL database connection and data import to data cleaning, feature engineering, exploratory data analysis (EDA), KPI calculation, and data visualization.
The analysis integrates customer, subscription, and support data to identify customer churn patterns and generate meaningful analytical insights.
________________________________________
🛠️ Technologies Used
•	Python
•	SQLite / sqlite3
•	SQL
•	Pandas
•	NumPy
•	Matplotlib
•	Seaborn
•	Jupyter Notebook
________________________________________
🔄 Project Workflow
SQLite Database
       ↓
SQL Queries + sqlite3
       ↓
Data Import using Pandas
       ↓
Data Cleaning & Quality Checks
       ↓
Data Integration / Merging
       ↓
Feature Engineering
       ↓
Exploratory Data Analysis
       ↓
KPI & Aggregation Analysis
       ↓
Data Visualization
       ↓
CSV Export
________________________________________
📂 Dataset
The project works with three main datasets:
•	Customer Data
•	Subscription Data
•	Support Data
The datasets are connected using customerid.
________________________________________
🔌 SQL Database Connection
The SQLite database is connected to Python using sqlite3.
import sqlite3

conn = sqlite3.connect("customer_churn.db")
SQL queries are executed through Pandas to import database tables into DataFrames.
df = pd.read_sql("SELECT * FROM table_name", conn)
________________________________________
🧹 Data Cleaning
The project performs several data-cleaning operations using Pandas and NumPy.
Data Cleaning Tasks
•	Data type conversion
•	Column selection and removal
•	Column standardization
•	Text formatting
•	Missing/null value handling
•	Data quality checks
•	Duplicate handling
•	Date conversion
•	Dataset validation
Examples include:
df['dob'] = pd.to_datetime(df['dob'])
df['name'] = df['name'].str.title()
Missing country values are handled using state-to-country mapping.
________________________________________
⚙️ Feature Engineering
New analytical features are created using Pandas and NumPy.
Features Created
•	churn_flag
•	complaint_count
•	tenure_days
•	escalations
•	churn_risk
Example:
df['churn_flag'] = np.where(
    df['cancellation_date'].notna(), 1, 0
)
Churn risk is categorized into:
•	Low
•	Medium
•	High
based on the churn score.
________________________________________
📊 Exploratory Data Analysis
The project performs EDA using Pandas and NumPy.
Analysis Includes
•	KPI calculation
•	Groupby analysis
•	Aggregation
•	Pivot tables
•	Churn analysis
•	Customer segmentation
•	Revenue analysis
•	Tenure analysis
•	Complaint analysis
•	Escalation analysis
•	Correlation analysis
________________________________________
📈 Key Results
Metric	Result
Total Customer Records	21
Churn Rate	28.57%
Retention Rate	71.43%
Average Monthly Charges	18.85
Average Tenure	1535.14 days
Revenue Loss from Churned Customers	73.94
Escalation Rate	14.29%
Escalation vs Churn Correlation	0.65
Churn by Plan
Plan Type	Churn Rate
Basic	60.00%
Premium	14.29%
Standard	22.22%
________________________________________
📊 Data Visualization
The project uses Matplotlib and Seaborn for visualization.
Visualizations Created
•	Monthly churn trend
•	Churn by plan type
•	Correlation heatmap
•	Pairplot
•	Monthly charges by plan, gender, and churn risk
Example Visualization
plt.plot(
    churn_trend.index.astype('str'),
    churn_trend.values,
    marker='o'
)

plt.title('Churn Monthly Trend')
plt.xlabel('Monthly')
plt.ylabel('Churned Customers')
plt.show()
Seaborn is also used for correlation and multidimensional analysis.
sns.heatmap(
    df_encoded.corr(),
    annot=True
)
________________________________________
📁 Project Structure
Customer-Churn-Data-Analysis/
│
├── datasets
	├──raw data
	├──cleaned date
├── Scripts
	├──churn_analysis.ipynb
├── Report
	├──churn_analysis_report
├── doc
	├──database table
└── README.md
________________________________________
📤 Data Export
The final processed dataset is exported as a CSV file.
df.to_csv(
    'exported_churn_data.csv',
    index=False
)
________________________________________
🎯 Skills Demonstrated
•	SQL database connectivity
•	SQLite
•	Python
•	Pandas
•	NumPy
•	Data cleaning
•	Data preprocessing
•	Missing-value handling
•	Data quality checks
•	Feature engineering
•	Data transformation
•	Filtering
•	Groupby and aggregation
•	Pivot tables
•	Exploratory Data Analysis
•	KPI analysis
•	Data visualization
•	Matplotlib
•	Seaborn
•	Data export
________________________________________
📄 Project Report
A detailed project report containing the methodology, results, graphs, and analysis is included in:
Customer_Churn_Data_Analysis_Report.docx
________________________________________
👨‍💻 Project Summary
This project demonstrates an end-to-end Python data analysis workflow, from extracting data from a SQLite database to cleaning, transforming, analyzing, visualizing, and exporting the final customer churn dataset.


