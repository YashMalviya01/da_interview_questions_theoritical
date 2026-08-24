Data Analyst Interview Preparation

Non-SQL Interview Questions + Python for Data Analytics

Today's batch: 15 Non-SQL Interview Questions + 10 Python Questions

Part A — Non-SQL Interview Questions

1. What is a Data Analyst?

A Data Analyst collects, cleans, analyzes, and interprets data to identify patterns, generate insights, and support business decisions.

Interview answer:

A Data Analyst uses data to answer business questions. The role typically involves collecting and cleaning data, performing analysis, identifying trends and patterns, creating visualizations, and communicating actionable insights to stakeholders.

2. What are the roles and responsibilities of a Data Analyst?

Typical responsibilities include:

Understanding business requirements.

Collecting relevant data.

Cleaning and validating data.

Performing exploratory and statistical analysis.

Writing SQL queries.

Working with Excel, Python, and BI tools.

Building dashboards and reports.

Identifying trends and patterns.

Communicating insights to stakeholders.

Supporting data-driven decision-making.

Interview answer:

A Data Analyst translates business questions into analytical problems, prepares and analyzes the relevant data, develops reports or dashboards, validates results, and communicates actionable insights to stakeholders.

3. What is data cleaning, and why is it important?

Data cleaning is the process of identifying and correcting problems in a dataset.

Common issues include:

Missing values

Duplicate records

Incorrect data types

Inconsistent formats

Invalid values

Outliers

Inconsistent categorical values

Interview answer:

Data cleaning ensures that the dataset is accurate, consistent, and suitable for analysis. I would inspect missing values, duplicates, data types, invalid values, and inconsistencies before performing the actual analysis.

Tableau

4. How do you perform Data Blending in Tableau?

Data blending combines data from different data sources using a common linking field.

For example:

Sales Data
CustomerID
Revenue

Customer Data
CustomerID
CustomerSegment

CustomerID can be used as the linking field.

Interview answer:

Data blending allows me to combine data from separate sources when they cannot be directly joined into a single data source. I establish a relationship using a common field and then use fields from both sources in the visualization.

5. What is the difference between Filters and Parameters in Tableau?

Filters restrict the data displayed in a visualization.

Parameters are user-controlled inputs that can dynamically influence calculations, filters, or visualizations.

Simple distinction:

Filter = restricts data.
Parameter = provides a dynamic input that can control analysis.

Interview answer:

A filter directly limits the data included in a view, while a parameter is a user-controlled value that can dynamically change calculations, filters, or other aspects of a visualization.

Excel

6. What is the difference between VLOOKUP, HLOOKUP, and INDEX-MATCH?

VLOOKUP

Searches vertically in the first column of a range.

=VLOOKUP(A2, E2:H100, 3, FALSE)

HLOOKUP

Searches horizontally across the first row.

=HLOOKUP(A2, B1:H5, 4, FALSE)

INDEX-MATCH

Combines INDEX() and MATCH() for flexible lookups.

=INDEX(C2:C100, MATCH(A2, A2:A100, 0))

Interview answer:

VLOOKUP searches vertically and HLOOKUP searches horizontally, while INDEX-MATCH provides more flexible lookups and does not require the lookup column to be positioned to the left of the return column.

7. How do you handle large datasets efficiently in Excel?

I would:

Convert the range into an Excel Table.

Avoid unnecessary formulas across entire columns.

Use Pivot Tables for aggregation.

Use Power Query for cleaning and transformation.

Remove unnecessary columns and rows.

Avoid volatile formulas where possible.

Use appropriate lookup and aggregation functions.

Use filters and structured references.

Keep calculations organized.

Move very large analytical workloads to SQL or another analytical system when Excel becomes unsuitable.

Interview answer:

For large datasets, I would minimize unnecessary formulas, use Tables and Pivot Tables, use Power Query for transformation, and push heavy processing to SQL or another analytical platform when the dataset becomes too large for efficient Excel processing.

Statistics

8. What is a p-value?

A p-value measures how compatible the observed data is with the null hypothesis.

A smaller p-value indicates stronger evidence against the null hypothesis.

For example, using a 5% significance level:

α = 0.05

p-value < 0.05
→ Reject the null hypothesis

