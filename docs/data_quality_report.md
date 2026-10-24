# Data Quality Assessment Report

## 1. Purpose

This report documents the initial data quality assessment performed on the Sample Superstore dataset used in the Retail Business Analytics project.

The objective is to evaluate data completeness, validity, uniqueness, consistency, and suitability for business analysis before calculating performance KPIs.

The report distinguishes between:
- Checks that passed.
- Findings requiring business investigation.
- Checks that are still pending.
- Cleaning decisions supported by evidence.

## 2. Dataset Profile

| Attribute | Result |
|---|---|
| Dataset | Sample Superstore |
| Rows | 10,194 |
| Columns | 21 |
| Distinct Order IDs | 5,111 |
| Distinct Product IDs | 1,862 |
| Exact Duplicate Rows | 0 |
| Duplicate Row IDs | 0 |

## 3. Initial Quality Checks

| Check | Result | Assessment |
|---|---:|---|
| Exact duplicate rows | 0 | Passed |
| Duplicate Row IDs | 0 | Passed |
| Sales values less than or equal to zero | 0 | Passed |
| Quantity values less than or equal to zero | 0 | Passed |
| Negative Profit records | 1,901 | Requires investigation |
| Negative Discount values | 0 | Passed |
| Discount values greater than 1 | 0 | Passed |
| Ship Date earlier than Order Date | 0 | Passed |

### 3.1 Uniqueness

No exact duplicate rows were identified in the initial check. The Row ID column also contains no duplicate values.

These results reduce concern about exact row duplication and repeated row identifiers. However, they do not establish the complete business grain of the dataset.

The combination of Order ID and Product ID must be examined to determine whether multiple records exist for the same order-product combination.

### 3.2 Sales and Quantity Validity

No records were found with Sales less than or equal to zero, or Quantity less than or equal to zero.

These checks passed under the selected validation rules. They do not independently prove that every sales amount or quantity is correct.

### 3.3 Negative Profit

A total of 1,901 rows contain negative Profit values.

Negative profit can represent legitimate business losses rather than data errors.

Further analysis should determine whether losses are concentrated in specific products, categories, discount levels, customer segments, or regions.

The number of loss-making rows must not be interpreted as the number of loss-making orders or products.

### 3.4 Discount Validity

No negative Discount values or Discount values greater than 1 were identified.

The observed values are within the expected range for a discount represented as a fraction. The precise meaning of the field should still be confirmed before applying business interpretations.

### 3.5 Date Consistency

No records were found where Ship Date occurs before Order Date.

The observed order date range is:

- Earliest order date: 2023-01-03
- Latest order date: 2026-12-30

The latest date is later than the current analysis date of October 2026. This requires investigation before finalizing time-based analysis.

Potential explanations include a modified dataset, synthetic records, or an issue with the date values. No explanation should be assumed without verification.

## 4. Pending Quality Checks

The following checks remain incomplete:

- Missing values by column.
- Future-dated Order Date and Ship Date records.
- Duplicate Order ID and Product ID combinations.
- Uniqueness of customer and product attributes where relevant.
- Consistency of categorical values, including Region, Segment, Category, and Ship Mode.
- Validation of the dataset's source and date range.
- Review of extreme Sales, Profit, Discount, and Quantity values.

## 5. Cleaning Decisions

No records should be removed solely because they contain negative Profit values.

No date corrections or deletions should be made until the future-dated records have been investigated.

The absence of exact duplicate rows does not justify removing records based on Order ID alone, because one order may legitimately contain multiple product records.

All future cleaning actions must include:
1. The issue identified.
2. The validation rule used.
3. The decision taken.
4. The business reason.
5. The impact on the dataset.

## 6. Business Impact

Data quality issues can affect the reliability of business metrics and recommendations.

For example:
- Incorrect order counting can inflate reported order volume.
- Unverified future dates can distort monthly and annual comparisons.
- Missing financial values can affect profit calculations.
- Incorrectly deleting loss-making records can overstate profitability.

The dataset should therefore complete the pending checks before the analysis is treated as a reliable basis for business recommendations.

## 7. Current Assessment Status

**Status: Initial assessment completed; further validation required.**

The initial checks identified no exact duplicate rows, no duplicate Row IDs, no non-positive Sales or Quantity values, no invalid discount values under the selected rules, and no shipping dates earlier than order dates.

Negative profit records and future-dated records require further investigation. Missing-value and record-grain validation are also pending.

## 8. Next Steps

1. Calculate missing values by column.
2. Investigate records with dates later than the current analysis date.
3. Validate the Order ID and Product ID combination.
4. Review categorical consistency and extreme values.
5. Finalize and document any necessary cleaning decisions.
6. Calculate baseline business KPIs after the relevant validation is complete.
