# E-Commerce Retail Analytics: Customer Segmentation & Cohort Retention

**An end-to-end retail analytics project using Python, Pandas, SQLite, SQL and Power BI to analyse transactional data, understand customer purchasing behaviour, develop RFM segments and evaluate customer retention patterns.**

![Python](https://img.shields.io/badge/Python-3.x-blue)
![SQL](https://img.shields.io/badge/SQL-SQLite-lightgrey)
![Pandas](https://img.shields.io/badge/Library-Pandas-purple)
![Power BI](https://img.shields.io/badge/Visualization-Power%20BI-yellow)
![Jupyter](https://img.shields.io/badge/Environment-Jupyter-orange)

---

# 1. Project Overview

Understanding customer purchasing behaviour and retention is essential for e-commerce businesses seeking sustainable revenue growth.

This project analyses the Online Retail II transactional dataset to examine sales performance, identify valuable customer segments and understand customer retention patterns over time.

Using Python, Pandas, SQLite and SQL, the project follows an analytical workflow involving data inspection, preprocessing, transaction-level revenue calculations, customer segmentation and cohort retention analysis.

The resulting insights are communicated through Power BI reporting visuals covering revenue performance, customer metrics, RFM segmentation and cohort retention.

### Key Project Highlights

- Audited 244,618 raw transactional records from the available dataset extract.
- Retained 186,406 transactions after SQL-based filtering.
- Achieved a 76.2% transaction retention rate.
- Calculated transaction-level revenue.
- Developed customer-level RFM metrics.
- Segmented customers according to purchasing behaviour.
- Implemented monthly cohort retention analysis.
- Created four Power BI reporting visuals.

# 2. Business Problem

E-commerce businesses generate large volumes of transactional data, but raw sales records alone do not provide a complete understanding of customer behaviour.

Businesses need to understand:

- Which customers contribute the most revenue?
- Which customers purchase frequently?
- Which customers have not purchased recently?
- How can customers be segmented according to purchasing behaviour?
- How effectively does the business retain customers after their initial purchase?
- At which stage of the customer lifecycle does retention decline?

This project addresses these questions through transactional analysis, RFM segmentation and cohort retention analysis.

# 3. Dataset Description

**Dataset:** Online Retail II

**Original Source:** UCI Machine Learning Repository

The original dataset contains 1,067,371 transactional records from a UK-based online retailer, covering the period December 2009 to December 2011.

The repository contains an analytical extract of 244,618 raw records rather than the complete original dataset.

### Dataset Attributes

| Column | Description |
|---|---|
| Invoice | Unique invoice identifier |
| StockCode | Product identifier |
| Description | Product description |
| Quantity | Number of units purchased |
| InvoiceDate | Date and time of transaction |
| Price | Unit price |
| CustomerID | Customer identifier |
| Country | Customer's country |

The dataset contains real-world transactional characteristics, including missing customer identifiers, non-positive quantities and cancellation-related records.

# 4. Technology Stack

| Technology | Application |
|---|---|
| Python | Analytical workflow and data processing |
| Pandas | Data manipulation and transformation |
| SQLite | Relational database management |
| SQL | Data filtering, extraction and aggregation |
| Jupyter Notebook | Interactive analysis |
| Power BI | Reporting and data visualization |
| Git & GitHub | Version control and project management |

# 5. Data Processing & Cleaning

The available raw extract contains 244,618 records.

Before conducting customer-level analysis, SQL-based filtering was implemented to improve data consistency.

### Data Cleaning Operations

The cleaning workflow included:

1. Identifying records with missing Customer IDs.
2. Excluding records with missing Customer IDs for customer-level analysis.
3. Filtering non-positive quantities to exclude returns and cancellation-related records from the sales analysis.
4. Calculating transaction-level revenue using Quantity × Price.
5. Preparing the cleaned transaction dataset for customer-level analysis.

### SQL Implementation

The primary filtering logic was implemented using SQL:

```sql
SELECT *
FROM retail_transactions
WHERE "Customer ID" IS NOT NULL
AND Quantity > 0;
```

This produces the retained transaction dataset used for subsequent analysis.

### Data Processing Summary

| Metric | Records |
|---|---:|
| Original UCI Dataset | 1,067,371 |
| Raw Extract | 244,618 |
| Records with Missing Customer IDs | 53,165 |
| Retained Transactions | 186,406 |
| Excluded Records | 58,212 |
| Transaction Retention Rate | 76.2% |

The original source dataset and the analytical extract are reported separately because the repository contains only a subset of the original transactional records.

# 6. Exploratory Data Analysis & Revenue Analysis

After data cleaning, the retained transactional records were used to examine purchasing activity and revenue patterns.

Transaction-level revenue was calculated as:

**Revenue = Quantity × Price**

The analysis focused on understanding transaction values, customer purchasing patterns and overall revenue distribution.

The cleaned transaction dataset was also exported for subsequent analytical operations.

# 7. RFM Customer Segmentation

RFM analysis is used to understand customer purchasing behaviour through three dimensions:

- Recency
- Frequency
- Monetary Value

### Recency (R)

Measures how recently a customer made a purchase.

A lower recency value indicates a more recent purchase.

### Frequency (F)

Measures the number of distinct purchase occasions or invoices associated with a customer.

A higher frequency indicates more frequent purchasing activity.

### Monetary Value (M)

Measures the total transaction revenue generated by a customer.

A higher monetary value indicates greater historical spending.

### RFM Analysis Workflow

The project calculates customer-level RFM metrics from the cleaned transactional dataset.

Customers are evaluated according to their recency, frequency and monetary scores.

These metrics are then used to classify customers into behavioural segments.

### Business Purpose

RFM segmentation helps distinguish between customers with different purchasing patterns.

For example:

- Customers with recent and frequent purchases may represent highly engaged customers.
- Customers with high historical spending may represent valuable customer relationships.
- Customers with older purchase activity may require further investigation for potential inactivity.

The segmentation provides a structured approach to understanding customer value and engagement.

# 8. Cohort Retention Analysis

Cohort analysis is used to understand how customer retention changes over time.

Customers are grouped according to their first purchase month.

Each cohort is then tracked across subsequent months to calculate the percentage of customers who return.

### Cohort Analysis Workflow

1. Identify each customer's first purchase date.
2. Extract the customer's acquisition month.
3. Calculate the number of months between the first purchase and subsequent transactions.
4. Count unique active customers in each cohort-month combination.
5. Calculate monthly retention percentages.
6. Organize the results into a cohort retention matrix.

### Retention Formula

**Monthly Retention Rate = Customers Active in a Cohort Month / Original Cohort Customers × 100**

The resulting retention matrix provides a view of how customer engagement changes after acquisition.

### Key Finding

The December 2009 acquisition cohort recorded **35.3% retention in its second month**.

This indicates an early customer lifecycle drop-off and provides an opportunity for further investigation into customer engagement and retention strategies.

The finding should be interpreted within the context of the historical dataset and its observation period.

# 9. Power BI Reporting & Visualization

Power BI was used to create four reporting visuals to communicate the analytical findings.

The repository includes exported screenshots of these visuals.

### 1. Revenue Summary KPI

Presents the overall transaction revenue calculated from the cleaned dataset.

### 2. Customer Count

Communicates customer-level metrics derived from the transactional data.

### 3. RFM Customer Segmentation

Shows the distribution of customers across the developed RFM segments.

### 4. Cohort Retention Matrix

Displays monthly customer retention across acquisition cohorts.

These visuals help communicate revenue performance, customer distribution and retention patterns.

**Deliverable Note:** The repository contains screenshots of the four Power BI reporting visuals. The downloadable `.pbix` file and live interactive dashboard are not currently included.

# 10. Key Analytical Findings

The analysis provides insights into three primary areas.

### A. Data Quality

The available raw extract contained 244,618 records.

After excluding records with missing Customer IDs and non-positive quantities, 186,406 transactions were retained.

This represents a 76.2% retention rate.

### B. Customer Segmentation

RFM analysis provides a structured way to classify customers based on their purchasing recency, frequency and monetary contribution.

The resulting segments help identify differences in customer engagement and historical value.

### C. Customer Retention

The December 2009 acquisition cohort recorded 35.3% retention in its second month.

This highlights an early lifecycle drop-off that could be investigated further through customer engagement and retention analysis.

# 11. Business Implications

The analytical findings provide several areas for potential business investigation.

**1. Customer Retention**

The early decline in cohort retention suggests that customer engagement after the first purchase deserves further investigation.

Businesses could evaluate post-purchase communication, customer experience and retention initiatives.

**2. Customer Segmentation**

RFM segmentation allows businesses to distinguish between customer groups based on historical purchasing behaviour.

Different engagement strategies could be investigated for high-value, frequent and less recently active customers.

**3. Revenue Monitoring**

Transaction-level revenue calculations and reporting visuals provide a structured view of historical sales performance.

This can support further analysis of purchasing patterns and customer contribution.

These are potential business implications rather than verified improvements in business performance.

# 12. Repository Structure

```text
retail_analysis/
│
├── Retail_analysis.ipynb
│   └── Main notebook containing data processing,
│       SQL analysis, RFM segmentation and cohort analysis
│
├── online_retail_II.csv
│   └── Available raw analytical dataset extract
│
├── 1_Cleaned_Transactions.csv
│   └── Retained transactional records
│
├── 2_RFM_Segments.csv
│   └── Customer-level RFM segmentation output
│
├── 3_Cohort_Retention.csv
│   └── Cohort retention analysis output
│
├── overall_record.jpeg
│   └── Data overview screenshot
│
├── count_id.jpeg
│   └── Customer count screenshot
│
├── sum_ofrevenue.jpeg
│   └── Revenue KPI screenshot
│
├── graphical_representation.jpeg
│   └── Power BI reporting visual
│
└── README.md
    └── Project documentation
```

# 13. How to Run the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook
- Pandas
- SQLite support through Python's built-in sqlite3 library

### Installation

Clone the repository:

```bash
git clone https://github.com/karanpaul2006-gif/retail_analysis.git
```

Navigate to the project directory:

```bash
cd retail_analysis
```

Install the required Python package:

```bash
pip install pandas jupyter
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
Retail_analysis.ipynb
```

Execute the notebook cells sequentially to reproduce the analytical workflow.

Ensure that the CSV file paths used in the notebook match the repository structure.

### Power BI Files

The repository contains exported Power BI screenshots rather than a downloadable PBIX file.

The screenshots can be viewed directly through the repository.

# 14. Limitations

The project has several limitations:

- The repository contains an extract rather than the complete original UCI dataset.
- Records with missing Customer IDs are excluded from customer-level analysis.
- Non-positive quantities are excluded from the sales analysis.
- The analysis focuses on historical transactional behaviour.
- RFM segments represent historical purchasing patterns rather than guaranteed future customer behaviour.
- Cohort retention measures observed repeat purchasing and does not establish the reasons behind customer inactivity.
- An interactive Power BI report is not included in the repository.

These limitations should be considered when interpreting the findings.

# 15. Future Improvements

Potential extensions include:

- Comparing customer retention across different acquisition periods.
- Investigating factors associated with early customer inactivity.
- Developing more detailed customer engagement strategies.
- Comparing RFM segments with future purchasing behaviour.
- Adding interactive Power BI reporting.
- Exploring customer lifetime value estimation.
- Developing customer churn prediction models.

# 16. Skills Demonstrated

**Programming:** Python, Pandas and Jupyter Notebook.

**SQL & Databases:** SQLite, SQL filtering and data extraction.

**Data Analytics:** Exploratory Data Analysis, revenue analysis, customer purchasing behaviour and data cleaning.

**Customer Analytics:** RFM segmentation and cohort retention analysis.

**Business Intelligence:** Power BI reporting visuals and analytical interpretation.

**Data Management:** Transaction processing, customer-level aggregation and structured analytical outputs.

---

**Author:** Karan Paul Arora

**Project:** E-Commerce Retail Analytics
