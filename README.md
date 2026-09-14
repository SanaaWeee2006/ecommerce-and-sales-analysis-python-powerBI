# E-commerce Sales, Customer & Operations Analytics

## Project Overview

This project analyzes the **Brazilian E-Commerce Public Dataset by Olist** to understand sales performance, customer behavior, product performance, delivery operations, and customer experience.

The objective is to transform raw e-commerce data into actionable business insights using **Python, Pandas, Power BI, and DAX**.

The project focuses on descriptive and diagnostic analytics rather than machine learning.

---

## Business Questions

The analysis addresses the following questions:

### Sales Performance

* How much revenue was generated?
* How many orders and items were sold?
* How does revenue change over time?
* Which product categories generate the most revenue?
* Which customer states contribute most to revenue?
* What is the average order value?
* How significant is freight relative to sales?

### Customer & Product Analytics

* How many unique customers are there?
* What proportion of customers make repeat purchases?
* How frequently do customers purchase?
* Which customers generate the highest revenue?
* Which customer segments have the highest value or risk?
* Which products and categories perform best?

### Operations & Customer Experience

* How long does delivery take on average?
* What percentage of orders arrive late?
* Which states have higher delivery delays?
* Are late deliveries associated with lower review scores?
* What is the distribution of order statuses?

---

## Dataset

The project uses the **Brazilian E-Commerce Public Dataset by Olist**, containing information about:

* Customers
* Orders
* Order items
* Payments
* Reviews
* Products
* Sellers
* Product categories
* Geolocation

The analysis primarily uses the following tables:

| Table                | Purpose                                |
| -------------------- | -------------------------------------- |
| Customers            | Customer and geographic information    |
| Orders               | Order dates and order status           |
| Order Items          | Products, prices, sellers, and freight |
| Payments             | Payment information                    |
| Reviews              | Customer review scores and feedback    |
| Products             | Product attributes and categories      |
| Sellers              | Seller information                     |
| Category Translation | Portuguese-to-English category names   |

---

## Tools & Technologies

* **Python**

  * Pandas
  * NumPy
  * Matplotlib
* **Power BI**

  * Data modeling
  * DAX
  * Interactive dashboards
* **SQL Server**

  * Data validation and analytical SQL scripts

Machine learning was intentionally excluded from this project.

---

## Project Workflow

```text
Raw E-commerce Data
        ↓
Data Loading & Audit
        ↓
Data Cleaning & Validation
        ↓
Exploratory Data Analysis
        ↓
Customer Analysis & RFM Segmentation
        ↓
Power BI Data Modeling
        ↓
DAX Measures & Calculations
        ↓
Interactive Dashboard
        ↓
Business Insights & Recommendations
```

---

## Data Quality & Validation

The raw data was audited before analysis.

Key checks included:

* Missing-value analysis
* Duplicate-key checks
* Order-status distribution
* Date validation
* Relationship validation between tables
* Delivery-date consistency
* Product-category completeness

No invalid delivery-date relationships were identified in the delivered-order analysis.

Some missing values were retained because they represent legitimate characteristics of the dataset. For example, delivery dates can be unavailable for orders that were not delivered, while missing review text does not prevent the review score from being analyzed.

Product records with missing categories were retained rather than removed and treated as unclassified where appropriate.

---

# Key KPIs

The delivered-order analysis produced the following core metrics:

| KPI                   |         Result |
| --------------------- | -------------: |
| Revenue               |   **R$13.22M** |
| Delivered Orders      |     **96,478** |
| Items Sold            |    **110,197** |
| Average Order Value   |   **R$137.04** |
| Freight               |    **R$2.20M** |
| Average Delivery Time | **12.56 days** |
| Late Delivery Rate    |      **8.11%** |

Revenue represents the sum of item prices for delivered orders.

> **Important:** The dataset does not provide product acquisition costs, so profit and profit-margin analysis are not included.

---

# Dashboard

The Power BI dashboard is divided into three analytical pages.

## 1. Executive Sales Performance

This page provides a high-level overview of sales performance.

### Key metrics

* Total Revenue
* Total Orders
* Average Order Value
* Items Sold
* Items per Order
* Total Freight
* Revenue Growth
* Late Delivery Rate

### Visual analysis

* Monthly revenue trend
* Monthly order volume
* Revenue by product category
* Revenue by customer state

This page is designed to answer:

> **How is the e-commerce business performing overall?**

---

## 2. Customer & Product Analytics

This page focuses on customer behavior and product performance.

### Customer metrics

* Unique Customers
* Repeat Customers
* Repeat Customer Rate
* Average Customer Revenue
* Average Items per Customer

### Customer analysis

* One-time vs repeat customers
* Customer purchase frequency
* Top customers by revenue
* RFM customer segments

### Product analysis

* Category revenue
* Order volume
* Item volume
* Revenue per order

RFM analysis uses:

* **Recency** — how recently the customer purchased
* **Frequency** — how often the customer purchased
* **Monetary** — how much revenue the customer generated

Customers were grouped into segments such as:

* Champions
* Loyal Customers
* High Value New
* At Risk Loyal
* At Risk High Value
* New / Promising
* Other

This page is designed to answer:

> **Who are the customers, how valuable are they, and which products drive performance?**

---

## 3. Operations & Customer Experience

This page evaluates delivery performance and its relationship with customer satisfaction.

### Key metrics

* Average Delivery Time
* Late Orders
* Late Delivery Rate
* Average Review Score

### Visual analysis

* Average delivery time by state
* Late delivery rate by state
* Review score: On-Time vs Late
* Order status distribution

The analysis found:

