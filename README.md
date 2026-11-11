# E-Commerce Retail Analytics: Customer Segmentation & Cohort Retention

An end-to-end retail analytics project exploring customer purchasing behaviour, revenue patterns, customer segmentation and retention using Python, Pandas, SQLite, SQL and Power BI.

<p align="left">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"/>
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
</p>

---

## 1. Project Overview

The objective of this project is to analyse historical retail transactions and understand customer purchasing behaviour, revenue generation, customer value and retention patterns.

Using the Online Retail II dataset, the project implements data cleaning, SQL-based analysis, RFM customer segmentation, cohort retention analysis and Power BI reporting.

### Business Questions

- How much revenue is generated through retail transactions?
- How many unique customers are represented in the dataset?
- Which customers contribute the most monetary value?
- How can customers be segmented based on purchasing behaviour?
- How does customer retention change across acquisition cohorts?
- At what stage of the customer lifecycle does retention begin to decline?

---

## 2. Dataset Information

**Dataset:** Online Retail II  
**Source:** UCI Machine Learning Repository  
**Original Dataset Size:** 1,067,371 records  
**Working Dataset Size:** 244,618 records  
**Time Period:** December 2009 – December 2011

The dataset contains historical transactions from a UK-based online retailer specialising in giftware and homeware products.

**Dataset Source:**  
https://archive.ics.uci.edu/dataset/502/online+retail+ii

### Important Dataset Clarification

The original UCI dataset contains 1,067,371 records.

This project uses a 244,618-record working dataset (`online_retail_II.csv`) extracted from the original source.

The CSV included in this repository is therefore not the complete original UCI dataset.

### Important Columns

| Column | Description |
|---|---|
| Invoice | Transaction invoice number |
| StockCode | Product identification code |
| Description | Product description |
| Quantity | Number of units purchased |
| InvoiceDate | Date and time of transaction |
| Price | Unit price |
| Customer ID | Unique customer identifier |
| Country | Customer's country |

---

## 3. Data Cleaning & Preparation

The working dataset initially contained 244,618 records.

SQL-based filtering and data preparation were performed to prepare the dataset for customer-level analysis.

### Cleaning Operations

- Identified and excluded records with missing Customer IDs.
- Removed transactions with non-positive quantities.
- Prepared transaction revenue using Quantity × Price.
- Prepared cleaned transactions for customer-level analysis.
- Structured the data for RFM segmentation and cohort analysis.

### Data Cleaning Summary

| Metric | Records |
|---|---:|
| Original UCI Dataset | 1,067,371 |
| Working Dataset | 244,618 |
| Missing Customer ID Records | 53,165 |
| Cleaned Transactions | 186,406 |
| Total Excluded Records | 58,212 |
| Retention Percentage | 76.2% |

**Calculation:**

186,406 / 244,618 × 100 = 76.2%

The retention percentage represents the proportion of working records retained after data cleaning.

---

## 4. Exploratory Data Analysis & SQL Analysis

SQL was implemented using SQLite to perform data extraction, filtering, aggregation and customer-level analysis.

The analysis includes:

- Transaction-level revenue calculation.
- Customer-level aggregations.
- Revenue analysis.
- Customer counts.
- Data filtering and validation.
- RFM metric preparation.
- Cohort-based retention calculations.

### SQL Concepts Implemented

- SELECT and WHERE
- GROUP BY
- Aggregate functions
- Data filtering
- Customer-level aggregation
- SQLite database operations

Python and Pandas were used alongside SQL for data manipulation and analytical calculations.

---

## 5. Customer Segmentation: RFM Analysis

RFM analysis was performed to understand customer purchasing behaviour and identify different customer value groups.

The three metrics used are:

| Metric | Meaning |
|---|---|
| Recency (R) | How recently a customer made a purchase |
| Frequency (F) | How frequently a customer makes purchases |
| Monetary (M) | How much a customer spends |

Customer-level RFM metrics were calculated using historical transaction data.

The purpose of this analysis is to distinguish customers based on their purchasing activity and monetary contribution.

This provides a foundation for identifying valuable customer segments and supporting targeted customer-retention strategies.

The resulting customer segmentation is exported to:

`2_RFM_Segments.csv`

---

## 6. Cohort Retention Analysis

Cohort analysis was performed to understand how customer retention changes over time.

Customers were grouped into cohorts based on their first purchase month.

