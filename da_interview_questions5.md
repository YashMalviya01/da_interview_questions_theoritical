# Data Analyst Interview Preparation — 15 Theory Questions + Solutions

> **Source:** Remaining non-SQL interview-question bank  
> **Rules:** Distinct from the previous theory batch; SQL and Python excluded.

---

# Data Analyst Fundamentals

## 1. What is the difference between Data Validation and Data Cleaning?

### Answer

**Data cleaning** focuses on identifying and correcting problems in the data, such as:

- Missing values
- Duplicate records
- Incorrect data types
- Invalid values
- Inconsistent formats

**Data validation** focuses on checking whether the data meets predefined rules, constraints, or expected conditions.

For example:

```text
Data Cleaning
→ Fix "New Yrok" to "New York"

Data Validation
→ Check that every OrderID is unique
→ Check that Revenue is not negative
```

### Interview answer

> Data cleaning is the process of correcting or transforming poor-quality data, while data validation checks whether the data satisfies predefined quality rules and constraints. I would typically validate the cleaned dataset before using it for analysis.

---

## 2. How would you handle missing data in a dataset?

I would not automatically delete or replace missing values. First, I would understand:

1. How much data is missing.
2. Which columns contain missing values.
3. Why the values are missing.
4. Whether the missingness is systematic.
5. How important the affected field is to the analysis.

Possible approaches include:

- Removing rows when the number of missing records is small and appropriate.
- Replacing numerical values with mean or median where justified.
- Using the mode for suitable categorical variables.
- Forward/backward filling for appropriate time-series data.
- Using a business-specific rule.
- Leaving values missing when `NULL` itself has meaning.

### Interview answer

> I first quantify and understand the missingness rather than automatically deleting or imputing it. Then I choose the appropriate treatment based on the data type, amount of missingness, reason for missingness, and business context.

---

## 3. How would you identify outliers in data?

I would combine statistical methods with business knowledge.

Common approaches include:

### IQR Method

Calculate:

```text
IQR = Q3 - Q1
```

Then define:

```text
Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Values outside these bounds can be treated as potential outliers.

### Z-Score

A common approach is:

```text
Z = (X - Mean) / Standard Deviation
```

Values with large absolute Z-scores may be potential outliers.

I would also use:

- Box plots
- Histograms
- Scatter plots
- Domain/business rules

### Interview answer

> I would identify outliers using methods such as the IQR method or Z-scores and then investigate them using visualizations and business context. I would not automatically remove an outlier because it could represent either an error or a genuine business event.

---

# Tableau

## 4. What is a Dual-Axis Chart in Tableau?

A Dual-Axis Chart allows two measures to be displayed using two different axes in the same visualization.

For example:

```text
Sales  → Left axis
Profit → Right axis
```

This can be useful when two measures have different scales.

A common example is comparing:

```text
Revenue
vs.
Profit Margin
```

### Interview answer

> A dual-axis chart allows two measures to be displayed in the same view using separate axes. I would use it when comparing related measures that have different scales, while making sure the visualization remains easy to interpret.

---

## 5. How do you create Calculated Fields in Tableau?

A calculated field allows you to create a new field using a formula based on existing data.

For example:

```text
Profit Ratio =
SUM([Profit]) / SUM([Sales])
```

Typical process:

1. Open the Tableau data pane.
2. Select **Create Calculated Field**.
3. Enter the calculation.
4. Validate the formula.
5. Save it.
6. Use the calculated field in the visualization.

### Interview answer

> I create a calculated field when the required business metric does not already exist in the source data. I define the appropriate formula, validate it, and then use the calculated field in the visualization or dashboard.

---

## 6. What are Level of Detail (LOD) expressions in Tableau?

LOD expressions allow calculations to be performed at a specified level of detail, independently of the level of detail currently displayed in the visualization.

Common types include:

- `FIXED`
- `INCLUDE`
- `EXCLUDE`

Example:

```text
{ FIXED [Customer ID] :
  SUM([Sales])
}
```

This calculates sales at the customer level regardless of the other dimensions in the view.

### Interview answer

> LOD expressions allow me to control the level at which Tableau performs a calculation. They are useful when the required calculation level differs from the level of detail currently shown in the visualization.

---

# Excel

## 7. What is Conditional Formatting in Excel?

Conditional Formatting automatically changes the appearance of cells based on specified conditions.

For example:

```text
Sales > 100000 → Highlight
Profit < 0     → Highlight
```

It can be used to identify:

- High or low values
- Duplicates
- Trends
- Threshold violations
- Performance indicators

### Interview answer

> Conditional Formatting helps visually identify patterns, exceptions, and important values by applying formatting based on predefined rules.

---

## 8. What is the difference between absolute, relative, and mixed cell references?

### Relative Reference

Example:

```excel
=A1
```

When copied, the reference changes.

### Absolute Reference

Example:

```excel
=$A$1
```

The row and column remain fixed when copied.

### Mixed Reference

Examples:

```excel
=$A1
=A$1
```

One part is fixed while the other can change.

| Type | Example | Behavior |
|---|---|---|
| Relative | `A1` | Row and column change |
| Absolute | `$A$1` | Row and column fixed |
| Mixed | `$A1` | Column fixed |
| Mixed | `A$1` | Row fixed |

### Interview answer

> Relative references change when a formula is copied, absolute references remain fixed, and mixed references lock either the row or the column.

---

## 9. What is Power Query in Excel, and how is it used for ETL?

Power Query is an Excel tool used to import, clean, transform, combine, and load data.

ETL means:

```text
Extract
Transform
Load
```

### Extract

Import data from sources such as:

- Excel files
- CSV files
- Databases
- Web sources

### Transform

Perform operations such as:

- Remove duplicates
- Change data types
- Handle missing values
- Split columns
- Merge datasets
- Filter rows
- Reshape data

### Load

Load the transformed data into Excel for analysis.

### Interview answer

> Power Query is useful for repeatable data preparation. I can extract data from multiple sources, transform and clean it through a series of applied steps, and then load the result into Excel for analysis or reporting.

---

# Statistics

## 10. What is the difference between Mean, Median, and Mode?

### Mean

The arithmetic average:

```text
Mean = Sum of values / Number of values
```

### Median

The middle value after sorting the data.

### Mode

The most frequently occurring value.

Example:

```text
10, 20, 20, 30, 100
```

```text
Mean   = 36
Median = 20
Mode   = 20
```

The mean can be strongly affected by extreme values, while the median is generally more robust to outliers.

### Interview answer

> Mean is the arithmetic average, median is the middle value of an ordered dataset, and mode is the most frequently occurring value. I would often prefer the median when the data is heavily skewed or contains extreme values.

---

## 11. What is Standard Deviation, and why is it important?

Standard deviation measures the amount of dispersion or variability in a dataset around its mean.

A smaller standard deviation means observations tend to be closer to the mean.

A larger standard deviation means observations are more spread out.

Example:

```text
Dataset A: 49, 50, 51
Dataset B: 10, 50, 90
```

Dataset B has much greater variability.

### Interview answer

> Standard deviation measures how spread out observations are around the mean. It is useful for understanding variability, comparing consistency, and identifying unusually distant observations when used with other statistical methods.

---

## 12. What is Regression Analysis, and when would you use it?

Regression analysis is a statistical technique used to model the relationship between a dependent variable and one or more independent variables.

Example:

```text
Sales = f(Advertising Spend, Price, Seasonality)
```

A simple linear regression can be represented as:

```text
Y = β₀ + β₁X + ε
```

Where:

- `Y` = dependent variable
- `X` = independent variable
- `β₀` = intercept
- `β₁` = coefficient
- `ε` = error term

Regression can be used for:

- Understanding relationships
- Estimating effects/associations
- Prediction
- Forecasting

### Interview answer

> Regression analysis models the relationship between variables. I would use it when I want to understand how one or more explanatory variables are associated with an outcome or when prediction is an appropriate objective.

---

# Business / Case-Based Analytics

## 13. How would you determine which products are driving revenue?

I would analyze revenue at the product level and then investigate the major contributors.

### Steps

1. Calculate total revenue by product.
2. Sort products by revenue.
3. Calculate each product's percentage contribution.
4. Analyze trends over time.
5. Segment by region or channel if necessary.
6. Compare revenue with quantity, price, and margin.

Example:

```sql
SELECT
    ProductID,
    SUM(Revenue) AS TotalRevenue