| Delivery Group | Average Review Score |
| -------------- | -------------------: |
| On Time        |         **4.29 / 5** |
| Late           |         **2.57 / 5** |

Late deliveries are therefore **strongly associated with lower customer review scores**, with a difference of approximately **1.73 points**.

This is an association identified in the data and should not be interpreted as proof that late delivery alone causes lower ratings.

---

# Key Business Insights

### 1. Sales volume is the primary driver of revenue variation

Monthly revenue and order volume follow similar patterns, while average order value is comparatively stable.

This suggests that changes in sales performance are influenced substantially by changes in the number of orders rather than large changes in order value.

---

### 2. Revenue is concentrated across several major categories

The strongest revenue-generating categories include:

* Health & Beauty
* Watches & Gifts
* Bed & Bath Table
* Sports & Leisure
* Computers & Accessories

The top categories provide important areas for merchandising, inventory, and sales-performance monitoring.

---

### 3. Repeat purchasing is an important growth opportunity

A significant portion of customers make only one delivered purchase.

This creates an opportunity to improve customer retention and increase customer lifetime value through targeted retention strategies.

---

### 4. Delivery performance is closely linked with customer experience

Customers whose orders arrived late had substantially lower average review scores than customers whose orders arrived on time.

This makes delivery reliability an important customer-experience KPI, not only an operational metric.

---

### 5. Delivery performance varies by state

Average delivery time and late-delivery rates vary considerably across customer states.

These differences can help the business identify locations where logistics performance requires further investigation.

Geographic differences should be treated as areas for investigation rather than evidence that location itself causes delays.

---

### 6. Freight is a significant operational metric

Delivered orders generated approximately **R$2.20M in freight charges** alongside approximately **R$13.22M in item-price revenue**.

Freight should therefore be monitored alongside sales performance when evaluating sellers, categories, and operational efficiency.

---

# Business Recommendations

## 1. Improve delivery reliability

Identify states, sellers, and order patterns with consistently high late-delivery rates.

Prioritize operational investigation in areas where both delivery delays and customer dissatisfaction are high.

---

## 2. Focus on customer retention

Use RFM segmentation to identify:

* High-value customers
* Loyal customers
* At-risk high-value customers
* Promising newer customers

Retention initiatives can then be targeted toward the customer groups with the greatest potential value.

---

## 3. Monitor high-performing categories

Track revenue, orders, and item volume across categories to understand which product areas contribute most to overall sales.

High-performing categories can receive greater attention in merchandising and inventory planning.

---

## 4. Monitor freight efficiency

Compare freight against revenue by:

* Seller
* Product category
* Customer state
* Order

This can highlight areas where transportation costs represent a relatively high portion of sales.

---

## 5. Make delivery reliability a CX KPI

Because late deliveries are strongly associated with lower review scores, delivery performance should be monitored alongside customer-experience metrics rather than treated as a separate operational issue.

---

# Project Structure

```text
olist-ecommerce-analytics/
│
├── data/
│   ├── raw/
│   └── processed/
│       ├── customer_analysis.csv
│       ├── customer_rfm.csv
│       └── customer_segments.csv
│
├── notebooks/
│   ├── 01_data_audit.ipynb
│   ├── 02_eda.ipynb
│   └── 03_customer_analysis.ipynb
│
├── sql/
│   ├── 01_data_validation.sql
│   ├── 02_sales_analysis.sql
│   └── 03_customer_analysis.sql
│
├── powerbi/
│   └── olist_ecommerce_dashboard.pbix
│
├── outputs/
│
└── README.md
```

---

# Analytical Approach

### Data Audit

Checked data types, missing values, duplicates, order statuses, and date consistency.

### Sales Analysis

Calculated revenue, order volume, item volume, AOV, freight, category performance, seller performance, and geographic sales patterns.

### Delivery Analysis

Calculated delivery duration, late-delivery rates, and state-level operational performance.

### Customer Analysis

Analyzed unique customers, repeat purchasing, customer revenue, purchase frequency, and customer value.

### RFM Segmentation

Segmented customers based on recency, frequency, and monetary value to identify different customer-value groups.

### Power BI

Built a relational data model and interactive dashboard using DAX measures, calculated columns, slicers, KPI cards, trend charts, and analytical visuals.

---

# Limitations

* The dataset does not contain product acquisition costs, so actual profit cannot be calculated.
* Missing delivery dates are expected for some non-delivered orders.
* Product categories are missing for a small portion of products.
* Customer review text has substantial missing values, so review-score analysis is more reliable than text-based sentiment analysis.
* Geographic differences show associations and operational patterns but do not establish causation.
* RFM segmentation is based on the available historical transaction period and should be interpreted within that timeframe.

---

# Conclusion

This project demonstrates an end-to-end approach to **e-commerce business analytics**, from raw data validation and exploratory analysis through customer segmentation and interactive Power BI reporting.

The analysis highlights three major business themes:

> **Strong sales performance, limited repeat purchasing, and a strong association between delivery delays and customer satisfaction.**

These findings provide practical opportunities to improve customer retention, delivery reliability, category performance, and operational efficiency.

---

## Skills Demonstrated

**Python:**
Pandas · NumPy · Data Cleaning · Data Transformation · EDA · Aggregation · Feature Engineering

**SQL:**
Data Validation · Joins · Aggregations · Analytical Queries

**Power BI:**
Data Modeling · Relationships · DAX · KPI Design · Interactive Dashboards · Data Visualization

**Business Analytics:**
Sales Analysis · Customer Analytics · RFM Segmentation · Operations Analytics · Customer Experience · Business Recommendations
