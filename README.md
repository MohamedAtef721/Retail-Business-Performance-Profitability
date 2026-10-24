# ShopSphere | Retail Business Performance & Profitability Analysis

**Turning Retail Data into Business Insights and Profitability Improvements**

## 📌 Project Overview

ShopSphere is a business analytics case study focused on understanding retail sales performance, identifying profitability issues, and supporting data-driven business decisions.

The project simulates a business scenario in which a retail company generates substantial sales but faces profitability challenges across certain products and sub-categories.

Using a Sample Superstore dataset, the analysis follows a business-oriented workflow, starting with business requirements and data quality assessment, followed by exploratory data analysis using Python and an interactive Power BI dashboard.

> **Note:** ShopSphere is a fictional business scenario. The analysis is based on the available dataset and does not represent actual company records.

## 🎯 Business Problem

High sales do not necessarily translate into high profits. Retail businesses need to understand which products generate losses, how discount levels relate to profitability, and where management should focus its improvement efforts.

This project addresses the following business questions:

- How are sales and profits performing overall?
- Which categories and sub-categories contribute most to profitability?
- Which products generate the largest losses?
- How are discount levels associated with profit margins?
- Which products require further pricing and cost investigation?
- What actions can management take to improve profitability?

## 🎯 Project Objectives

- Translate business problems into measurable analytical requirements.
- Assess data quality and identify potential reliability issues.
- Analyze sales, profit, profit margins, discounts, and product performance.
- Identify loss-making products and prioritize business investigations.
- Develop interactive Power BI reports to communicate findings.
- Turn analytical results into actionable business recommendations.

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Data analysis and exploratory analysis |
| Pandas | Data manipulation and aggregation |
| NumPy | Numerical analysis |
| Matplotlib | Data visualization |
| Jupyter Notebook | Documenting the analytical workflow |
| Power BI | Interactive business intelligence dashboards |
| DAX | Business measures and KPI calculations |
| Git & GitHub | Version control and project documentation |

## 📊 Dataset Overview

The project uses a Sample Superstore-style retail dataset containing order, customer, product, sales, discount, and profit information.

**Original dataset:**
- 10,194 rows
- 21 columns
- 5,111 unique order IDs

**Historical analytical dataset:**
- 9,195 rows
- 4,588 unique order IDs
- Orders dated on or before October 24, 2026

### Key Data Fields

| Field | Description |
|---|---|
| Order ID | Unique order identifier |
| Order Date | Date the order was placed |
| Ship Date | Date the order was shipped |
| Customer Name | Customer associated with the transaction |
| Segment | Customer segment |
| Region | Sales region |
| Category | Main product category |
| Sub-Category | Product sub-category |
| Product Name | Product description |
| Sales | Recorded sales amount |
| Quantity | Quantity sold |
| Discount | Discount applied |
| Profit | Recorded profit amount |

### Data Quality Considerations

The initial assessment identified the following:

- No missing values across the 21 columns.
- No exact duplicate rows.
- No duplicate Row IDs.
- No negative sales or quantities.
- No shipping dates earlier than order dates.
- 999 rows with order dates after October 24, 2026.
- 11 repeated Order ID–Product ID combinations requiring further investigation.

Future-dated records were excluded from the historical analytical extract to support a time-bounded analysis. The original data remains unchanged, and the exclusion is an analytical decision rather than confirmation that those records are invalid.

Repeated order-product combinations were retained because they may represent legitimate transactions and should not be removed without verifying the source data's grain.

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
- Documented data quality findings and limitations.

### 3. Exploratory Data Analysis (Python)

Performed business-focused analysis to understand sales and profitability patterns.

**Baseline Performance**
- Total sales and profit.
- Overall profit margin.
- Unique orders and total quantity.
- Comparison between the complete dataset and the historical analytical period.

**Discount Analysis**
- Profitability across discount levels.
- Comparison of discount patterns across product categories.
- Identification of discount levels associated with negative aggregate profit.

**Product & Sub-Category Analysis**
- Profitability by category and sub-category.
- Identification of loss-making products.
- Ranking products by financial losses.
- Assessment of the concentration of loss-making products within sub-categories.

### 4. Power BI Dashboard

The planned dashboard will translate the Python findings into interactive reports for business stakeholders.

**Page 1 — Executive Overview**
- Total Sales
- Total Profit
- Profit Margin
- Total Orders
- Total Quantity
- Sales and profit trends over time

