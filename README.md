## Dataset Source & Description

This project uses the **Online Retail II dataset** from the UCI Machine Learning Repository, containing 1,067,371 original transactional records from a UK-based online retailer.

**Dataset Details:**
- Source: UCI Machine Learning Repository
- Original Records: 1,067,371
- Time Period: December 2009 – December 2011
- Business Domain: E-Commerce / Retail
- Key Attributes: Invoice, StockCode, Description, Quantity, InvoiceDate, Price, CustomerID, Country.

The original dataset is available in the repository as `online_retail_II.csv`.

## Data Cleaning & Preparation

The original dataset contains real-world transactional data quality issues. SQL-based filtering and data preparation were performed before customer-level analysis.

Key preprocessing operations included:

- Identifying and excluding records with missing Customer IDs for customer-level analysis.
- Filtering non-positive quantities to exclude returns and cancellation-related records from sales analysis.
- Handling invalid or non-positive unit prices.
- Preparing transaction-level revenue using Quantity × Price.
- Preparing the resulting dataset for customer segmentation and cohort analysis.

**Dataset Processing Summary**

| Metric | Records |
|---|---:|
| Original UCI Dataset | 1,067,371 |
| Records Loaded into Analysis | [Insert verified count] |
| Records Retained After Cleaning | [Insert verified count] |

The original source size and the final analytical dataset size are reported separately because not every source transaction is suitable for customer-level sales analysis.

## Power BI Visualizations

Power BI was used to develop reporting visuals presenting the analytical findings.

The repository includes screenshots of four Power BI report visuals:

1. Revenue Summary KPI – Total transaction revenue.
2. Customer Count – Customer-level metrics.
3. RFM Customer Segmentation – Distribution of customer segments.
4. Cohort Retention Matrix – Customer retention patterns across acquisition cohorts.

These screenshots provide a visual representation of the report. The downloadable Power BI `.pbix` file and live interactive report are not currently included in this repository.

## Analytical Findings

The analysis provides insights into:

- Customer purchasing behaviour and historical spending patterns.
- RFM-based customer segmentation.
- Monthly cohort retention patterns.
- Revenue distribution and customer engagement trends.

For example, the December 2009 acquisition cohort recorded 35.3% retention in its second month, highlighting an early customer lifecycle drop-off for further investigation.

