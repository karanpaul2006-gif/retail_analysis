# 🛍️ E-Commerce Retail Analysis & Customer Segmentation

An end-to-end data analytics project examining transactional e-commerce data to uncover purchasing behaviors, evaluate customer lifetime value via **RFM (Recency, Frequency, Monetary) Segmentation**, track month-over-month customer retention through **Cohort Analysis**, and visualize performance metrics using interactive dashboards.

---

## 📂 Project Structure

```text
retail_analysis/
│
├── Retail_analysis.ipynb          # Main Jupyter Notebook containing data pipeline & analysis
├── 1_Cleaned_Transactions.csv     # Cleaned and processed transactional dataset
├── 2_RFM_Segments.csv             # Customer RFM scores and segment classifications
├── 3_Cohort_Retention.csv         # Cohort analysis retention matrix data
├── online_retail_ii.csv           # Raw dataset source file
├── count_id.jpeg                  # Power BI visual: Customer count metrics
├── graphical_representation.jpeg  # Power BI visual: RFM customer profiles breakdown
├── overall_record.jpeg            # Power BI visual: Cohort retention matrix heatmap
├── sum_ofrevenue.jpeg             # Power BI visual: Executive revenue summary KPI
└── README.md                      # Project documentation


📊 Key Analytical Pipeline
Data Cleaning & Preparation:

Filtered out missing customer records and negative quantities (returns/cancellations).

Standardized datetime attributes and engineered a total Revenue metric (Quantity * Price).

RFM Customer Segmentation:

Recency (R): Measures how recently a customer made a purchase.

Frequency (F): Quantifies how often a customer transacts.

Monetary (M): Evaluates total capital spent by the customer.

Segmented users into distinct behavioral groups (Champions, Loyal Customers, At Risk, Needs Attention) to inform targeted marketing strategies.

Cohort Retention Analysis:

Grouped customers by their initial acquisition month to create cohorts.

Tracked period-over-period retention curves to monitor customer loyalty and churn dynamics.

📈 Power BI Visualizations
Key performance dashboards and visual outputs integrated into the project:

Executive Revenue Summary (sum_ofrevenue.jpeg): High-level commercial KPI tracking total financial turnover.   

Customer Count Metrics (count_id.jpeg): Active user scale tracking.   

RFM Profiles Breakdown (graphical_representation.jpeg): Visual distribution of revenue contributions across customer segments.   

Cohort Retention Matrix (overall_record.jpeg): Comprehensive heatmap tracking month-over-month retention percentages.   
Screenshot 2026-11-04 140354.jpg
