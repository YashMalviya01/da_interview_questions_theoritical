# Part B — Interview Theory (15 Questions)

## Q101. How do you choose the appropriate visualization for a business problem?

**Solution / Interview Answer:** Start with the business question and the type of comparison required. Use line charts for trends over time, bar charts for category comparisons, scatter plots for relationships, maps for geographic patterns, and KPI cards for headline metrics. The visualization should make the intended insight easy to understand.

## Q102. How do you improve Tableau dashboard performance?

**Solution / Interview Answer:** Reduce unnecessary data, use extracts when appropriate, limit marks and worksheets, optimize calculations, avoid excessive filters, simplify data-source complexity, and use Tableau's performance tools to identify actual bottlenecks before optimizing.

## Q103. How would you design an interactive Tableau dashboard?

**Solution / Interview Answer:** First define the audience and business questions. Then select the most important KPIs and visualizations. Add meaningful filters, parameters, actions, tooltips, and drill-down interactions while keeping the layout simple. Finally validate usability and all dashboard numbers against the underlying data.

## Q104. What are the most commonly used Excel functions for data analysis?

**Solution / Interview Answer:** Common functions include `SUM`, `AVERAGE`, `COUNT`, `COUNTIF`, `COUNTIFS`, `SUMIF`, `SUMIFS`, `IF`, `IFERROR`, `XLOOKUP` or `VLOOKUP`, `INDEX-MATCH`, text functions, rounding functions, and date functions. The choice depends on the analytical requirement.

## Q105. How do you use Pivot Tables to summarize data?

**Solution / Interview Answer:** Place categorical fields such as Region or Product into Rows or Columns and numerical fields such as Sales into Values. Then aggregate using SUM, COUNT, or AVERAGE and use filters or slicers to explore the results.

## Q106. What is a Pivot Table and when would you use it?

**Solution / Interview Answer:** A Pivot Table is an Excel tool for quickly summarizing and analyzing structured data. I would use it when I need flexible aggregation, grouping, filtering, or comparison without writing complex formulas.

## Q107. What is the difference between VLOOKUP, HLOOKUP, and INDEX-MATCH?

**Solution / Interview Answer:** `VLOOKUP` searches vertically in the first column of a table, while `HLOOKUP` searches horizontally in the first row. `INDEX-MATCH` combines two functions to locate and return values flexibly and can look in directions where traditional VLOOKUP is less convenient.

## Q108. Why is INDEX-MATCH better than VLOOKUP in some situations?

**Solution / Interview Answer:** `INDEX-MATCH` can look to the left, separates lookup and return positions, and is less dependent on a fixed column index. Modern Excel also provides `XLOOKUP` as another flexible alternative.

## Q109. How do you remove duplicate values in Excel?

**Solution / Interview Answer:** Use **Data → Remove Duplicates** after selecting the relevant columns. Before deleting, I would normally keep a copy of the original data or verify which records should be considered duplicates.

## Q110. How do you handle large datasets efficiently in Excel?

**Solution / Interview Answer:** Use structured tables, Power Query, Pivot Tables, and efficient formulas. Avoid unnecessary volatile formulas and excessive formatting. For very large datasets, consider moving transformation or analysis to SQL, Power BI, or another suitable analytical system.

## Q111. How do you use the IF function with multiple conditions?

**Solution / Interview Answer:** Nested `IF` functions can handle multiple conditions, while `IFS` or logical functions can improve readability.

```excel
=IF(A2>=90,"Excellent",IF(A2>=75,"Good",IF(A2>=50,"Average","Needs Improvement")))
```

Conditions are evaluated in order.

## Q112. How do you create a dynamic Excel dashboard?

**Solution / Interview Answer:** Prepare a clean source dataset, create Pivot Tables or calculated metrics, build Pivot Charts, and connect them to Slicers or Timelines. KPI cards and charts should respond dynamically to user selections while remaining focused on business questions.

## Q113. How do you use Pivot Charts?

**Solution / Interview Answer:** Pivot Charts visualize Pivot Table results and remain connected to the Pivot structure. When the Pivot Table is filtered or refreshed, the chart can update accordingly.

## Q114. How do you use Slicers and Timelines?

**Solution / Interview Answer:** Slicers provide clickable filters for fields such as Region or Product. Timelines provide interactive date filtering. Together they let users explore dashboard results without manually changing formulas.

## Q115. How do you use Power Query for ETL?

**Solution / Interview Answer:** Power Query supports Extract, Transform, and Load workflows. I can connect to sources, import data, clean and transform it, merge or append datasets, change data types, and load the final dataset into Excel. The transformation steps can be refreshed when new source data arrives.

---

# Today's Checklist

## SQL

- [ ] Q136 — Calculate age from Date of Birth
- [ ] Q137 — Calculate percentages
- [ ] Q138 — Department with highest employee count
- [ ] Q139 — Employee count by department
- [ ] Q140 — Highest-paid employee in each department
- [ ] Q141 — Customers who never placed an order
- [ ] Q142 — Customers without orders using Orders/Customers/Products context
- [ ] Q143 — Customers with multiple transactions above $5,000
- [ ] Q144 — First five characters
- [ ] Q145 — Different ways to extract five characters
- [ ] Q146 — ACID properties
- [ ] Q147 — Transaction
- [ ] Q148 — COMMIT vs ROLLBACK
- [ ] Q149 — Savepoint
- [ ] Q150 — IN vs EXISTS

## Theory

- [ ] Q101 — Choosing visualizations
- [ ] Q102 — Tableau performance
- [ ] Q103 — Interactive Tableau dashboard
- [ ] Q104 — Common Excel functions
- [ ] Q105 — Pivot Tables
- [ ] Q106 — Pivot Table use cases
- [ ] Q107 — VLOOKUP vs HLOOKUP vs INDEX-MATCH
- [ ] Q108 — INDEX-MATCH advantages
- [ ] Q109 — Remove Excel duplicates
- [ ] Q110 — Large Excel datasets
- [ ] Q111 — IF with multiple conditions
- [ ] Q112 — Dynamic Excel dashboard
- [ ] Q113 — Pivot Charts
- [ ] Q114 — Slicers and Timelines
- [ ] Q115 — Power Query ETL

# Progress After Today's Session

| Category | Before | Today | After |
|---|---:|---:|---:|
| SQL | 135 | +15 | **150** |
| Interview Theory | 100 | +15 | **115** |
| Python | 15 | +0 | **15** |
| **Total completed** | **250** | **+30** | **280** |

> The 305-question master bank is tracked separately from the 5 Monster Queries, which remain excluded.
