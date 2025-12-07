# Customer Bahevior Data Analytics Project

## 📌 Overview

This project demonstrates an end-to-end **data analytics pipeline**, starting from raw data and ending with business-ready insights and visualizations.

The workflow includes:

1. Loading a dataset in **Python (pandas)**
2. Performing **Exploratory Data Analysis (EDA)**
3. **Cleaning and preprocessing** the data
4. Loading the cleaned data into **MySQL** and running **SQL queries**
5. Building an interactive **Power BI dashboard**
6. Creating a **presentation/report** using **Gamma AI**

> 🔧 You can adapt this project to any business domain (sales, customers, operations, HR, etc.).

---

## 🛠 Tech Stack

* **Programming & Analytics**

  * Python (pandas, numpy, matplotlib, seaborn, etc.)
* **Database**

  * MySQL Server / MySQL Workbench
* **BI & Visualization**

  * Microsoft Power BI Desktop
* **Reporting**

  * Gamma AI (for slide deck / report creation)
* **Others**

  * Jupyter Notebook / VS Code / any IDE

---

## 📂 Project Structure

> Update the paths/names below according to your actual project.

```text
project-root/
│
├── data/
│   ├── raw/
│   │   └── dataset.csv
│   └── processed/
│       └── cleaned_dataset.csv
│
├── notebooks/
│   ├── 01_data_loading_eda.ipynb
│   └── 02_data_cleaning_feature_engineering.ipynb
│
├── sql/
│   └── analysis_queries.sql
│
├── powerbi/
│   └── dashboard.pbix
│
├── reports/
│   └── business_insights_gamma_ai.pptx
│
└── README.md
```

---

## 🚀 Getting Started

### 1. Prerequisites

* **Python** (3.8+)
* **MySQL Server** and **MySQL Workbench** (or any other MySQL client)
* **Power BI Desktop**
* **Gamma AI** account (web-based)

### 2. Python Environment Setup

```bash
# Create virtual environment (optional but recommended)
python -m venv venv

# Activate environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

> If you don’t use `requirements.txt`, install directly: `pip install pandas numpy matplotlib seaborn sqlalchemy mysql-connector-python`.

---

## 📊 Step 1 – Data Loading & EDA (Python)

All Python-based analysis is done in the `notebooks/` folder.

Typical steps covered:

* Importing data using `pandas.read_csv()`
* Inspecting structure (`head()`, `info()`, `describe()`)
* Checking missing values and data types
* Univariate and bivariate analysis (distributions, correlations)
* Basic visualizations (histograms, bar charts, boxplots, etc.)

To run:

1. Open `01_data_loading_eda.ipynb` in Jupyter/VS Code.
2. Run cells in order and review:

   * Data profile
   * Key patterns/trends
   * Initial hypotheses

---

## 🧹 Step 2 – Data Cleaning & Preprocessing

Data cleaning and feature engineering logic is implemented in:
`notebooks/02_data_cleaning_feature_engineering.ipynb`

This includes:

* Handling missing values (imputation / removal)
* Removing duplicates and irrelevant columns
* Fixing inconsistent formats (dates, categorical labels)
* Outlier detection and treatment (if applicable)
* Creating derived features (e.g., profit, margin, month, customer segment)

Output:

* A cleaned dataset saved to `data/processed/cleaned_dataset.csv`
* Data ready to be loaded into **MySQL** and **Power BI**

---

## 🗄️ Step 3 – SQL Analysis in MySQL

The cleaned dataset is imported into MySQL for further analysis using SQL.

### 3.1 Create Database & Table

Example:

```sql
CREATE DATABASE analytics_project;

USE analytics_project;

CREATE TABLE sales_data (
    id INT PRIMARY KEY AUTO_INCREMENT,
    -- define your columns here, e.g.:
    order_id VARCHAR(50),
    order_date DATE,
    customer_name VARCHAR(255),
    category VARCHAR(100),
    sub_category VARCHAR(100),
    sales DECIMAL(10,2),
    quantity INT,
    discount DECIMAL(5,2),
    profit DECIMAL(10,2)
);
```

### 3.2 Load Data into MySQL

You can import `cleaned_dataset.csv` using:

* **MySQL Workbench** → Table Data Import Wizard
* OR `LOAD DATA INFILE` command (if enabled)

### 3.3 Run SQL Queries

Core queries are stored in `sql/analysis_queries.sql`.
Examples:

* Top-selling products / categories
* Most profitable segments / regions
* Monthly sales and profit trends
* High discount vs low profit analysis

Run these queries in **MySQL Workbench** to validate insights and cross-check with Python/Power BI.

---

## 📈 Step 4 – Power BI Dashboard

The interactive dashboard is built in **Power BI** using the cleaned dataset (directly from CSV or via MySQL connection).

Key features (customize based on your dashboard):

* Overall **Sales**, **Profit**, **Quantity**, **Discount** KPIs
* Sales & profit trend over time
* Breakdown by **Category / Sub-Category / Region / Segment**
* Filters/slicers for:

  * Date range
  * Region / Category
  * Customer segment

Power BI file: `powerbi/dashboard.pbix`

> You can also create **calculated columns** and **measures** (DAX) for advanced metrics like profit margin, YoY growth, etc.

---

## 📑 Step 5 – Business Report using Gamma AI

A summarized **business presentation** is created using **Gamma AI**, based on the insights from Python, SQL, and Power BI.

Highlights of the report (typical sections):

1. **Project Objective & Dataset Overview**
2. **EDA Summary** – key trends and patterns
3. **SQL Insights** – top findings from database analysis
4. **Dashboard Walkthrough** – explanation of Power BI visuals
5. **Business Insights** – what the numbers mean in plain language
6. **Recommendations / Next Steps** (if applicable)

Exported file: `reports/business_insights_gamma_ai.pptx`

---

## 📷 Screenshots (Optional)

> Add actual images in a `images/` folder and link them here.

```markdown
### Power BI Dashboard Preview

![Power BI Dashboard](images/powerbi_dashboard.png)

### Sample EDA Plot

![EDA Plot](images/eda_sales_distribution.png)
```

---

## ✅ Key Outcomes

By the end of this project, we achieve:

* A **clean, well-structured dataset**
* Clear understanding of **sales & profit drivers**
* **SQL-based validation** of insights on a relational database
* A **Power BI dashboard** that stakeholders can interact with
* A **Gamma AI report** ready to present to management / clients

---

## 📌 How to Use This Project

1. Clone the repository
2. Set up the Python environment and run notebooks
3. Import processed data into MySQL
4. Open and explore the Power BI dashboard
5. Review the Gamma AI presentation in the `reports/` folder

---

## 🤝 Contributing

Contributions are welcome. You can:

* Add new EDA notebooks or advanced ML models
* Improve SQL queries and performance
* Enhance Power BI visuals and DAX measures
* Refine the Gamma AI report structure
* Create a **requirements.txt** based on your libraries
* Add a **section explaining your exact dataset (columns + meanings)** once you share them.
