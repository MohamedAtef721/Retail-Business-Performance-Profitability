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

## 5. Product-Level Loss Analysis

The product-level analysis identified the 15 products with the largest aggregate losses in the date-filtered dataset.

### Finding 6: Losses are concentrated in several identifiable products

The 15 products recorded a combined aggregate loss of approximately 30,409.56.

The largest individual losses were:

| Product | Category | Total Profit | Average Discount |
|---|---|---:|---:|
| Cubify CubeX 3D Printer Double Head Print | Technology | -8,879.97 | 53% |
| Lexmark MX611dhe Monochrome Laser Printer | Technology | -4,589.97 | 40% |
| Chromcraft Bull-Nose Wood Oval Conference Table | Furniture | -2,876.12 | 28% |
| GBC DocuBind P400 Electric Binding System | Office Supplies | -1,878.17 | 45% |
| Cisco TelePresence System EX90 Videoconferencing System | Technology | -1,811.08 | 50% |

**Business implication:** Certain products generate substantial losses despite recording sales. These products warrant further investigation into pricing, costs, discount levels, and transaction-level profitability.

### Finding 7: Machines and Tables warrant further investigation

Several products in the Machines and Tables sub-categories appear among the 15 largest product-level losses.

This pattern suggests that these sub-categories should be investigated further to determine whether losses are concentrated in a few products or reflect a broader profitability issue.

**Recommended action:** Analyze aggregate profit by sub-category, then investigate individual transactions for the products with the largest losses.

### Analytical limitation

The product-level results identify loss-making products but do not establish why the losses occurred. Average discounts are descriptive indicators and should not be treated as proof that discounts caused the losses.

The findings should be validated through sub-category analysis and transaction-level investigation before final pricing recommendations are made.

## Sub-Category Profitability Analysis

The sub-category analysis identified three sub-categories with negative aggregate profit in the date-filtered dataset.

| Category | Sub-Category | Total Sales | Total Profit | Profit Margin |
|---|---|---:|---:|---:|
| Furniture | Tables | 184,795.12 | -15,822.42 | -8.56% |
| Furniture | Bookcases | 108,827.77 | -3,115.69 | -2.86% |
| Office Supplies | Supplies | 43,645.85 | -1,235.62 | -2.83% |

### Finding 8: Furniture contains the most significant sub-category losses

Tables recorded the largest aggregate loss at 15,822.42, followed by Bookcases at 3,115.69.

**Business implication:** Furniture warrants further investigation, particularly the Tables and Bookcases sub-categories, because both generate sales while recording negative aggregate profit.

**Recommended action:** Identify the products responsible for these losses and examine their discount levels and transaction-level profitability before proposing pricing changes.

### Finding 9: Aggregate sub-category profit can hide individual product losses

Machines generated positive aggregate profit of 7,997.60, despite several individual Machines products appearing among the largest loss-making products.

**Business implication:** A profitable sub-category can still contain products that consistently lose money.

**Recommended action:** Evaluate profitability at both sub-category and product levels to avoid overlooking individual products with significant losses.

### Analytical limitation

These findings describe aggregate performance within the observed dataset. They do not establish the causes of the losses or prove that discounts are responsible.

## 6. Cross-Category Interpretation

The findings indicate that profitability patterns differ across product categories.

- Furniture shows negative aggregate profit beginning at the observed 30% discount level.
- Office Supplies shows substantial losses in the observed 70% and 80% discount groups.
- Technology shows negative aggregate profit at several observed discount levels, including 40%, 50%, and 70%.

These observations support a more detailed investigation of discount policies by category and product.

They do not establish a universal discount threshold. Different products may have different cost structures, and the number of observations varies substantially between discount groups.

## 7. Initial Business Recommendations

Based on the current findings, the following actions are proposed for further investigation:

1. **Validate future-dated records** before using the full dataset for historical reporting.
2. **Review high-discount transactions** with negative aggregate profit.
3. **Investigate loss-making products** to determine which products contribute most to total losses.
4. **Evaluate discount policies by category** rather than applying the same assumptions to all products.
5. **Track sales and profitability together**, since high sales do not necessarily indicate strong profitability.
6. **Validate findings at product level** before recommending changes to prices or discount approval rules.

These recommendations are preliminary and should be refined as further analysis becomes available.

## 8. Data and Analytical Limitations

- The business scenario is simulated using the Sample Superstore dataset. The findings should not be interpreted as actual results for a real company named ShopSphere.
- Future-dated records require source validation.
- Repeated Order ID and Product ID combinations have been identified, but their intended transaction-line structure has not yet been confirmed.
- Discount-level comparisons are descriptive and do not prove causation.
- The number of transaction rows varies across discount groups, which can affect the reliability of comparisons.
- The dataset does not contain all information needed to evaluate marketing ROI, shipping cost efficiency, or product returns directly.
- Product-level investigation is still required before making specific pricing recommendations.

## Product Risk Concentration Analysis

The product risk analysis measured the number and proportion of loss-making products within each sub-category.

### Finding 10: Tables has the highest proportion of loss-making products

Furniture - Tables has 41 loss-making products out of 56, representing 73.21% of the products in the sub-category.

The aggregate losses across these loss-making products total 19,557.98, while the overall sub-category profit is -15,822.42.

**Business implication:** Losses in Tables are not limited to a single product. The high proportion of loss-making products suggests a broader profitability concern that warrants further investigation.

### Finding 11: Machines has the largest combined losses among loss-making products

Technology - Machines has 22 loss-making products out of 62, representing 35.48%. These products have combined losses of 20,460.84, even though the sub-category overall reports positive profit of 7,997.60.

**Business implication:** Profitable products offset the losses generated by other products in the same sub-category. Aggregate profitability alone can therefore hide significant product-level risks.

### Finding 12: Bookcases also shows broad product-level profitability concerns

Furniture - Bookcases has 31 loss-making products out of 49, representing 63.27%, with combined losses of 6,833.77 across loss-making products.

**Business implication:** Together, Tables and Bookcases suggest that Furniture should receive priority in the next stage of product-level investigation.

### Recommended investigation priorities

1. **Furniture - Tables:** Investigate the high proportion of loss-making products and the sub-category's negative overall profit.
2. **Technology - Machines:** Identify the products contributing most to losses despite the sub-category's positive overall profit.
3. **Furniture - Bookcases:** Investigate the high proportion of loss-making products and the negative overall profit.
4. **Other sub-categories:** Review loss-making products with material financial impact before considering broader policy changes.

### Interpretation notes

`Total_Product_Loss` is the sum of negative product-level profit values only. It is not the same as the net profit of the entire sub-category, which includes both profitable and loss-making products.

Products with exactly zero profit are excluded from both the loss-making and profitable product counts.

These findings identify where further investigation should be prioritized. They do not establish the causes of losses or prove that discounts are responsible.

## 9. Next Steps

1. Identify the 15 products with the largest aggregate losses.
2. Examine their discount levels, sales, profit, and transaction volumes.
3. Investigate whether losses are concentrated in particular products or sub-categories.
4. Perform time-based analysis after validating the future-dated records.
5. Convert validated findings into business requirements and Power BI visuals.
6. Develop an executive dashboard that connects sales performance, profitability, discount exposure, and product-level risks.

## 10. Current Status

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