# Business Requirements — Retail Business Analytics

## 1. Document Purpose

This document translates the business problem into measurable analytical requirements for the ShopSphere retail case study.

The requirements define the business questions, required metrics, relevant data fields, analytical methods, and intended decision outcomes.

ShopSphere is a fictional business scenario. The Sample Superstore dataset is used as a proxy dataset for analysis.

## 2. Business Requirements

### BR-01: Establish Overall Business Performance

**Business Question:** What is the company's current sales and profitability performance?

**Requirements:**
- Calculate total sales.
- Calculate total recorded profit.
- Calculate overall profit margin.
- Count distinct orders.
- Calculate total quantity sold.

**Required Fields:** `Sales`, `Profit`, `Order ID`, `Quantity`

**Analytical Method:** Aggregation using Python and Pandas.

**Expected Output:** A baseline KPI summary.

**Business Decision Supported:** Establish a reference point for evaluating business performance.

**Acceptance Criteria:**
- Total sales and profit are calculated from the available records.
- Order count uses distinct Order IDs.
- Overall profit margin is calculated as total profit divided by total sales.

### BR-02: Analyze Sales and Profit Trends

**Business Question:** Are sales and profit changing at the same rate over time?

**Requirements:**
- Aggregate sales and profit by month.
- Compare monthly and annual performance where the date range supports it.
- Calculate sales growth and profit growth between comparable periods.
- Investigate unusual changes in sales or profitability.

**Required Fields:** `Order Date`, `Sales`, `Profit`, `Order ID`

**Analytical Method:** Time-series aggregation and period-over-period comparisons.

**Expected Output:** Monthly performance trends and growth comparisons.

**Business Decision Supported:** Identify periods where sales growth does not translate into proportional profit growth.

**Acceptance Criteria:**
- Periods are compared consistently.
- Incomplete periods are identified.
- Future-dated records are investigated before final conclusions.

### BR-03: Evaluate Product and Category Profitability

**Business Question:** Which products and product groups contribute most to sales and profit?

**Requirements:**
- Compare sales and profit by category and subcategory.
- Rank products by sales and recorded profit.
- Identify products with negative recorded profit.
- Identify products with high sales but relatively weak profitability.

**Required Fields:** `Product ID`, `Product Name`, `Category`, `Sub-Category`, `Sales`, `Profit`, `Quantity`

**Analytical Method:** Grouping, aggregation, ranking, and profitability comparisons.

**Expected Output:** Product and category performance analysis.

**Business Decision Supported:** Identify product groups that may require pricing, assortment, or cost-related investigation.

**Acceptance Criteria:**
- Sales and profit are reported separately.
- Loss-making products are identified using aggregated profit, not a single transaction alone.
- Rankings are based on clearly defined metrics.

### BR-04: Investigate Discount Effectiveness

**Business Question:** How are discount levels associated with sales and recorded profitability?

**Requirements:**
- Examine sales, profit, and profit margin across discount levels.
- Compare results across product categories and subcategories.
- Identify cases where higher discounts coincide with weak profitability.
- Investigate whether discount patterns differ across customer segments.

**Required Fields:** `Discount`, `Sales`, `Profit`, `Category`, `Sub-Category`, `Segment`

**Analytical Method:** Grouped comparisons and descriptive analysis.

**Expected Output:** Discount and profitability analysis.

**Business Decision Supported:** Support evidence-based review of discount policies.

**Acceptance Criteria:**
- Discount groups are documented and consistently applied.
- Comparisons include both sales and profitability.
- Results are described as associations, not proof that discounts caused a change in profit.

### BR-05: Compare Customer Segment Performance

**Business Question:** Which customer segments contribute most to sales and recorded profit?

**Requirements:**
- Compare sales, profit, and profit margin by segment.
- Compare order volume across segments.
- Identify segments with strong sales but relatively weak profitability.

**Required Fields:** `Segment`, `Order ID`, `Sales`, `Profit`, `Quantity`

**Analytical Method:** Grouped aggregation and comparison.

**Expected Output:** Customer segment performance summary.