Important: A p-value does not tell us the probability that the null hypothesis itself is true.

Interview answer:

A p-value measures how unusual the observed result would be if the null hypothesis were true. A sufficiently small p-value provides evidence against the null hypothesis, based on the chosen significance level.

9. What is Hypothesis Testing?

Hypothesis testing is a statistical method used to evaluate a claim about a population using sample data.

Typical process:

Define the null hypothesis (H₀).

Define the alternative hypothesis (H₁).

Choose a significance level.

Collect and analyze sample data.

Calculate a test statistic and p-value.

Decide whether to reject or fail to reject the null hypothesis.

Interpret the result in the business context.

Example:

H₀ → New design does not increase conversion.
H₁ → New design increases conversion.

Interview answer:

Hypothesis testing provides a structured way to determine whether sample evidence is strong enough to support a claim about a population.

10. What are Type I and Type II errors?

Type I Error

Rejecting a true null hypothesis.

False Positive

Type II Error

Failing to reject a false null hypothesis.

False Negative

Error

Meaning

Type I

False Positive

Type II

False Negative

Interview answer:

A Type I error occurs when we reject a true null hypothesis, while a Type II error occurs when we fail to reject a false null hypothesis.

Business / Case-Based Analytics

11. How would you investigate a sudden decline in sales?

I would approach it systematically.

Validate the decline — check for data pipeline, missing-record, duplicate, or reporting issues.

Identify when it started — analyze the sales trend over time.

Segment the decline — break sales down by region, product, customer segment, channel, and time period.

Investigate drivers — traffic, conversion, AOV, inventory, pricing, promotions, and retention.

Communicate findings — explain what happened, why, which segment caused it, and what action should be considered.

Interview answer:

I would first validate that the decline is genuine, then identify when it started and segment the data by product, region, channel, and customer segment. I would investigate the underlying drivers such as traffic, conversion, pricing, inventory, and retention before recommending an action.

12. How would you identify the most profitable customer segment?

First define profitability:

Profit = Revenue - Costs

Then:

Segment customers using relevant attributes.

Calculate revenue by segment.

Calculate associated costs.

Calculate profit and profit margin.

Compare segments.

Check for outliers.

Consider customer lifetime value where appropriate.

Interview answer:

I would compare segments using profit and profit margin rather than revenue alone. I would also consider customer lifetime value and acquisition or servicing costs to identify the segment that creates the greatest economic value.

Project-Based

13. How did you design your data model for your analytics project?

I would start with the business questions and identify the required facts and dimensions.

Example:

FactSales
---------
OrderID
CustomerID
ProductID
DateID
Quantity
Revenue
Cost
Profit

Possible dimensions:

DimCustomer
DimProduct
DimDate
DimGeography
DimChannel

I would define relationships, establish appropriate keys, and validate the model against the source data.

Interview answer:

I designed the data model around the business questions. I separated measurable business events into fact tables and descriptive attributes into dimension tables, established appropriate keys and relationships, and validated the resulting metrics against the source data.

14. Why did you choose a Star Schema?

A Star Schema organizes analytical data into a central fact table surrounded by dimension tables.

             DimCustomer
                  |
DimProduct — FactSales — DimDate
                  |
             DimGeography

Advantages

Simple structure

Easy analytical querying

Efficient aggregations

Clear business relationships

Works well with BI tools

Easy for analysts and stakeholders to understand

Interview answer:

I chose a Star Schema because it provides a simple and intuitive structure for analytical workloads. It separates measurable business events from descriptive dimensions, making SQL queries and BI reporting easier to build and maintain.

HR / Behavioral

15. How do you handle ambiguous requirements?

I would avoid making assumptions silently.

My approach:

Identify what is unclear.

Clarify the business objective.

Ask targeted questions.

Confirm metrics, scope, timeframe, and expected output.

Document the agreed requirements.

Create a small prototype if appropriate.

Validate the direction with the stakeholder.

Interview answer:

When requirements are ambiguous, I first clarify the business objective and identify the specific areas that are unclear. I confirm the expected metrics, scope, timeframe, and deliverable with the stakeholder before proceeding. If necessary, I create a small prototype and validate the direction early.