Their subsequent purchasing activity was tracked across later months.

### Analysis Objectives

- Understand customer retention over time.
- Compare purchasing behaviour across acquisition cohorts.
- Identify early customer lifecycle drop-offs.
- Examine how customer engagement changes after the first purchase.

### Key Finding

The December 2009 acquisition cohort recorded **35.3% retention in its second month**.

This indicates an early customer lifecycle drop-off and highlights an area worth investigating through customer engagement and retention initiatives.

The calculated cohort retention results are exported to:

`3_Cohort_Retention.csv`

---

## 7. Power BI Reporting & Visualizations

Power BI was used to create reporting visuals presenting the results of the retail analysis.

The report includes four major visual components:

1. **Revenue Summary KPI** – Displays total transaction revenue.
2. **Customer Count** – Presents customer-level metrics.
3. **RFM Customer Segmentation** – Shows the distribution of customer segments.
4. **Cohort Retention Matrix** – Displays retention patterns across acquisition cohorts.

### Dashboard Visuals

![Overall Record Analysis](overall_record.jpeg)

![Revenue Analysis](sum_ofrevenue.jpeg)

![Customer Count Analysis](count_id.jpeg)

![Analytical Visualization](graphical_representation.jpeg)

**Dashboard Availability Note**

The Power BI report was developed, but the downloadable `.pbix` file and live interactive Power BI report are not included in this repository.

Screenshots are provided to demonstrate the reporting visuals created during the project.

---

## 8. Key Analytical Findings

- The working dataset initially contained 244,618 records.
- 186,406 records were retained after data preparation.
- The cleaned dataset represents 76.2% of the working records.
- Customer purchasing behaviour was analysed through RFM metrics.
- Customers were segmented based on Recency, Frequency and Monetary value.
- Cohort analysis revealed 35.3% second-month retention for the December 2009 cohort.
- Four Power BI reporting visuals were developed to communicate analytical findings.

---

## 9. Technologies & Tools

| Category | Technologies |
|---|---|
| Programming | Python |
| Data Manipulation | Pandas |
| Database | SQLite |
| Query Language | SQL |
| Analysis | RFM Analysis, Cohort Analysis, EDA |
| Visualization | Power BI |
| Development Environment | Jupyter Notebook |
| Version Control | Git, GitHub |

---

## 10. Repository Structure

```text
retail_analysis/
│
├── Retail_analysis.ipynb
│
├── online_retail_II.csv
│
├── 1_Cleaned_Transactions.csv
│
├── 2_RFM_Segments.csv
│
├── 3_Cohort_Retention.csv
│
├── overall_record.jpeg
├── sum_ofrevenue.jpeg
├── count_id.jpeg
├── graphical_representation.jpeg
│
└── README.md
```

---

## 11. Running the Project

### Requirements

- Python 3.x
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- SQLite (available through Python's built-in `sqlite3` module)

### Installation

Install the required Python libraries:

```bash
pip install pandas numpy matplotlib jupyter
```

### Execution

1. Clone or download this repository.
2. Open `Retail_analysis.ipynb` in Jupyter Notebook.
3. Ensure `online_retail_II.csv` is available in the working directory.
4. Execute the notebook cells sequentially.
5. Review the cleaning operations, SQL queries, RFM segmentation and cohort retention analysis.

---

## 12. Project Limitations

- The analysis uses a 244,618-record working dataset rather than the complete 1,067,371-record UCI dataset.
- Customer-level analysis excludes records without valid customer identifiers.
- The Power BI `.pbix` file and interactive report are not currently included.
- Findings are based on historical transactional data and should not be interpreted as verified outcomes from an implemented business intervention.
- The analysis identifies retention patterns but does not establish the causes of customer churn.

---

## 13. Conclusion

This project demonstrates an end-to-end retail analytics workflow covering data cleaning, SQL-based analysis, customer segmentation, cohort retention analysis and business-oriented reporting.

By combining Python, Pandas, SQLite, SQL and Power BI, the project transforms transactional records into structured customer and business insights.

It demonstrates practical applications of data analytics in e-commerce, particularly in understanding customer value, purchasing behaviour and retention patterns.

---

## Dataset Citation

Chen, D. (2012). Online Retail II [Dataset]. UCI Machine Learning Repository.

https://doi.org/10.24432/C5CG6D
