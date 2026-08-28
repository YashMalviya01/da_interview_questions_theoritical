# Data Analyst Interview Preparation — 20 Theory Questions

> **Focus:** Data Analyst Fundamentals, Tableau, Excel, Statistics, Business Cases, and Project/Behavioral Questions  
> **Format:** Interview-ready answers  
> **Rule:** Questions are kept distinct from the previously completed theory batches.

---

## 1. Data Analyst Fundamentals

### Q1. What are the different types of data?

Data can be broadly classified into **qualitative** and **quantitative** data.

- **Qualitative data** describes categories or characteristics, such as product category, gender, or region.
- **Quantitative data** represents numerical values that can be measured, such as revenue, age, quantity, or salary.

Quantitative data can further be divided into:
- **Discrete data:** Countable values, such as number of orders.
- **Continuous data:** Measurable values, such as height, weight, or temperature.

**Interview answer:**  
> Data can be qualitative or quantitative. Quantitative data can be discrete or continuous depending on whether the values are countable or measurable.

---

### Q2. What is data validation, and why is it necessary?

Data validation is the process of checking whether data meets predefined rules and is suitable for analysis.

Examples include checking:
- Required fields are not missing.
- Values are within valid ranges.
- Dates are valid.
- IDs follow the expected format.
- Duplicate records are handled appropriately.

**Interview answer:**  
> Data validation ensures that the data meets predefined quality and business rules. It is important because invalid data can produce incorrect analysis and misleading business decisions.

---

### Q3. How would you handle missing data in a dataset?

I would first understand **why the data is missing** and how much is missing.

My approach would be:

1. Identify missing values.
2. Measure the percentage of missing data.
3. Determine whether the missingness has a meaningful pattern.
4. Decide whether to remove, replace, or retain the missing values.
5. Validate the effect of the chosen approach.

For numerical variables, appropriate imputation might include the median or mean depending on the situation. For categorical variables, a mode or an explicit `"Unknown"` category may be appropriate.

**Interview answer:**  
> I would not automatically delete missing values. I would first understand their extent and pattern and then choose an appropriate treatment based on the business context and the variable.

---

### Q4. How would you identify outliers in data?

I would use both statistical methods and business context.

Common approaches include:

- **IQR method**
- **Z-score**
- Box plots
- Distribution analysis
- Domain/business rules

For the IQR method:

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR
Upper Bound = Q3 + 1.5 × IQR
```

Values outside these boundaries can be potential outliers.

**Interview answer:**  
> I would identify potential outliers using methods such as IQR or Z-scores, then investigate whether they are genuine observations or data-quality issues before deciding how to handle them.

---

# 2. Tableau

### Q5. How do you perform Data Blending in Tableau?

Data blending combines data from different data sources using a common linking field.

One data source acts as the **primary data source**, while another acts as the **secondary data source**.

For example, sales data and budget data could be blended using:

```text
Region
```

This allows analysis combining actual sales with budget information.

**Interview answer:**  
> Data blending allows me to combine data from different sources using a common linking field. It is useful when the sources cannot be directly joined into one physical data table.

---

### Q6. What is the difference between Filters and Parameters?

**Filters** restrict the data displayed in a visualization.

**Parameters** are user-controlled values that can dynamically influence calculations, filters, or visualizations.

Example:

```text
Filter:
Show only Region = "West"