FROM Sales
GROUP BY ProductID
ORDER BY TotalRevenue DESC;
```

I would also investigate whether a product has high revenue because of:

- High volume
- High price
- Promotions
- A specific region/channel

### Interview answer

> I would calculate and rank revenue by product, then examine each product's contribution to total revenue and its trend over time. I would also compare volume, pricing, and profitability so that I don't mistake high revenue for high business value.

---

## 14. How would you analyze regional sales performance?

I would compare regions using multiple business metrics rather than revenue alone.

### Steps

1. Calculate revenue by region.
2. Compare profit and profit margin.
3. Analyze sales growth over time.
4. Compare order volume and average order value.
5. Examine customer counts and retention.
6. Identify high-performing and underperforming regions.
7. Investigate the drivers behind regional differences.

Example metrics:

```text
Revenue
Profit
Profit Margin
Orders
AOV
Customer Count
Growth Rate
Retention
```

### Interview answer

> I would compare regions using revenue, profit, margin, growth, order volume, and customer metrics. After identifying performance differences, I would drill down into products, channels, pricing, and customer behavior to understand what is driving them.

---

# HR / Behavioral

## 15. How do you ensure accuracy in your analytical work?

I use multiple validation steps rather than assuming the first result is correct.

My approach includes:

1. Understanding the business definition of each metric.
2. Checking data types and missing values.
3. Checking duplicates.
4. Validating joins and row counts.
5. Comparing calculated metrics against source data.
6. Testing SQL results with smaller samples.
7. Cross-checking important numbers using another method where appropriate.
8. Validating dashboard figures against the underlying dataset.
9. Reviewing unusual results and outliers.
10. Documenting assumptions and transformations.

### Interview answer

> I ensure accuracy by validating the data before analysis, checking joins and row counts, reconciling important metrics with source data, testing calculations, and validating dashboard numbers against the underlying analysis. I also document assumptions so the analysis is reproducible and understandable.

---

# Today's 15-Question Checklist

- [x] Data Validation vs Data Cleaning
- [x] Handling Missing Data
- [x] Identifying Outliers
- [x] Dual-Axis Charts
- [x] Calculated Fields
- [x] LOD Expressions
- [x] Conditional Formatting
- [x] Cell References
- [x] Power Query / ETL
- [x] Mean, Median, Mode
- [x] Standard Deviation
- [x] Regression Analysis
- [x] Product Revenue Analysis
- [x] Regional Sales Analysis
- [x] Ensuring Analytical Accuracy

## Progress

```text
Previous Non-SQL completed: 45
Today's theory questions:   +15
--------------------------------
Non-SQL completed:           60
Non-SQL remaining:           78
```

**SQL and Python are tracked separately.**
