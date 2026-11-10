# 🛍️ E-Commerce Retail Analytics: Customer Segmentation & Retention Engine

An end-to-end data analytics pipeline processing over 1 million transactional e-commerce records to uncover purchasing behaviors, evaluate customer lifetime value, and track retention. This project combines **SQL-based ETL processes**, statistical modeling via **RFM (Recency, Frequency, Monetary) Segmentation**, and **Cohort Analysis** to deliver actionable business intelligence through interactive Power BI dashboards.

---

## 🛠️ Tech Stack & Tools

* **Data Extraction & Transformation:** SQL (SQLite), Python
* **Data Analysis & Modeling:** Pandas, NumPy
* **Business Intelligence & Visualization:** Power BI
* **Environment:** Jupyter Notebook, Git/GitHub

---

## 📊 Key Analytical Pipeline

### 1. SQL Data Extraction & Cleaning (ETL)

* Utilized an in-memory SQLite database to process raw transactional data.
* Executed SQL queries to filter out missing customer records, remove negative quantities (returns/cancellations), and handle unit price anomalies.
* Engineered a foundational `Revenue` metric (`Quantity * Price`) directly within the extraction pipeline to prepare the dataset for behavioral modeling.

### 2. RFM Customer Segmentation

* **Recency (R):** Measured the days since a customer's last purchase to gauge current engagement.
* **Frequency (F):** Quantified the total number of distinct orders to identify repeat buyers.
* **Monetary (M):** Evaluated the total capital spent to determine customer lifetime value (CLV).
* **Business Impact:** Segmented users into highly actionable behavioral cohorts (*Champions*, *Loyal Customers*, *At Risk (High Value)*, and *Needs Attention*) to allow marketing teams to optimize targeted campaigns and reduce churn.

### 3. Cohort Retention Analysis

* Grouped customers by their initial acquisition month to establish baseline cohorts.
* Tracked period-over-period retention curves to monitor customer loyalty and platform stickiness.
* **Business Impact:** Generated retention matrices to pinpoint exactly when customer drop-offs occur in the lifecycle, enabling proactive retention strategies.

---

## 📈 Power BI Visualizations

The analytical outputs were ingested into Power BI to create an interactive, executive-level decision support dashboard. Key visual components include:

* **Executive Revenue Summary (`sum_ofrevenue.jpeg`):** High-level commercial KPI tracking total financial turnover.
* **Customer Count Metrics (`count_id.jpeg`):** Active user scale and acquisition tracking.
* **RFM Profiles Breakdown (`graphical_representation.jpeg`):** Visual distribution of revenue contributions across segmented customer groups.
* **Cohort Retention Matrix (`overall_record.jpeg`):** Comprehensive heatmap tracking month-over-month retention percentages to quickly identify lifecycle trends.

---
Dataset Overview & Data Quality.
Original UCI dataset	1,067,371
Raw records: 244618
Missing Customer IDs: 53165
Non-positive quantities: 6661
Cleaned records: 186406
Excluded records: 58212
Retention percentage: 76.2 %

## 📂 Project Structure

```text
retail_analysis/
│
├── Retail_analysis.ipynb          # Main Jupyter Notebook (SQL Data Pipeline, RFM, & Cohort Analysis)
├── online_retail_ii.csv           # Raw dataset source file
│
├── 1_Cleaned_Transactions.csv     # Cleaned and processed transactional dataset (SQL Output)
├── 2_RFM_Segments.csv             # Customer RFM scores and segment classifications
├── 3_Cohort_Retention.csv         # Cohort analysis retention matrix data
│
├── count_id.jpeg                  # Power BI visual: Customer count metrics
├── graphical_representation.jpeg  # Power BI visual: RFM customer profiles breakdown
├── overall_record.jpeg            # Power BI visual: Cohort retention matrix heatmap
├── sum_ofrevenue.jpeg             # Power BI visual: Executive revenue summary KPI
│
└── README.md                      # Project documentation

```