Parameter:
Allow the user to select:
Sales
Profit
Quantity
```

**Interview answer:**  
> A filter limits the data being displayed, while a parameter is a dynamic input that can control calculations, filters, or other aspects of a Tableau visualization.

---

### Q7. What is a Dual-Axis Chart?

A Dual-Axis Chart displays **two measures using two axes** in the same visualization.

For example:

```text
Sales + Profit
```

could be displayed together to compare their trends.

In Tableau, you can create one by placing two measures on the view and selecting **Dual Axis**.

**Interview answer:**  
> A dual-axis chart allows two measures with potentially different scales to be displayed together, making it useful for comparing related metrics and trends.

---

### Q8. What are Level of Detail (LOD) expressions?

LOD expressions allow you to control the level at which Tableau performs a calculation, independently of the visualization's dimensions.

Common types include:

- `FIXED`
- `INCLUDE`
- `EXCLUDE`

Example:

```text
{ FIXED CustomerID : SUM(Sales) }
```

This calculates total sales at the customer level regardless of other dimensions in the view.

**Interview answer:**  
> LOD expressions give me control over the granularity of a calculation. They are useful when the calculation needs to be performed at a level different from the current visualization.

---

# 3. Excel

### Q9. What is Conditional Formatting?

Conditional Formatting automatically changes the appearance of cells based on specified conditions.

Examples:

- Highlight sales below a target.
- Highlight duplicate values.
- Use color scales to show performance.
- Identify top-performing values.

Example:

```text
Sales < 50,000 → Highlight
Sales >= 50,000 → Normal
```

**Interview answer:**  
> Conditional Formatting helps visually identify patterns, exceptions, and important values by applying formatting based on predefined conditions.

---

### Q10. What is the difference between absolute, relative, and mixed cell references?

**Relative reference:**

```excel
A1
```

Changes when a formula is copied.

**Absolute reference:**

```excel
$A$1
```

The row and column remain fixed.

**Mixed reference:**

```excel
$A1
A$1
```

One part remains fixed while the other can change.

**Interview answer:**  
> Relative references change when copied, absolute references remain completely fixed, and mixed references fix either the row or the column.

---

### Q11. How do you use Data Validation in Excel?

Data Validation controls what users can enter into cells.

For example, I can create a dropdown:

```text
Region:
North
South
East
West
```

It can also restrict values to:
- Whole numbers
- Decimal ranges
- Dates
- Text length
- Custom rules

**Interview answer:**  
> Data Validation helps maintain data quality by restricting entries to predefined values or rules. A common example is creating dropdown lists for categorical fields.

---

### Q12. What is Power Query in Excel?

Power Query is Excel's data connection and transformation tool.

It can be used to:

- Import data from different sources.
- Clean data.
- Remove duplicates.
- Change data types.
- Merge datasets.
- Append datasets.
- Reshape data.
- Automate repeatable transformation steps.

**Interview answer:**  
> Power Query is an ETL and data-transformation tool in Excel. I can use it to connect to data sources, clean and transform data, and create a repeatable data-preparation workflow.

---

# 4. Statistics

### Q13. What is a p-value?

A p-value measures how compatible the observed data is with the null hypothesis under the assumptions of the statistical test.

A commonly used threshold is:

```text
p-value < 0.05
```

which may lead us to reject the null hypothesis, depending on the test and significance level.

**Interview answer:**  
> A p-value helps determine whether the observed evidence is statistically significant under the null hypothesis. A small p-value provides stronger evidence against the null hypothesis.

---

### Q14. What is Hypothesis Testing?

Hypothesis testing is a statistical method used to evaluate a claim about a population using sample data.

Typical steps are:

1. Define the **null hypothesis (H₀)**.
2. Define the **alternative hypothesis (H₁)**.
3. Select a significance level.
4. Collect and analyze sample data.
5. Calculate an appropriate test statistic and p-value.
6. Make a statistical decision.
7. Interpret the result in business context.

**Interview answer:**  
> Hypothesis testing allows us to use sample data to evaluate whether there is sufficient statistical evidence to reject a null hypothesis.

---

### Q15. What are Type I and Type II errors?

**Type I error:**

Rejecting the null hypothesis when it is actually true.

```text
False Positive
```

**Type II error:**

Failing to reject the null hypothesis when it is actually false.

```text
False Negative
```

Example:

If we test whether a new marketing campaign improves conversion:

- Type I: Conclude that it improves conversion when it actually does not.
- Type II: Fail to detect a real improvement.

**Interview answer:**  
> Type I error is a false positive, while Type II error is a false negative.

---

### Q16. What is the Central Limit Theorem?

The Central Limit Theorem states, under common conditions and with sufficiently large random samples, that the sampling distribution of the sample mean tends toward a normal distribution, even when the underlying population is not normally distributed.

This is important because it supports many statistical inference methods.

**Interview answer:**  
> The Central Limit Theorem tells us that the distribution of sample means tends to become approximately normal as sample size increases, which is fundamental to statistical inference.

---

# 5. Business / Case-Based Analytics

### Q17. How would you investigate a sudden decline in sales?

I would approach it systematically.

### Step 1 — Validate the metric

First, I would confirm that the decline is real and not caused by:

- Incorrect SQL logic
- Duplicate records
- Missing data
- Changes in data pipelines
- Dashboard calculation issues

### Step 2 — Break down the decline

I would analyze sales by:

- Date
- Region
- Product
- Customer segment
- Sales channel
- Sales representative

### Step 3 — Investigate drivers

I would compare the affected period with previous periods and look for changes in:

- Order volume
- Average order value
- Conversion rate
- Customer traffic
- Product availability
- Pricing
- Promotions

### Step 4 — Communicate findings

I would identify the main driver and quantify its contribution to the decline.

**Interview answer:**  
> I would first validate that the decline is genuine, then segment the data to locate where it is occurring, investigate the underlying drivers, and finally quantify the main causes and recommend appropriate actions.

---

### Q18. How would you determine which products are driving revenue?

I would calculate revenue by product and rank the products.

```sql
SELECT
    ProductID,
    SUM(Revenue) AS TotalRevenue
