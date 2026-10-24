# Analysis Plan — ShopSphere Retail Business Analytics

## 1. Purpose

This document defines the analytical approach for investigating retail sales performance and profitability in the ShopSphere business case study.

The goal is to transform the available transaction data into reliable business insights and recommendations that support better pricing, discount, and product performance decisions.

ShopSphere is a fictional business scenario analyzed using a Sample Superstore-style dataset.

## 2. Business Objectives

The analysis aims to:

- Establish a baseline for sales, profit, and order performance.
- Assess data quality before drawing business conclusions.
- Identify categories, sub-categories, and products with profitability issues.
- Examine how discount levels relate to recorded profit and profit margins.
- Prioritize products and sub-categories for further investigation.
- Communicate findings through an interactive Power BI dashboard.

## 3. Analytical Scope

### In Scope

- Data structure and quality assessment.
- Missing-value and duplicate checks.
- Date validation and identification of future-dated orders.
- Overall sales and profitability analysis.
- Discount-level profitability analysis.
- Category and sub-category performance analysis.
- Product-level profitability and loss concentration.
- Business insights and recommendations.
- Power BI dashboard development.

### Out of Scope

The available dataset does not support a direct assessment of:

- Marketing campaign ROI.
- Shipping cost efficiency.
- Product return rates.
- Customer acquisition costs.

These topics would require additional data sources.

## 4. Data Preparation Strategy

The original dataset will be preserved without modification.

The preparation process includes:

1. Inspecting column names, data types, and dataset dimensions.
2. Checking missing values and exact duplicate records.
3. Validating sales, quantity, discount, and shipping dates.
4. Investigating repeated Order ID–Product ID combinations without automatically removing them.
5. Identifying order dates later than the selected analysis date.
6. Creating a separate historical analytical extract for orders dated on or before October 24, 2026.
7. Documenting the assumptions and limitations associated with the prepared dataset.

Future-dated records are excluded only from the historical analytical extract. Their presence does not automatically mean that they are invalid.

## 5. Analysis Phases

### Phase 1 — Business Understanding

**Objective:** Define the business problem and translate it into measurable questions.

Activities:
- Document the ShopSphere business scenario.
- Identify the main business stakeholders.
- Define business requirements and KPI calculations.
- Establish the scope and limitations of the analysis.

Deliverables:
- `business_problem.md`
- `business_requirements.md`

### Phase 2 — Data Quality Assessment

**Objective:** Evaluate the reliability and suitability of the dataset.

Activities:
- Inspect dataset structure and column types.
- Check missing values and duplicate records.
- Validate numerical values and date relationships.
- Investigate future-dated orders and repeated order-product combinations.

Deliverables:
- `01_data_quality_assessment.ipynb`
- `data_quality_report.md`

### Phase 3 — Baseline Business Performance

**Objective:** Establish the initial performance measures for the selected historical period.

Key metrics:
- Total Sales
- Total Profit
- Profit Margin
- Total Orders
- Total Quantity

The baseline will provide a reference point for subsequent product and profitability investigations.

Deliverable:
- `02_baseline_business_performance.ipynb`

### Phase 4 — Profitability and Discount Analysis

**Objective:** Understand where profit is generated and where losses occur.

Activities:
- Compare profitability across discount levels.
- Analyze discount patterns within product categories.
- Calculate sales, profit, and profit margin by category and sub-category.
- Identify sub-categories with negative overall profit.

Business questions:
- Which discount levels are associated with negative aggregate profitability?
- Which sub-categories generate the largest losses?
- Do profitability patterns differ across product categories?

Interpretation rule:

Observed relationships between discounts and profitability will be treated as descriptive findings, not proof of causation.

### Phase 5 — Product-Level Investigation

**Objective:** Identify products that require closer business investigation.

Activities:
- Rank products by recorded profit.
- Identify the largest individual product losses.
- Calculate product-level profit margins and average discounts.
- Measure the proportion of loss-making products by sub-category.
- Compare product-level losses with overall sub-category profitability.

Priority areas identified so far:
- Furniture — Tables
- Furniture — Bookcases
- Technology — Machines

Deliverable:
- Findings documented in `business_insights.md`

### Phase 6 — Power BI Dashboard

**Objective:** Translate analytical findings into an interactive report for business stakeholders.

Planned pages:

**Page 1 — Executive Overview**
- Sales, profit, profit margin, orders, and quantity.
- Sales and profit trends over time.
- High-level performance indicators.

**Page 2 — Profitability Analysis**
- Profit by category and sub-category.
- Profit margin comparisons.
- Discount and profitability patterns.
- Identification of underperforming areas.

**Page 3 — Product Performance**
- Most profitable and most loss-making products.
- Product-level sales, profit, and discount details.
- Interactive filtering for further investigation.

The dashboard will use a clearly defined reporting period and communicate relevant data limitations.

## 6. KPI Definitions

| KPI | Definition |
|---|---|
| Total Sales | Sum of the recorded Sales values |
| Total Profit | Sum of the recorded Profit values |
| Profit Margin | Total Profit divided by Total Sales, multiplied by 100 |
| Total Orders | Count of distinct Order IDs |
| Total Quantity | Sum of the Quantity values |

Profit Margin will be calculated from aggregate profit and sales, rather than by averaging individual transaction margins.

## 7. Analytical Principles

The analysis will follow these principles:

- Preserve the original data.
- Document data preparation decisions.
- Validate findings before making business recommendations.
- Distinguish product-level losses from overall sub-category net profit.
- Avoid interpreting correlation as causation.
- Consider the financial impact and recurrence of losses when prioritizing investigations.
- Keep the analytical workflow reproducible and documented.

## 8. Expected Deliverables

- Business problem definition.
- Business requirements and KPI definitions.
- Data catalog and data quality report.
- Python notebooks for data assessment and business analysis.
- Documented business insights and recommendations.
- Processed historical dataset for Power BI.
- Interactive Power BI dashboard.
- Final project documentation in GitHub.

## 9. Current Status

| Phase | Status |
|---|---|
| Business Understanding | Completed |
| Data Quality Assessment | Completed |
| Baseline Business Performance | Completed |
| Discount and Profitability Analysis | Completed for the initial scope |
| Product-Level Investigation | Initial investigation completed |
| Power BI Dashboard | Next phase |

The project will continue with the Power BI implementation, beginning with data import, data type validation, and KPI measure creation.