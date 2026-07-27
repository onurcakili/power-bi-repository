# Data Modeling

Data modeling is the step where raw tables become an analytical structure.

A report can look visually good but still produce wrong numbers if the model is weak. This is why modeling comes before dashboard design.

## Core Idea

A good Power BI model usually separates facts and dimensions.

- **Fact table**: Numeric business events such as sales, orders, payments, or page views.
- **Dimension table**: Descriptive context such as customer, product, date, city, or category.

## Example

For a sales report:

~~~text
FactSales
  DateKey
  ProductKey
  CustomerKey
  SalesAmount
  Quantity

DimDate
DimProduct
DimCustomer
~~~

`FactSales` answers what happened. Dimension tables explain when, where, and for whom it happened.

## Why Star Schema Matters

Star schema keeps relationships simple. Instead of connecting every table to every other table, fact tables connect to dimension tables.

This makes DAX easier, filter behavior more predictable, and reports easier to debug.

## Common Mistakes

- Building visuals directly on messy raw tables.
- Using many-to-many relationships without understanding filter flow.
- Mixing IDs, names, and calculations in the same table without a clear purpose.
- Forgetting a proper date table.
