# Business Problem Definition — Retail Business Analytics

## 1. Business Context

ShopSphere is a fictional retail company used for this business analytics case study.

The company sells products across multiple categories and serves different customer segments and geographic regions.

Management wants to understand how sales performance relates to profitability and identify opportunities to improve business performance through better pricing, product mix, and sales decisions.

The analysis uses the Sample Superstore dataset as a proxy for the business scenario. ShopSphere is not the verified owner of the dataset, and the business problem is simulated for learning purposes.

## 2. Business Problem Statement

The company is concerned that sales growth may not be translating into proportional profit growth.

Management needs to determine whether profitability challenges are associated with discounting, product mix, customer segments, geographic performance, or changes over time.

The objective is to identify the main drivers of recorded sales and profit, quantify their business impact, and provide evidence-based recommendations that support better commercial decisions.

**Current status:** This is a business hypothesis to investigate, not a confirmed conclusion from the data.

## 3. Business Objectives

The project aims to:

1. Establish a reliable baseline for sales, profit, profit margin, and order volume.
2. Compare sales growth with profit growth over time.
3. Identify products and product categories that contribute most to sales and profit.
4. Investigate loss-making transactions and the factors associated with them.
5. Evaluate the relationship between discount levels and recorded profitability.
6. Compare performance across customer segments, regions, and shipping modes.
7. Translate validated findings into practical recommendations for management.

## 4. Key Stakeholders

| Stakeholder | Primary Concern | Information Needed |
|---|---|---|
| General Manager | Overall business performance | Sales and profit trends, key drivers, recommendations |
| Finance Team | Profitability and financial performance | Profit margins, loss-making products, discount patterns |
| Marketing Team | Sales growth and discount effectiveness | Sales and profitability by discount level, product, and segment |
| Operations Team | Operational performance | Shipping-mode comparisons and product-level performance |
| Business Analyst | Reliable, actionable analysis | Data quality, KPI definitions, validated insights |

These stakeholder roles are part of the simulated business scenario.

## 5. Key Business Questions

### A. Overall Performance
- What are the total sales, total recorded profit, and overall profit margin?
- How do sales and profit change over time?
- Are sales and profit growing at similar rates?

### B. Product Performance
- Which categories and subcategories generate the highest sales?
- Which categories contribute the most profit?
- Which products generate high sales but low profit or losses?

### C. Discount Effectiveness
- How does recorded profitability vary across discount levels?
- Are higher discounts associated with lower profit margins?
- Do some products or categories perform differently under similar discount levels?

### D. Customer and Geographic Performance
- Which customer segments contribute most to sales and profit?
- Which regions perform best and worst?
- Are there segments or regions with high sales but weak profitability?

### E. Shipping Performance
- How do sales and recorded profit vary across shipping modes?
- Are there meaningful differences in order patterns or profitability by shipping mode?

Shipping cost efficiency cannot be measured directly without a suitable shipping-cost field.

## 6. Scope of Analysis

### In Scope
- Data profiling and quality assessment using Python and Pandas.
- Sales and profitability analysis.
- Time-based performance analysis.
- Product, customer segment, geographic, and shipping-mode comparisons.
- Discount and profitability analysis.
- Business recommendations based on validated findings.
- Power BI reporting and interactive business insights.

### Out of Scope
- Direct calculation of marketing campaign ROI.
- Detailed shipping-cost optimization without shipping-cost data.
- Returns analysis without a returns dataset or reliable return indicator.
- Claims about causal relationships based only on descriptive analysis.
- Forecasting or predictive modeling unless justified by the data and business requirements.

## 7. Data and Measurement Considerations

The analysis will use the available Sample Superstore fields, including Sales, Profit, Discount, Quantity, Order Date, Order ID, Category, Sub-Category, Segment, Region, and Ship Mode.

The following principles will guide the analysis:

- Count orders using distinct Order IDs rather than counting transaction rows.
- Calculate overall profit margin as total recorded profit divided by total sales.
- Treat negative profit as a business signal to investigate, not automatically as a data error.
- Validate the date range and missing values before finalizing time-based conclusions.
- Avoid interpreting associations as proof of causation.
- Verify the meaning and limitations of the recorded Profit measure before describing it as net profit.

## 8. Expected Deliverables

1. Data catalog and data quality report.
2. Reproducible Python analysis and documented cleaning decisions.
3. Business KPI definitions and baseline performance results.
4. Exploratory analysis of the key business questions.
5. Power BI report with relevant metrics and interactive analysis.
6. Final business insights and prioritized recommendations.

## 9. Definition of Success

The project will be considered successful when it:

- Establishes trustworthy baseline performance metrics.
- Identifies and quantifies the main observed drivers of profitability.
- Distinguishes confirmed findings from assumptions and data limitations.
- Provides actionable recommendations tied to evidence.
- Communicates the findings clearly enough to support management decisions.

## 10. Next Step

Complete the data quality assessment, validate the dataset's date range and record-level grain, and document any cleaning decisions before calculating the baseline KPIs.