FROM Sales
GROUP BY ProductID
ORDER BY TotalRevenue DESC;
```

Then I would analyze:

- Revenue contribution
- Revenue growth
- Units sold
- Average selling price
- Profit margin
- Regional performance

A Pareto analysis can also identify products contributing the majority of revenue.

**Interview answer:**  
> I would aggregate revenue by product, rank the products, and then examine their revenue contribution, growth, and profitability to understand which products are driving the business.

---

# 6. Project / Behavioral

### Q19. How did you validate the quality of your data in a project?

I would validate data quality at multiple stages.

I would check:

- Missing values
- Duplicate records
- Invalid data types
- Unexpected values
- Referential integrity
- Date ranges
- Row counts before and after transformations
- Aggregated results against source data

For example, after a SQL join, I would compare row counts before and after the join to make sure the join did not unintentionally duplicate records.

**Interview answer:**  
> I validate data through completeness, uniqueness, consistency, validity, and reconciliation checks. I also validate important metrics against the source data before presenting results.

---

### Q20. How do you handle ambiguous requirements?

I would avoid making assumptions without clarification.

My approach would be:

1. Identify what is unclear.
2. Ask targeted questions.
3. Understand the business objective.
4. Define the required metrics and scope.
5. Confirm assumptions with the stakeholder.
6. Start the analysis once the requirements are sufficiently clear.

For example, if someone asks for "customer retention," I would clarify:

```text
What is the retention period?
How is an active customer defined?
What customer population should be included?
What date range should be analyzed?
```

**Interview answer:**  
> I handle ambiguity by clarifying the business objective, defining the metrics and assumptions, and confirming the expected output with the stakeholder before proceeding.

---

# Quick Revision Sheet

| # | Topic | Key Point |
|---|---|---|
| 1 | Types of Data | Qualitative vs Quantitative |
| 2 | Data Validation | Verify data meets quality rules |
| 3 | Missing Data | Understand pattern before treatment |
| 4 | Outliers | IQR, Z-score, business context |
| 5 | Tableau Blending | Combine different sources |
| 6 | Filters vs Parameters | Restriction vs dynamic input |
| 7 | Dual Axis | Two measures, two axes |
| 8 | LOD | Control calculation granularity |
| 9 | Conditional Formatting | Highlight values based on rules |
| 10 | Cell References | Relative, absolute, mixed |
| 11 | Data Validation | Control cell input |
| 12 | Power Query | ETL/data transformation |
| 13 | p-value | Evidence against null hypothesis |
| 14 | Hypothesis Testing | Test a population claim |
| 15 | Type I/II | False positive / false negative |
| 16 | CLT | Sample means tend toward normality |
| 17 | Sales Decline | Validate → segment → investigate → quantify |
| 18 | Revenue Drivers | Aggregate, rank, analyze contribution |
| 19 | Data Quality | Validate completeness, accuracy, consistency |
| 20 | Ambiguous Requirements | Clarify objective and assumptions |

---


