# ShopSphere | Retail Business Performance & Profitability
## Business Insights & Findings

## 1. Executive Summary

This report presents the key business insights identified through the ShopSphere Retail Business Performance & Profitability Analysis project.

The analysis focuses on sales performance, profitability, discount patterns, product performance, customer segments, geographic performance, and shipping modes.

The findings highlight areas of strong performance as well as opportunities to improve profitability, manage discount exposure, and identify loss-making products and sub-categories.

## 2. Scope and Analytical Approach

The project uses the Sample Superstore dataset as the basis for a simulated retail business case study.

The analysis covers:

1. Overall sales and profitability performance.
2. Monthly sales and profit trends.
3. Profitability across discount levels.
4. Product and sub-category performance.
5. Customer segment performance.
6. Geographic sales and profitability.
7. Shipping mode performance.

The analysis uses descriptive measures, including Total Sales, Total Profit, Profit Margin, Total Orders, Total Quantity, and Average Discount.

## 3. Baseline Business Performance

The historical analysis includes records with Order Dates on or before October 24, 2026.

| KPI | Historical Performance |
|---|---:|
| Transaction Rows | 9,195 |
| Total Sales | $2,115,813.28 |
| Total Profit | $273,117.69 |
| Profit Margin | 12.91% |
| Total Orders | 4,588 |
| Total Quantity | 34,787 |

The business generated more than $2.1 million in sales and approximately $273K in recorded profit, with an overall profit margin of 12.91%.

## 4. Executive Overview and Time-Based Performance

The Executive Overview provides a high-level view of the business through key performance indicators and time-based analysis.

The dashboard highlights:

- Total Sales and Total Profit.
- Overall Profit Margin.
- Total Orders.
- Monthly Sales and Profit Trends.
- Sales by Category.
- Profit by Region.

These metrics provide a consolidated view of business performance and help identify changes in sales activity and profitability over time.

## 5. Discount and Profitability Analysis

The analysis compares profitability across different discount levels to identify discount groups associated with positive and negative profit.

### Key Finding: Higher discount levels are associated with negative profitability

| Discount | Total Sales | Total Profit | Profit Margin |
|---:|---:|---:|---:|
| 30% | $96,218.60 | -$9,754.22 | -10.14% |
| 40% | $106,128.86 | -$20,744.63 | -19.55% |
| 50% | $49,747.94 | -$16,120.13 | -32.40% |
| 60% | $6,128.19 | -$5,212.27 | -85.05% |
| 70% | $38,457.31 | -$37,830.61 | -98.37% |
| 80% | $12,834.68 | -$23,705.38 | -184.70% |

The results show that several higher discount groups generate negative aggregate profit.

### Category-Level Findings

**Furniture**

Furniture profitability declines across the observed discount groups, with negative aggregate profit at discount levels of 30% and 40%.

**Office Supplies**

The 70% and 80% discount groups generate substantial aggregate losses.

**Technology**

Technology records strong profitability in the zero-discount group, while several higher discount groups generate negative aggregate profit.

### Business Recommendations

- Review products associated with high discount levels and negative profit.
- Evaluate discount policies separately across product categories.
- Consider minimum profit margin thresholds when reviewing discount decisions.
- Monitor profit and profit margin alongside sales when evaluating discount performance.

These findings describe observed relationships between discount levels and profitability.

## 6. Product Performance and Profitability

Product performance analysis evaluates products based on sales, profit, and profit margin.

The dashboard includes:

- Total Products.
- Profitable Products.
- Loss-Making Products.
- Loss-Making Products %.
- Top 10 Profitable Products.
- Top 10 Loss-Making Products.
- Product Performance Details.

### Key Finding: Product sales do not always translate into profitability

Some products generate substantial sales while recording negative profit.

The largest individual product losses include:

| Product | Category | Total Profit |
|---|---|---:|
| Cubify CubeX 3D Printer Double Head Print | Technology | -$8,879.97 |
| Lexmark MX611dhe Monochrome Laser Printer | Technology | -$4,589.97 |
| Chromcraft Bull-Nose Wood Oval Conference Table | Furniture | -$2,876.12 |
| GBC DocuBind P400 Electric Binding System | Office Supplies | -$1,878.17 |
| Cisco TelePresence System EX90 Videoconferencing System | Technology | -$1,811.08 |

### Business Recommendations

- Review products with the largest negative profit.
- Evaluate selling prices, costs, and discount levels.
- Monitor product-level profit margins.
- Prioritize products based on their contribution to overall losses.

## 7. Sub-Category Profitability and Risk Concentration

The sub-category analysis identifies areas with negative aggregate profit.

| Category | Sub-Category | Total Sales | Total Profit | Profit Margin |
|---|---|---:|---:|---:|
| Furniture | Tables | $184,795.12 | -$15,822.42 | -8.56% |
| Furniture | Bookcases | $108,827.77 | -$3,115.69 | -2.86% |
| Office Supplies | Supplies | $43,645.85 | -$1,235.62 | -2.83% |

### Key Finding: Furniture contains the largest sub-category losses

Tables records the largest aggregate loss, followed by Bookcases.

The product risk analysis also highlights a high proportion of loss-making products in these sub-categories.

- Tables: 41 loss-making products out of 56 (73.21%).
- Bookcases: 31 loss-making products out of 49 (63.27%).
- Machines: 22 loss-making products out of 62 (35.48%).

Machines generates positive overall sub-category profit of $7,997.60, despite losses across several individual products.

### Business Recommendations

- Prioritize Tables and Bookcases for profitability improvement.
- Investigate loss-making products within Machines.
- Evaluate performance at both product and sub-category levels.
- Monitor the concentration of losses across products.

## 8. Customer Segment Performance

The customer segment analysis compares Consumer, Corporate, and Home Office performance.

