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

### Missing Values

No missing values were detected in any of the 21 columns.

**Result:** Passed for completeness checks.

**Business Impact:** The required columns are populated, so no missing-value imputation or deletion is currently required. However, populated values must still be checked for validity and consistency.

## 4. Pending Quality Checks

### Future-Dated Records

Using the fixed analysis date of October 24, 2026:

| Check | Result |
|---|---:|
| Records with future Order Dates | 999 |
| Records with future Ship Dates | 1,040 |

These records require investigation before time-based reporting is finalized.

The counts refer to transaction rows, not distinct orders. The records should not be deleted automatically. Their date range, source, and business context must be reviewed first.

### Repeated Order-Product Combinations

A duplicate check on the combination of `Order ID` and `Product ID` identified 11 repeated combinations. Each combination appears twice, representing 22 transaction rows in total.

#### Repeated Combination Summary

Further investigation showed that the repeated combinations have different Sales, Quantity, and Profit values. Each combination has one distinct Discount value within its two records.

These findings do not establish that the records are erroneous duplicates. They may represent separate transaction lines, but the original transaction-line structure and source documentation are needed to confirm their intended meaning.

**Decision:** Retain all records for now. Do not remove records based on `Order ID` and `Product ID` alone. Verify the transaction-line grain and ensure that subsequent aggregations or joins do not introduce additional duplication.

### Categorical Distribution

The initial categorical review identified:

- **Region:** West, East, Central, South.
- **Segment:** Consumer, Corporate, Home Office.
- **Category:** Office Supplies, Furniture, Technology.
- **Ship Mode:** Standard Class, Second Class, First Class, Same Day.

The counts across each of these four columns sum to 10,194, matching the dataset row count. Further source validation may be needed before treating these categories as fully verified.

### Assessment Update

The dataset has no detected missing values, exact duplicate rows, or duplicate Row IDs. However, future-dated records and repeated order-product combinations have been investigated, but their intended transaction-line structure still requires source validation.

No records have been removed or corrected based solely on these findings.



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

1. Investigate records with dates later than the current analysis date.
2. Validate the Order ID and Product ID combination.
3. Review categorical consistency and extreme values.
4. Finalize and document any necessary cleaning decisions.
5. Calculate baseline business KPIs and compare the full dataset with records dated on or before October 24, 2026.
