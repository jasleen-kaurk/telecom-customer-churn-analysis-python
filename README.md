# 📊 Telecom Customer Churn Analysis — Python

## 📌 Project Overview

This project focuses on analyzing **customer churn in the telecom industry using Python**.

The analysis is performed in a Jupyter Notebook using **Pandas, NumPy, Matplotlib, and Seaborn**. The project covers data loading, data quality checking, missing-value handling, data transformation, exploratory data analysis, and visualization of customer churn patterns.

The main goal is to understand customer behavior and identify patterns related to **customer demographics, tenure, contracts, telecom services, and payment methods**.

---

## 🎯 Project Objectives

The objectives of this project are to:

* Explore the structure and quality of the telecom customer dataset.
* Check for missing values and data types.
* Clean and prepare the dataset for analysis.
* Analyze overall customer churn.
* Study churn according to gender.
* Analyze churn based on senior-citizen status.
* Explore customer tenure.
* Analyze churn across different contract types.
* Compare churn across telecom services.
* Analyze churn according to payment methods.
* Generate meaningful insights from the customer data.

---

## 🛠️ Tools & Technologies

| Tool / Library   | Purpose                        |
| ---------------- | ------------------------------ |
| Python           | Data analysis                  |
| Pandas           | Data cleaning and manipulation |
| NumPy            | Numerical operations           |
| Matplotlib       | Data visualization             |
| Seaborn          | Statistical visualization      |
| Jupyter Notebook | Analysis environment           |

---

## 📂 Dataset

**Dataset:** `telecom_customer.csv`

The dataset contains:

* **7,043 customers**
* **21 columns**
* Customer demographic information
* Telecom service information
* Contract information
* Payment-method information
* Churn information

### Important columns

```text
customerID
gender
SeniorCitizen
Partner
Dependents
tenure
PhoneService
MultipleLines
InternetService
OnlineSecurity
OnlineBackup
DeviceProtection
TechSupport
StreamingTV
StreamingMovies
Contract
PaperlessBilling
PaymentMethod
MonthlyCharges
TotalCharges
Churn
```

---

## 🧹 Data Cleaning

The notebook first checks the dataset structure using:

```python
df.shape
df.info()
df.isnull().sum()
```

There are **11 missing values in `TotalCharges`**.

These missing values are handled using the median:

```python
df['TotalCharges'] = df['TotalCharges'].fillna(
    df['TotalCharges'].median()
)
```

The notebook also transforms the `SeniorCitizen` column from `0/1` into `yes/no` labels.

---

## 📈 Overall Churn Analysis

The dataset contains:

| Customer Status | Customers |
| --------------- | --------: |
| Retained        |     5,174 |
| Churned         |     1,869 |
| Total           |     7,043 |

The overall churn rate is approximately:

**26.54%**

The notebook uses both a **count plot** and a **pie chart** to visualize the churn distribution.

---

## 👥 Customer Churn by Gender

The notebook compares customer churn between female and male customers.

| Gender | Churned |
| ------ | ------: |
| Female |     939 |
| Male   |     930 |

The analysis notes that **female customers have slightly higher churn than male customers** in this dataset.

---

## 👴 Customer Churn by Senior Citizen

Customer churn is also analyzed according to `SeniorCitizen`.

The notebook converts:

```text
0 → no
1 → yes
```

The analysis compares churn between senior-citizen and non-senior-citizen customers using Seaborn count plots.

---

## ⏳ Customer Tenure Analysis

Customer tenure represents the length of time customers have been associated with the telecom service.

A histogram with churn as a grouping variable is used to visualize tenure.

The dataset shows a clear difference in average tenure:

| Customer Status | Average Tenure |
| --------------- | -------------: |
| Retained        |   37.57 months |
| Churned         |   17.98 months |

This indicates that churned customers, on average, have been associated with the service for a shorter period than retained customers.

---

## 📄 Customer Churn by Contract

Contract type is analyzed using a count plot.

