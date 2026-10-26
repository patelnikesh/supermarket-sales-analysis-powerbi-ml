# 🛒 Supermarket Sales Analysis & BI Dashboard

> An end-to-end data analytics, machine learning, and business intelligence solution to analyze retail performance, customer purchasing behavior, and transaction values across supermarket branches.

---

## 📌 Overview
This project presents a complete data analysis pipeline covering exploratory data analysis (EDA), data cleaning, interactive business intelligence reporting, and machine learning classification. Using historical supermarket transaction records, the project uncovers drivers of retail revenue, identifies high-value customer segments, and deploys predictive classification models to distinguish between high- and low-value transactions.

---

## 🎯 Problem Statement
Modern retail chains handle vast volumes of daily transactional data across multiple cities, branches, and product departments. Without systematic analytics:
1. Store leadership cannot identify which branches, product lines, or customer profiles generate the highest gross income versus cost of goods sold.
2. Inconsistent data hygiene (outliers, missing entries, duplicate logs) distorts high-level financial reporting.
3. Marketing and store operations lack predictive insights to classify incoming baskets as high-value or standard-value transactions for targeted retention and inventory prioritization.

---

## 📂 Dataset
* **Source:** Supermarket transactional records (`supermarket_sales_eda.csv` / `supermarket_sales_processed.csv`).
* **Granularity:** Transactional records covering sales across multiple branches from January to June.
* **Key Attributes:**
  * `Invoice_ID`: Unique transaction identifier.
  * `Branch` & `City`: Retail location attributes (Branches A, B, and C).
  * `Customer_Type`: Membership status (`Member` vs. `Normal`)[cite: 6].
  * `Gender`: Customer gender (`Female` vs. `Male`)[cite: 6].
  * `Product_Line`: Departmental categories (`Home and lifestyle`, `Fashion accessories`, `Food and beverages`, `Health and beauty`, `Sports and travel`, `Electronic accessories`)[cite: 1, 6].
  * `Unit_Price`, `Quantity`, `Tax_5_Percent`: Pricing and government levy fields[cite: 6].
  * `Total` & `COGS`: Aggregate transaction gross amount and Cost of Goods Sold[cite: 6].
  * `Gross_Income`: Calculated store margin[cite: 6].
  * `Rating`: Customer checkout rating (1 to 10 scale).
  * `Payment`: Method of tender (`Credit card`, `Cash`, `Ewallet`)[cite: 6].

---

## 🛠️ Tools and Technologies
* **Programming Language:** Python
* **Data Processing & Analytics:** Pandas, NumPy
* **Exploratory Visualization:** Matplotlib, Seaborn
* **Business Intelligence & Reporting:** Microsoft Power BI Desktop (DAX, Power Query)
* **Machine Learning:** Scikit-Learn (Logistic Regression, Decision Tree Classifier, Random Forest Classifier, K-Nearest Neighbors)
* **Development Environment:** Jupyter Notebook, VS Code

---

## ⚙️ Methods
1. **Data Preprocessing & Data Cleaning:**
   * Missing value inspection, imputation, and duplicate record removal.
   * Interquartile Range (IQR) implementation for anomaly detection and outlier remediation.
   * Type casting and datetime extraction to establish calendar-ordered month dimensions (`January` to `June`)[cite: 6].
2. **Exploratory Data Analysis (EDA):**
   * Univariate and bivariate evaluations across branches, departmental categories, customer tiers, and tender channels.
   * Statistical correlation profiling between quantity, gross margin, ratings, and transactional totals.
3. **Business Intelligence Engineering:**
   * Power Query transformation pipeline outputting structured relational data for BI consumption.
   * DAX measure calculations for aggregate sales, cost accounting, and customer metric cards[cite: 6].
   * Chronological axis sorting using custom scripted pipeline logic[cite: 6].
4. **Machine Learning Workflow:**
   * Target formulation: Segmented transaction total via median thresholding into a binary classification variable (`Total_Sale_Class`).
   * One-hot encoding of categorical variables (`Branch`, `Customer_Type`, `Gender`, `Payment`).
   * Train-test splitting, model training across 4 classification algorithms, and cross-validation benchmarking.

---

## 💡 Key Insights
* **Topline Financial Performance:** Total sales reached **$288.13K** with a Cost of Goods Sold (COGS) of **$274.41K**, netting a store gross margin/income of **$13.72K**[cite: 6].
* **Branch Balance:** Revenue distribution across locations remains balanced, led by **Branch B (34.99% / $100.81K)**, followed closely by **Branch A (34.31% / $98.86K)** and **Branch C (30.70% / $88.46K)**[cite: 6].
* **Membership Value:** **Members** generate the clear majority of total store revenue (**58.87% / $169.63K**) compared to standard/normal walk-in customers (**41.13% / $118.50K**), confirming high returns on loyalty member engagement[cite: 6].
* **Demographic Equality:** Purchasing gross totals are evenly balanced across genders (**Female: 51.32% / $147.87K** vs. **Male: 48.68% / $140.26K**)[cite: 6].
* **Tender Preference:** Payments are distributed across payment options: **Credit card** leads marginally at **35.89% ($103.42K)**, followed by **Cash at 32.22% ($92.82K)** and **E-wallet at 31.89% ($91.88K)**[cite: 6].
* **Product Drivers:** **Home and lifestyle** and **Fashion accessories** consistently record the highest department sales[cite: 1, 6].

---

## 📊 Dashboard / Model / Output

### Executive Power BI Dashboard
![Super Market Sales Analysis Dashboard](dashboard/dashboard_preview.png)[cite: 6]

### Machine Learning Classification Benchmark
The classification models were benchmarked to identify whether a transaction qualifies as high-value:

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression** | Baseline | Evaluated | Evaluated | Evaluated |
| **Decision Tree** | Evaluated | Evaluated | Evaluated | Evaluated |
| **Random Forest** | Top Performer | Top Performer | Top Performer | Top Performer |
| **K-Nearest Neighbors (KNN)** | Evaluated | Evaluated | Evaluated | Evaluated |

*(Model evaluation metrics can be verified directly inside `notebook/Super Market Sale Analysis(2).ipynb`).*

---

## 🚀 How to Run this Project?

### Prerequisites
* Python 3.8+
* Microsoft Power BI Desktop (for `.pbix` report viewing)

### 1. Clone the Repository
```bash
git clone https://github.com/patelnikesh/supermarket-sales-analysis-powerbi-ml.git
cd supermarket-sales-analysis-powerbi-ml