**Business Decision Supported:** Identify segments that may warrant further commercial investigation.

### BR-06: Compare Geographic Performance

**Business Question:** Which regions generate the strongest sales and profitability?

**Requirements:**
- Compare sales and profit by region.
- Examine state- or city-level performance where the data is sufficiently reliable.
- Identify geographic areas with negative or weak recorded profit.

**Required Fields:** `Region`, `State/Province`, `City`, `Sales`, `Profit`, `Order ID`

**Analytical Method:** Geographic grouping and performance ranking.

**Expected Output:** Regional performance comparison.

**Business Decision Supported:** Identify geographic areas for deeper sales or profitability investigation.

### BR-07: Examine Shipping-Mode Performance

**Business Question:** How does recorded business performance vary by shipping mode?

**Requirements:**
- Compare sales, profit, order count, and available order-level patterns by shipping mode.
- Examine shipping duration using Order Date and Ship Date if useful.
- Avoid interpreting recorded profit differences as shipping-cost differences without cost data.

**Required Fields:** `Ship Mode`, `Order Date`, `Ship Date`, `Order ID`, `Sales`, `Profit`

**Analytical Method:** Grouped comparisons and date-difference calculations.

**Expected Output:** Shipping-mode performance analysis.

**Business Decision Supported:** Identify patterns that may warrant further operational investigation.

### BR-08: Assess Data Reliability

**Business Question:** Is the dataset sufficiently reliable for business reporting?

**Requirements:**
- Check missing values and data types.
- Validate key identifiers and record-level grain.
- Investigate date ranges and future-dated records.
- Review negative profit values without automatically removing them.
- Document cleaning decisions and remaining limitations.

**Required Fields:** All available columns.

**Analytical Method:** Data profiling, validation rules, and documented quality checks.

**Expected Output:** Data quality report and a reproducible preparation process.

**Business Decision Supported:** Establish confidence in the analytical results and identify limitations.

## 3. KPI Definitions

| KPI | Definition | Important Consideration |
|---|---|---|
| Total Sales | Sum of `Sales` | Depends on the validity of the sales records |
| Total Recorded Profit | Sum of `Profit` | Not automatically equivalent to fully loaded net profit |
| Overall Profit Margin | Total Profit / Total Sales | Use aggregated totals, not the average of row-level margins |
| Total Orders | Distinct count of `Order ID` | Do not count transaction rows as orders |
| Total Quantity Sold | Sum of `Quantity` | Represents units recorded in the dataset |
| Sales Growth | (Current Period Sales - Previous Comparable Period Sales) / Previous Comparable Period Sales | Requires comparable periods and a nonzero prior-period value |
| Profit Growth | (Current Period Profit - Previous Comparable Period Profit) / Previous Comparable Period Profit | Requires careful handling of zero or negative prior-period profit |
| Loss-Making Product | Product with aggregated recorded profit below zero | Aggregate by product before classifying |
| Shipping Duration | Ship Date minus Order Date | Measures elapsed calendar days, not necessarily business days |

## 4. General Acceptance Criteria

The analysis must:
- Use documented KPI definitions.
- Apply consistent aggregation and filtering rules.
- Distinguish data quality issues from legitimate business outcomes.
- State limitations where required fields are unavailable.
- Support conclusions with measurable results.
- Avoid unsupported causal claims.
- Produce findings that can be communicated clearly to business stakeholders.

## 5. Requirement-to-Deliverable Mapping

| Requirement | Planned Deliverable |
|---|---|
| BR-01 | Baseline KPI summary |
| BR-02 | Sales and profit trend analysis |
| BR-03 | Product and category profitability analysis |
| BR-04 | Discount analysis |
| BR-05 | Customer segment analysis |
| BR-06 | Geographic analysis |
| BR-07 | Shipping-mode analysis |
| BR-08 | Data quality report |

## 6. Next Steps

1. Complete data quality validation.
2. Confirm the dataset's row-level grain.
3. Establish the baseline KPIs.
4. Analyze each business requirement using Python.
5. Translate validated findings into Power BI reporting requirements.
6. Document insights and recommendations.
