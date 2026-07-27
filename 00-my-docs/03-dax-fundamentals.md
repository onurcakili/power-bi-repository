# DAX Fundamentals

DAX is the calculation language used in Power BI.

It is not only formula writing. DAX is mostly about understanding context: which filters are active, which rows are visible, and how the calculation should respond.

## Measures

A measure calculates a result based on the current filter context.

Example:

~~~DAX
Total Sales = SUM(FactSales[SalesAmount])
~~~

If the report is filtered by year, city, or product, the measure recalculates automatically inside that context.

## Calculated Columns

A calculated column is computed row by row and stored in the model.

Use calculated columns when a value belongs to each row. Use measures when the value should change with filters.

## Important Difference

`Total Sales` as a measure is dynamic. It changes when the user filters the report.

A calculated column is static after refresh. It does not behave like an interactive aggregation.

## Practical Habit

Before writing complex DAX, write the business sentence first:

> I want to calculate total revenue for the selected date range and selected product category.

Then translate that sentence into a measure.
