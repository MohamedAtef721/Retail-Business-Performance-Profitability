# Data Catalog — Retail Business Analytics

## 1. Dataset Overview

| Attribute | Description |
|---|---|
| Project Name | Retail Business Performance & Profitability Analysis |
| Dataset Name | Sample Superstore |
| Dataset Type | Retail / Sales Transaction Data |
| Data Format | CSV |
| Current Row Count | 10,194 |
| Number of Columns | 21 |
| Distinct Orders | 5,111 |
| Distinct Products | 1,862 |
| Analysis Tools | Python, Pandas, Power BI |
| Project Status | Data Understanding & Quality Assessment |

### Project Context

This project investigates retail business performance, with a focus on understanding the relationship between sales and profitability.

The analysis aims to identify potential profitability issues, investigate the impact of discounts and product mix, and uncover differences in performance across customer segments, products, regions, and time.

**Important:** The dataset is being used to simulate a business analytics case study. The business scenario and stakeholder questions are analytical assumptions, not verified facts about the dataset's original business.

---

## 2. Dataset Grain

The dataset contains transaction-level product records.

Based on the initial inspection, the dataset has 10,194 rows and 5,111 distinct Order IDs.

This suggests that an order may contain multiple product records. The exact row-level grain should be confirmed by checking the combination of Order ID and Product ID.

**Analytical implication:** Row count must not be used as a substitute for order count. Distinct orders should be calculated using the unique Order ID.

---

## 3. Data Dictionary

### 3.1 Order and Shipping Information

| Column | Observed Data Type | Description | Analytical Use |
|---|---|---|---|
| Row ID | Integer | Row identifier | Record identification and uniqueness checks |
| Order ID | String | Identifier for a customer order | Distinct order counting |
| Order Date | Datetime | Date the order was placed | Sales trends and time-based analysis |
| Ship Date | Datetime | Date the order was shipped | Shipping delay and fulfillment analysis |
| Ship Mode | String | Shipping service or delivery mode | Comparing sales and profit across shipping modes |

### 3.2 Customer and Geographic Information

| Column | Observed Data Type | Description | Analytical Use |
|---|---|---|---|
| Customer ID | String | Customer identifier | Distinct customer counting |
| Customer Name | String | Customer name | Customer-level analysis |
| Segment | String | Customer segment classification | Segment performance comparison |
| Country/Region | String | Country or geographic region | Geographic analysis |
| City | String | City associated with the record | City-level performance |
| State/Province | String | State or province associated with the record | Regional performance analysis |
| Postal Code | Object | Postal or ZIP code | Geographic grouping and data validation |
| Region | String | Broader geographic sales region | Regional sales and profitability comparison |

### 3.3 Product Information

| Column | Observed Data Type | Description | Analytical Use |
|---|---|---|---|
| Product ID | String | Product identifier | Distinct product counting |
| Category | String | Main product category | Category-level performance |
| Sub-Category | String | Product subcategory | Detailed product mix analysis |
| Product Name | String | Product name | Product-level sales and profitability |

### 3.4 Sales and Financial Information

| Column | Observed Data Type | Description | Analytical Use |
|---|---|---|---|
| Sales | Float | Sales amount recorded for a product transaction | Revenue analysis |
| Quantity | Integer | Number of units recorded for a transaction | Sales volume analysis |
| Discount | Float | Discount value associated with the transaction | Discount and profitability analysis |
| Profit | Float | Profit value recorded for the transaction | Profitability and loss analysis |

**Financial interpretation note:** The dataset's Profit column is used as the recorded profit measure. Its exact accounting definition should be verified before treating it as net profit. The available columns do not explicitly identify all operating expenses, marketing costs, shipping costs, or return costs.

---

## 4. Initial Data Quality Findings

The following checks have been completed so far.

| Check | Result | Status |
|---|---|---|
| Dataset dimensions | 10,194 rows × 21 columns | Verified |
| Exact duplicate rows | 0 | Passed |
| Duplicate Row IDs | 0 | Passed |
| Sales values less than or equal to zero | 0 | Passed |
| Quantity values less than or equal to zero | 0 | Passed |
| Negative Profit records | 1,901 | Requires business investigation |
| Negative Discount values | 0 | Passed |
| Discount values greater than 1 | 0 | Passed |
| Ship Date before Order Date | 0 | Passed |
| Missing values | Pending confirmation | Not yet documented |
| Future-dated records | Pending investigation | Not yet documented |
| Order and product record grain | Pending validation | Not yet documented |

### Initial Date Range

- First Order Date: 2023-01-03
- Last Order Date: 2026-12-30

The date range requires further validation because it extends beyond the current analysis date. Future-dated records should be investigated before using the full period for time-series analysis.

### Important Interpretation

The 1,901 records with negative Profit are not automatically data errors. They represent recorded losses at the row level and should be investigated to determine whether losses are concentrated in specific products, categories, discounts, customer segments, or regions.

The number of loss-making records must not be interpreted as the number of loss-making orders.

---

## 5. Key Business Questions

The dataset will be used to investigate the following questions:

1. What are the overall sales, profit, and profit margin?
2. How do sales and profitability change over time?
3. Which categories and subcategories generate the highest sales and profit?
4. Which products or product groups generate losses?
5. Is there an association between discounts and lower profitability?
6. Which customer segments and regions perform best?
7. Do shipping modes show meaningful differences in recorded profitability?
8. Are sales growth and profit growth moving at the same pace?

These questions will be refined after reviewing the data and establishing baseline business metrics.

---

## 6. Known Data Limitations

- The available columns do not explicitly include marketing expenditure or campaign-level data, so marketing ROI cannot be calculated directly.
- Separate shipping cost data is not available in the listed columns.
- No explicit returns table or return indicator appears in the current schema.
- Recorded Profit should not be assumed to represent fully loaded net profit without verifying its definition.
- The dataset's future-dated records and missing-value status still require investigation.
- The data's original business context and date range should be verified before drawing conclusions about real-world performance.

---

## 7. Next Steps

1. Complete missing-value and date validation.
2. Confirm the dataset's row-level grain.
3. Document all cleaning decisions in `data_quality_report.md`.
4. Establish baseline sales and profitability KPIs.
5. Perform exploratory data analysis in Python.
6. Translate validated findings into business recommendations.
7. Build the Power BI report after the analysis and business requirements are clear.

---

## 8. Update Policy

This catalog should be updated whenever the schema, data types, data quality findings, or understanding of the dataset changes.

All data cleaning decisions should be documented separately so that the analysis remains transparent and reproducible.