**Page 2 — Profitability Analysis**
- Profit by category and sub-category
- Profit margin comparison
- Discount versus profitability analysis
- Identification of underperforming areas

**Page 3 — Product Performance**
- Top and bottom products by profit
- Loss-making product analysis
- Product-level sales, profit, and discount details
- Interactive filtering and drill-down analysis

## 📈 Preliminary Business Findings

The initial analysis produced several findings that warrant further business investigation.

### 1. Overall Profitability

For orders dated on or before October 24, 2026:

| KPI | Value |
|---|---:|
| Total Sales | 2,115,813.28 |
| Total Profit | 273,117.69 |
| Profit Margin | 12.91% |
| Unique Orders | 4,588 |
| Total Quantity | 34,787 |

*These figures reflect the historical analytical extract and the dataset's recorded Profit field.*

### 2. Furniture — Tables

- 41 of 56 products were loss-making (73.21%).
- The sub-category recorded an overall loss of 15,822.42.
- The concentration of loss-making products suggests a broader profitability concern.

**Business implication:** Investigate product costs, selling prices, and discount practices across the sub-category.

### 3. Technology — Machines

- 22 of 62 products were loss-making (35.48%).
- Losses across those loss-making products totaled 20,460.84.
- Despite these product-level losses, the sub-category generated an overall profit of 7,997.60.

**Business implication:** Profitable products can offset losses elsewhere, making product-level analysis essential.

### 4. Furniture — Bookcases

- 31 of 49 products were loss-making (63.27%).
- The sub-category recorded an overall loss of 3,115.69.

**Business implication:** Prioritize investigation of loss-making products and evaluate whether pricing or cost adjustments are justified.

### 5. Product-Level Losses

The Cubify CubeX 3D Printer Double Head Print recorded:

- Sales: 11,099.96
- Profit: -8,879.97
- Average discount: 53%
- Profit margin: -80%

The Cisco TelePresence System EX90 also recorded a loss of 1,811.08 despite sales of 22,638.48.

**Business implication:** High revenue does not guarantee profitability. Product-level costs and pricing should be reviewed alongside sales and discounts.

### Important Interpretation Note

These findings describe patterns in the available data; they do not establish causation. In particular, high discounts may be associated with negative profitability, but the analysis alone cannot prove that discounts caused the losses.

## 💡 Business Recommendations

Based on the preliminary findings:

1. Prioritize investigation of loss-making products in Tables, Bookcases, and Machines.
2. Review product costs and selling prices for products with substantial losses.
3. Evaluate discount practices using product-level profit margins.
4. Monitor revenue and profitability together rather than relying on sales alone.
5. Use the Power BI dashboard to identify emerging risks and support ongoing performance monitoring.

Recommendations should be validated against reliable cost and pricing records before commercial policies are changed.

## 📁 Project Structure

```text
retail-business-analytics/
│
├── README.md
├── data_catalog.md
│
├── data/
│   ├── README.md
│   ├── raw/
│   └── processed/
│       └── shopsphere_historical.csv
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
├── src/
│   └── data_quality.py
│
├── reports/
│
└── powerbi/
    └── README.md
```

*The structure represents the intended project organization; files and folders may be added as development progresses.*

## 🚀 How to Explore the Project

1. Review `docs/business_problem.md` to understand the business context.
2. Read `docs/business_requirements.md` for the business questions and KPIs.
3. Explore `data_catalog.md` and `docs/data_quality_report.md` to understand the dataset and its limitations.
4. Follow the Python notebooks to reproduce the analysis.
5. Review `docs/business_insights.md` for analytical findings and recommendations.
6. Open the Power BI report when the dashboard implementation is available.

## ⚠️ Limitations

- The dataset is used for an analytical case study and is not verified company data.
- Future-dated records require context before they can be interpreted as invalid.
- The recorded Profit field has not been independently reconciled against accounting records.
- Marketing costs, shipping costs, and returns information are not available for direct analysis.
- The relationship between discounts and profitability is descriptive, not causal.

## 👤 Author

**Mohamed Atef**

Computer Science Graduate | Data Analyst & BI Developer

- GitHub: [MohamedAtef721](https://github.com/MohamedAtef721)
- Portfolio: [mohamedatef-ten.vercel.app](https://mohamedatef-ten.vercel.app/)

---

*This project demonstrates a business-oriented analytics workflow, from understanding the business problem and assessing data quality to identifying profitability risks and communicating actionable insights.*

01_data_quality_assessment.ipynb