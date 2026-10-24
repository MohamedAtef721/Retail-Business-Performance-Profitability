# Business Insights & Findings

## 1. Overview

This document records the business insights identified during the Retail Business Analytics project using the Sample Superstore dataset.

The objective is to understand sales performance, profitability, and potential business risks through data-driven analysis.

The project follows a structured analytical approach:

1. Assess data quality and identify potential data issues.
2. Establish baseline business performance.
3. Investigate profitability across discount levels.
4. Compare discount-related profitability patterns across product categories.
5. Identify loss-making products and investigate potential causes.
6. Translate validated findings into actionable business recommendations.

**Current status:** Initial baseline analysis and discount profitability analysis completed. Product-level investigation is the next step.

## 2. Baseline Business Performance

The initial baseline was calculated using the full dataset and compared with records whose Order Date is on or before October 24, 2026.

| KPI | Full Dataset | As of October 24, 2026 |
|---|---:|---:|
| Transaction Rows | 10,194 | 9,195 |
| Total Sales | 2,326,534.35 | 2,115,813.28 |
| Total Profit | 292,296.81 | 273,117.69 |
| Profit Margin | 12.56% | 12.91% |
| Distinct Orders | 5,111 | 4,588 |
| Total Quantity | 38,654 | 34,787 |

### Finding 1: Future-dated records affect reported performance

The full dataset contains 999 transaction rows with Order Dates later than October 24, 2026.

Including all records increases reported sales by 210,721.07 and reported profit by 19,179.12 compared with the date-filtered dataset.

However, the overall profit margin decreases from 12.91% to 12.56%.

**Business implication:** Unverified future-dated records can affect financial KPIs and time-based comparisons.

**Recommended action:** Investigate the source and business meaning of these dates before finalizing historical performance reporting. Do not delete the records without sufficient evidence.

## 3. Discount and Profitability Analysis

Profitability was analyzed across discount levels using records with Order Dates on or before October 24, 2026.

Profit Margin is calculated as:

`Profit Margin = Total Profit / Total Sales × 100`

### Finding 2: High discount levels are associated with negative profitability

The analysis identified several discount levels with negative aggregate profit.

| Discount | Total Sales | Total Profit | Profit Margin |
|---:|---:|---:|---:|
| 30% | 96,218.60 | -9,754.22 | -10.14% |
| 40% | 106,128.86 | -20,744.63 | -19.55% |
| 50% | 49,747.94 | -16,120.13 | -32.40% |
| 60% | 6,128.19 | -5,212.27 | -85.05% |
| 70% | 38,457.31 | -37,830.61 | -98.37% |
| 80% | 12,834.68 | -23,705.38 | -184.70% |

**Business implication:** Some high-discount transactions may be contributing to substantial financial losses.

**Recommended action:** Review the profitability of heavily discounted products and investigate whether discount approval rules or minimum margin thresholds are needed.

**Important limitation:** These results show an association between discount levels and profitability. They do not prove that discounts alone caused the losses. Product costs, product mix, pricing, and other factors may also influence profitability.

## 4. Category-Level Profitability Findings

The discount analysis was extended to Furniture, Office Supplies, and Technology to identify differences across product categories.

### Finding 3: Furniture profitability declines at higher discount levels

| Discount | Total Profit | Profit Margin |
|---:|---:|---:|
| 0% | 53,738.95 | 23.00% |
| 10% | 6,533.59 | 15.04% |
| 20% | 6,317.22 | 3.13% |
| 30% | -10,080.25 | -10.90% |
| 40% | -14,132.41 | -35.83% |

**Business implication:** Furniture shows a substantial decline in aggregate profitability as discounts increase across the observed groups.

**Recommended action:** Investigate furniture products sold at discounts of 30% or more and assess whether their pricing and discount policies protect target margins.

### Finding 4: High discounts are associated with losses in Office Supplies

| Discount | Total Profit | Profit Margin |
|---:|---:|---:|
| 0% | 122,713.59 | 29.93% |
| 10% | 1,086.08 | 25.12% |
| 20% | 35,499.93 | 16.33% |
| 70% | -15,705.87 | -73.58% |
| 80% | -23,705.38 | -184.70% |

**Business implication:** The highest observed discount levels in Office Supplies are associated with substantial aggregate losses.

**Recommended action:** Examine the products sold at 70% and 80% discounts, considering both total loss and the number of transaction rows.

### Finding 5: Technology profitability also becomes negative at higher discounts

| Discount | Total Profit | Profit Margin |
|---:|---:|---:|
| 0% | 119,931.01 | 33.75% |
| 10% | 832.08 | 24.39% |
| 20% | 42,835.81 | 14.61% |
| 40% | -6,582.89 | -9.88% |
| 50% | -3,515.46 | -12.05% |
| 70% | -18,579.36 | -125.09% |

**Business implication:** Technology has strong aggregate profitability in the zero-discount group, while some higher-discount groups generate negative profit.

**Recommended action:** Investigate the products contributing to these losses before recommending category-wide discount restrictions.

## 5. Cross-Category Interpretation

The findings indicate that profitability patterns differ across product categories.

- Furniture shows negative aggregate profit beginning at the observed 30% discount level.
- Office Supplies shows substantial losses in the observed 70% and 80% discount groups.
- Technology shows negative aggregate profit at several observed discount levels, including 40%, 50%, and 70%.

These observations support a more detailed investigation of discount policies by category and product.

They do not establish a universal discount threshold. Different products may have different cost structures, and the number of observations varies substantially between discount groups.

## 6. Initial Business Recommendations

Based on the current findings, the following actions are proposed for further investigation:

1. **Validate future-dated records** before using the full dataset for historical reporting.
2. **Review high-discount transactions** with negative aggregate profit.
3. **Investigate loss-making products** to determine which products contribute most to total losses.
4. **Evaluate discount policies by category** rather than applying the same assumptions to all products.
5. **Track sales and profitability together**, since high sales do not necessarily indicate strong profitability.
6. **Validate findings at product level** before recommending changes to prices or discount approval rules.

These recommendations are preliminary and should be refined as further analysis becomes available.

## 7. Data and Analytical Limitations

- The business scenario is simulated using the Sample Superstore dataset. The findings should not be interpreted as actual results for a real company named ShopSphere.
- Future-dated records require source validation.
- Repeated Order ID and Product ID combinations have been identified, but their intended transaction-line structure has not yet been confirmed.
- Discount-level comparisons are descriptive and do not prove causation.
- The number of transaction rows varies across discount groups, which can affect the reliability of comparisons.
- The dataset does not contain all information needed to evaluate marketing ROI, shipping cost efficiency, or product returns directly.
- Product-level investigation is still required before making specific pricing recommendations.

## 8. Next Steps

1. Identify the 15 products with the largest aggregate losses.
2. Examine their discount levels, sales, profit, and transaction volumes.
3. Investigate whether losses are concentrated in particular products or sub-categories.
4. Perform time-based analysis after validating the future-dated records.
5. Convert validated findings into business requirements and Power BI visuals.
6. Develop an executive dashboard that connects sales performance, profitability, discount exposure, and product-level risks.

## 9. Current Status

**Completed**
- Initial data quality assessment.
- Baseline business performance calculation.
- Discount-level profitability analysis.
- Category-level discount profitability analysis.

**In Progress**
- Product-level loss investigation.
- Validation of future-dated records.
- Finalization of business recommendations.

The project will continue to prioritize validated business findings over assumptions, with each recommendation supported by documented analysis.