# ShopSphere | Retail Business Performance & Profitability Analysis

**Turning Retail Data into Business Insights and Profitability Improvements**

## 📌 Project Overview

ShopSphere is a business analytics case study focused on understanding retail sales performance, identifying profitability challenges, and supporting data-driven business decisions.

The project simulates a retail business scenario in which strong sales performance does not always translate into strong profitability across products, sub-categories, customer segments, and geographic areas.

Using a Sample Superstore-style dataset, the project follows an end-to-end business analytics workflow, starting with business understanding and data quality assessment, followed by exploratory data analysis using Python and an interactive six-page Power BI dashboard.

> **Note:** ShopSphere is a fictional business scenario. The analysis uses the Sample Superstore dataset as a proxy and does not represent actual company records.

## 🎯 Business Problem

High sales do not necessarily translate into high profits. Retail businesses need to understand which products generate losses, how discount levels relate to profitability, and which business areas require further investigation.

This project addresses the following business questions:

- How are sales and profits performing overall?
- Which categories and sub-categories contribute most to profitability?
- Which products generate the largest losses?
- How do discount levels relate to profit margins?
- Which customer segments contribute most to sales and profit?
- Which geographic areas demonstrate strong or weak profitability?
- How does performance vary across shipping modes?
- What actions can management take to improve profitability?

## 🎯 Project Objectives

- Translate business problems into measurable analytical requirements.
- Assess data quality and document relevant data considerations.
- Analyze sales, profit, profit margins, discounts, and product performance.
- Identify loss-making products and prioritize business investigations.
- Evaluate customer segment, geographic, and shipping-mode performance.
- Develop interactive Power BI dashboards to communicate findings.
- Turn analytical results into actionable business recommendations.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Data analysis and exploratory data analysis |
| Pandas | Data manipulation and aggregation |
| NumPy | Numerical analysis |
| Matplotlib | Data visualization |
| Jupyter Notebook | Documenting the analytical workflow |
| Power BI | Interactive business intelligence dashboards |
| DAX | Business measures and KPI calculations |
| Git & GitHub | Version control and project documentation |

## 📊 Dataset Overview

The project uses a Sample Superstore-style retail dataset containing order, customer, product, sales, discount, and profit information.

**Original Dataset**

- 10,194 transaction rows
- 21 columns
- 5,111 unique Order IDs
- 1,862 distinct Product IDs

**Historical Analytical Dataset**

- 9,195 transaction rows
- 4,588 unique Order IDs
- Order Dates on or before October 24, 2026

### Key Data Fields

| Field | Description |
|---|---|
| Order ID | Order identifier |
| Order Date | Date the order was placed |
| Ship Date | Date the order was shipped |
| Customer ID | Customer identifier |
| Customer Name | Customer associated with the transaction |
| Segment | Customer segment |
| Region | Sales region |
| State | State or province |
| City | City |
| Category | Main product category |
| Sub-Category | Product sub-category |
| Product ID | Product identifier |
| Product Name | Product description |
| Sales | Recorded sales amount |
| Quantity | Quantity sold |
| Discount | Discount applied |
| Profit | Recorded profit amount |
| Ship Mode | Shipping method |

### Data Quality Considerations

The initial assessment covered completeness, uniqueness, validity, and consistency.

Key findings included:

- No missing values across the 21 columns.
- No exact duplicate rows.
- No duplicate Row IDs.
- No non-positive Sales or Quantity values.
- No negative Discount values or Discount values greater than 1.
- No shipping dates earlier than order dates.
- 1,901 transaction rows with negative Profit values.
- 999 rows with Order Dates after October 24, 2026.
- 1,040 rows with Ship Dates after October 24, 2026.
- 11 repeated Order ID–Product ID combinations, representing 22 rows.

Future-dated records were excluded from the historical analytical extract to establish a consistent reporting period. The original dataset was preserved.

Repeated Order ID–Product ID combinations were retained rather than automatically removed because they may represent separate transaction lines.

Negative Profit values were treated as business signals for profitability analysis, not automatically as data errors.

## 🔍 Analytical Workflow

### 1. Business Understanding

- Defined the fictional ShopSphere business scenario.
- Identified the main profitability challenge.
- Established business questions and analytical objectives.
- Documented business requirements and KPI definitions.

### 2. Data Quality Assessment