| Segment | Orders | Total Sales | Total Profit | Profit Margin |
|---|---:|---:|---:|---:|
| Consumer | 2,349 | $1.065M | $124K | 12% |
| Corporate | 1,395 | $0.649M | $94K | 15% |
| Home Office | 844 | $0.402M | $55K | 14% |

### Key Findings

- Consumer is the largest segment in sales, profit, and order volume.
- Corporate records the highest profit margin at approximately 15%.
- Home Office has the lowest sales and order volume among the three segments.

The dashboard also evaluates customer distribution using Total Customers and Customers by Segment.

### Business Recommendations

- Maintain the Consumer segment's strong sales contribution.
- Examine the practices and product mix associated with Corporate's higher margin.
- Explore opportunities to increase Home Office sales and customer activity.
- Evaluate customer volume alongside revenue and profitability.

## 9. Geographic Performance

Geographic Performance examines sales and profitability across regions, states or provinces, and cities.

The analysis uses the following KPIs:

- Total Sales.
- Total Profit.
- Profit Margin %.
- Geographic Areas Served.
- Cities Served.

### Regional Performance

The regional analysis compares the four business regions:

- West
- East
- Central
- South

Sales and profit are evaluated together to identify regions contributing most to overall business performance.

### Geographic Sales Distribution

The geographic map displays sales distribution across locations using city, state or province, and country information.

This provides a geographic view of business reach and sales concentration.

### State/Province Performance

The State/Province Performance visual highlights locations with the lowest total profit.

This helps identify geographic areas that may require closer attention to improve profitability.

### City Profitability Analysis

The city-level scatter chart compares Total Sales and Total Profit.

It also uses order volume to provide additional context when evaluating city performance.

### Key Business Insights

- Regional performance provides an overview of sales and profit contribution.
- State and province analysis helps identify lower-profit geographic areas.
- City-level analysis highlights differences in sales and profitability across locations.
- Geographic performance should be evaluated using both revenue and profit rather than sales alone.

### Business Recommendations

- Monitor sales and profit across all regions.
- Investigate states and provinces with negative or low profit.
- Evaluate cities with high sales but relatively low profitability.
- Use geographic performance to support regional planning and resource allocation.

## 10. Shipping Mode Performance

The shipping analysis compares performance across the available shipping modes.

The dashboard evaluates:

- Total Sales by Ship Mode.
- Total Profit by Ship Mode.
- Total Orders by Ship Mode.
- Average Shipping Duration.
- Profit Margin by Ship Mode.

### Key Findings

- Standard Class contributes the largest sales and profit.
- Same Day records the highest profit margin at approximately 18%.
- Standard Class has the longest average shipping duration at approximately 4.99 days.
- Same Day has the shortest average shipping duration at approximately 0.05 days.
- Overall Average Shipping Duration is approximately 3.96 days.

Shipping duration is calculated as the elapsed calendar days between Order Date and Ship Date.

### Business Recommendations

- Continue monitoring the contribution of each shipping mode to sales and profit.
- Compare shipping duration alongside order volume and profitability.
- Evaluate the relationship between delivery speed and customer service objectives.
- Monitor shipping mode performance over time.

## 11. Consolidated Business Recommendations

Based on the overall analysis, the following actions are recommended:

1. **Improve discount management:** Review high-discount groups associated with negative profitability.
2. **Focus on loss-making products:** Prioritize products with the largest negative profit.
3. **Improve sub-category profitability:** Give particular attention to Tables and Bookcases.
4. **Evaluate customer segments:** Maintain strong-performing segments while exploring growth opportunities in lower-volume segments.
5. **Monitor geographic performance:** Identify and investigate lower-profit states, provinces, and cities.
6. **Evaluate shipping performance:** Consider sales, profit, order volume, and shipping duration together.
7. **Use profitability-focused KPIs:** Evaluate business performance using profit and margin alongside sales.

## 12. Data Quality and Analytical Limitations

The project uses the Sample Superstore dataset as a proxy for a simulated retail business scenario. The findings should not be interpreted as actual results for a real company named ShopSphere.

The analysis is based on the dataset's recorded fields and measures.

Key analytical considerations:

- Discount comparisons are descriptive and do not establish causation.
- Shipping duration represents elapsed calendar days, not business days.
- The dataset does not contain Shipping Cost, so shipping cost efficiency cannot be evaluated directly.
- The dataset does not provide sufficient information to calculate marketing ROI or customer acquisition cost.
- Product returns are not included in the available analysis.
- Total Recorded Profit should be interpreted according to the dataset's recorded Profit field.

## 13. Next Steps

The project can be extended through:

1. Further investigation of loss-making products and sub-categories.
2. More detailed analysis of product and discount combinations.
3. Monitoring profitability trends over time.
4. Deeper investigation of geographic performance.
5. Continued evaluation of customer segment performance.
6. Development of additional performance measures as more business data becomes available.

## 14. Power BI Project Status

The Power BI report includes the following dashboard pages:

| Page | Dashboard |
|---|---|
| 01 | Executive Overview |
| 02 | Profitability Analysis |
| 03 | Product Performance |
| 04 | Customer Segment Performance |
| 05 | Geographic Performance |
| 06 | Shipping Mode Performance |

Each page provides a focused view of business performance and supports the overall objective of understanding sales, profitability, and operational patterns.

## 15. Conclusion

The ShopSphere Retail Business Performance & Profitability Analysis provides an integrated view of business performance across sales, profitability, products, customer segments, geography, and shipping modes.

The analysis highlights the importance of evaluating profitability alongside revenue, identifying loss-making products, managing discount exposure, and monitoring performance across different business dimensions.

The Power BI dashboard translates these findings into an interactive reporting solution that supports performance monitoring and data-driven business decisions.