| Contract Type  | Churned Customers |
| -------------- | ----------------: |
| Month-to-month |             1,655 |
| One year       |               166 |
| Two year       |                48 |

### Key observation

**Month-to-month customers represent the largest number of churned customers.**

This makes contract type an important area to investigate when developing customer-retention strategies.

---

## 📞 Telecom Service Analysis

The notebook creates a **3 × 3 grid of count plots** to analyze churn across different telecom services.

The analyzed columns are:

```text
PhoneService
MultipleLines
InternetService
OnlineSecurity
OnlineBackup
DeviceProtection
TechSupport
StreamingTV
StreamingMovies
```

Each visualization compares service categories based on:

```text
Churn = Yes
Churn = No
```

This allows customer churn patterns to be explored across multiple service offerings.

---

## 💳 Churn by Payment Method

The project also analyzes churn according to payment method.

| Payment Method            | Churned Customers |
| ------------------------- | ----------------: |
| Electronic check          |             1,071 |
| Mailed check              |               308 |
| Bank transfer (automatic) |               258 |
| Credit card (automatic)   |               232 |

### Key observation

The analysis shows that **electronic check has the highest number of churned customers**.

---

## 🔍 Key Insights

Based on the actual dataset and notebook analysis:

* **26.54%** of customers have churned.
* There are **1,869 churned customers** out of **7,043 customers**.
* **Month-to-month contracts** have the highest number of churned customers.
* **Electronic check** has the highest churn count among payment methods.
* Churned customers have a much lower average tenure than retained customers.
* Female customers have a slightly higher churn count than male customers.
* Churn is explored across multiple telecom services including internet, security, backup, device protection, technical support, and streaming services.

---

## 🔄 Project Workflow

```text
Raw Telecom Dataset
        ↓
Import Python Libraries
        ↓
Load CSV Dataset
        ↓
Check Shape & Data Types
        ↓
Check Missing Values
        ↓
Handle Missing Data
        ↓
Transform Data
        ↓
Exploratory Data Analysis
        ↓
Create Visualizations
        ↓
Analyze Churn Patterns
        ↓
Generate Insights
```

---

## 📊 Visualizations Created

The notebook includes:

* Customer churn count plot
* Customer churn pie chart
* Churn by gender
* Churn by senior-citizen status
* Senior-citizen distribution
* Dependents distribution
* Partner distribution
* Tenure distribution by churn
* Churn by contract type
* 3 × 3 telecom service churn analysis
* Churn by payment method

---

## 📁 Repository Structure

```text
telecom-customer-churn-analysis-python/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   └── telecom_customer.csv
│
├── notebooks/
│   └── telecom_customer_churnanalysis.ipynb
│
└── screenshots/
    └── telecom-churn-analysis.png
```

---

## ▶️ How to Run

### Clone the repository

```bash
git clone https://github.com/jasleen-kaurk/telecom-customer-churn-analysis-python.git
```

### Install required libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Open Jupyter Notebook

```bash
jupyter notebook
```

Then open:

```text
telecom_customer_churnanalysis.ipynb
```

Make sure the CSV dataset is available at the path used by the notebook:

```python
df = pd.read_csv(r'telecom_customer.csv')
```

---

## 🧠 Skills Demonstrated

This project demonstrates practical knowledge of:

* Python
* Pandas
* NumPy
* Data Cleaning
* Missing-Value Handling
* Exploratory Data Analysis
* Matplotlib
* Seaborn
* Data Visualization
* Customer Churn Analysis
* Business Insights

---

## 🚀 Future Improvements

The project can be extended by:

* Building a Power BI dashboard.
* Creating customer segments.
* Developing a machine-learning churn prediction model.
* Predicting individual customer churn probability.
* Performing deeper statistical analysis.
* Analyzing customer lifetime value and revenue impact.

---

## 👩‍💻 Author

**Jasleen Kaur**

**Aspiring Data Analyst**

`Python | SQL | Power BI | Data Analytics | Data Visualization`

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐.

**Thank you for visiting this project!**