- Inspected dataset structure and column data types.
- Checked missing values and exact duplicates.
- Validated sales, quantity, discount, and shipping dates.
- Investigated future-dated orders and repeated order-product combinations.
- Documented data quality findings and analytical considerations.

### 3. Exploratory Data Analysis (Python)

Performed business-focused analysis to understand sales and profitability patterns.

**Baseline Business Performance**

- Total sales and recorded profit.
- Overall profit margin.
- Unique orders and total quantity.
- Comparison between the complete dataset and the historical analytical period.

**Discount & Profitability Analysis**

- Profitability across discount levels.
- Comparison of discount patterns across product categories.
- Identification of discount levels associated with negative aggregate profit.

**Product & Sub-Category Analysis**

- Profitability by category and sub-category.
- Identification of loss-making products.
- Ranking products by financial losses.
- Assessment of loss-making product concentration within sub-categories.

### 4. Power BI Dashboard Development

The completed Power BI report translates the analytical findings into six interactive dashboard pages.

#### Page 1 — Executive Overview

Provides a high-level summary of overall business performance.

- Total Sales
- Total Profit
- Profit Margin %
- Total Orders
- Monthly Sales & Profit Trend
- Sales by Category
- Profit by Region

#### Page 2 — Profitability Analysis

Examines profitability patterns across discounts, categories, and products.

- Profit by Discount Level
- Profit by Sub-Category
- Loss-Making Products
- Profit Margin Analysis
- Average Discount
- Interactive filtering by category, region, and segment

#### Page 3 — Product Performance

Evaluates individual product contributions to business profitability.

- Total Products
- Profitable Products
- Loss-Making Products
- Loss-Making Products %
- Top 10 Profitable Products
- Top 10 Loss-Making Products
- Product Performance Details
- Product-level sales, profit, margin, and discount analysis

#### Page 4 — Customer Segment Performance

Compares business performance across Consumer, Corporate, and Home Office segments.

- Sales by Segment
- Profit by Segment
- Profit Margin by Segment
- Orders by Segment
- Customers by Segment
- Total Customers

#### Page 5 — Geographic Performance

Evaluates sales and profitability across geographic areas.

- Total Sales
- Total Profit
- Profit Margin %
- Geographic Areas Served
- Cities Served
- Sales & Profit by Region
- Geographic Sales Distribution Map
- State/Province Performance
- City Profitability Analysis

#### Page 6 — Shipping Mode Performance

Examines business performance and shipping duration across shipping methods.

- Total Sales
- Total Profit
- Total Orders
- Average Shipping Duration
- Sales by Ship Mode
- Profit by Ship Mode
- Orders by Ship Mode
- Average Shipping Duration by Ship Mode
- Shipping Mode Performance Summary

## 📈 Key Business Findings

The analysis identified several important profitability patterns and areas for further business investigation.

### 1. Overall Business Performance

For orders dated on or before October 24, 2026:

| KPI | Value |
|---|---:|
| Total Sales | $2,115,813.28 |
| Total Profit | $273,117.69 |
| Profit Margin | 12.91% |
| Total Orders | 4,588 |
| Total Quantity | 34,787 |

The historical dataset generated more than $2.1 million in sales and approximately $273K in recorded profit.

### 2. Discount & Profitability

Several higher discount levels recorded negative aggregate profit.

Examples include:

| Discount | Total Profit | Profit Margin |
|---:|---:|---:|
| 30% | -$9,754.22 | -10.14% |
| 40% | -$20,744.63 | -19.55% |
| 50% | -$16,120.13 | -32.40% |
| 70% | -$37,830.61 | -98.37% |
| 80% | -$23,705.38 | -184.70% |

These findings highlight the importance of evaluating discount decisions alongside product-level profitability.

### 3. Sub-Category Profitability

Three sub-categories recorded negative aggregate profit:

| Category | Sub-Category | Total Sales | Total Profit |
|---|---|---:|---:|
| Furniture | Tables | $184,795.12 | -$15,822.42 |
| Furniture | Bookcases | $108,827.77 | -$3,115.69 |
| Office Supplies | Supplies | $43,645.85 | -$1,235.62 |

Tables recorded the largest aggregate sub-category loss, followed by Bookcases.

### 4. Product-Level Losses

Some products generated substantial sales while recording negative profit.

Examples include:

| Product | Total Profit |
|---|---:|
| Cubify CubeX 3D Printer Double Head Print | -$8,879.97 |
| Lexmark MX611dhe Monochrome Laser Printer | -$4,589.97 |
| Chromcraft Bull-Nose Wood Oval Conference Table | -$2,876.12 |
| GBC DocuBind P400 Electric Binding System | -$1,878.17 |

These products highlight the importance of analyzing product-level profitability rather than relying on sales revenue alone.

### 5. Customer Segment Performance

The analysis compares Consumer, Corporate, and Home Office segments.

Key observations:

- Consumer contributes the largest sales, profit, and order volume.
- Corporate records the highest profit margin at approximately 15%.
- Home Office has the lowest sales and order volume among the three segments.

### 6. Geographic Performance

The geographic analysis evaluates business performance at regional, state/province, and city levels.

Key observations:

- Regional comparisons highlight differences in sales and profit contribution.
- State/province analysis helps identify lower-profit geographic areas.
- City-level analysis compares sales and profitability to highlight local performance differences.
- Geographic reach is evaluated using Geographic Areas Served and Cities Served.

### 7. Shipping Mode Performance

The shipping analysis highlights differences in business performance and delivery duration.

Key observations:

- Standard Class contributes the largest sales and profit.
- Same Day records the highest profit margin at approximately 18%.
- Standard Class has the longest average shipping duration at approximately 4.99 days.
- Same Day has the shortest average shipping duration at approximately 0.05 days.
- Overall Average Shipping Duration is approximately 3.96 days.

## 💡 Business Recommendations

Based on the overall analysis, the following actions are recommended:

1. **Improve discount management:** Review higher discount groups associated with negative profitability.
2. **Focus on loss-making products:** Prioritize products with the largest negative profit.
3. **Improve sub-category profitability:** Give particular attention to Tables and Bookcases.
4. **Evaluate customer segments:** Maintain strong-performing segments while exploring opportunities in lower-volume segments.
5. **Monitor geographic performance:** Investigate lower-profit states, provinces, and cities.
6. **Evaluate shipping performance:** Consider sales, profit, order volume, and shipping duration together.
7. **Use profitability-focused KPIs:** Evaluate business performance using profit and margin alongside sales.

## 📁 Project Structure

```text
retail-business-analytics/
│
├── README.md
├── data_catalog.md
│
├── data/
│   ├── shopsphere_raw.xls
│   └── shopsphere_historical.csv
│
├── docs/
│   ├── business_problem.md
│   ├── business_requirements.md
│   ├── data_quality_report.md
│   ├── analysis_plan.md
│   └── business_insights.md
│
├── notebooks/
│   ├── 01_data_quality_assessment.ipynb
│   └── 02_baseline_business_performance.ipynb
│
└── powerbi/
    └── ShopSphere_Retail_Business_Analytics.pbix
```

## 🚀 How to Explore the Project

1. Review `docs/business_problem.md` to understand the business context.
2. Read `docs/business_requirements.md` for business questions and KPI definitions.
3. Explore `data_catalog.md` and `docs/data_quality_report.md` to understand the dataset and its quality assessment.
4. Follow the Python notebooks to explore the analytical workflow.
5. Review `docs/business_insights.md` for detailed findings and recommendations.
6. Open the Power BI report in the `powerbi/` folder to explore the six interactive dashboard pages.

## ⚠️ Limitations

- ShopSphere is a fictional business scenario based on the Sample Superstore dataset.
- The analysis uses the dataset's recorded Profit field, which should not automatically be interpreted as fully loaded net profit.
- Discount and profitability comparisons are descriptive and do not establish causation.
- Shipping duration represents elapsed calendar days, not business days.
- The dataset does not contain Shipping Cost, so shipping cost efficiency cannot be evaluated directly.
- Marketing ROI, customer acquisition cost, and product return rates cannot be calculated from the available fields.

## 👤 Author

**Mohamed Atef**

Computer Science Graduate | Data Analyst & BI Developer

- LinkedIn: [Mohamed Atef](https://www.linkedin.com/in/mohamed-atef22/)
- GitHub: [MohamedAtef721](https://github.com/MohamedAtef721)
- Portfolio: [mohamedatef-ten.vercel.app](https://mohamedatef-ten.vercel.app/)

---

*This project demonstrates an end-to-end, business-oriented analytics workflow, from understanding the business problem and assessing data quality to analyzing profitability, identifying business risks, and communicating actionable insights through interactive Power BI dashboards.*