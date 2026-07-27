# Shopify Online Tracker

Shopify online commerce tracking project. Use this project to document revenue, orders, product performance, customer behavior, and online sales movement.

## Project Status

This folder is a documentation-ready shell for the private Power BI file:

- Source PBIX: Shopify Online Tracker.pbix
- Original private location: D:\Projects\Private-DataPlatform\powerbi_projects\publish\Shopify Online Tracker.pbix
- PBIX exists in private source: True
- Private PBIX size: 39929842 bytes

The PBIX file is not copied automatically to avoid moving private report data into the repository by accident.

## Folder Structure

~~~text
04-shopify-online-tracker/
  README.md
  source/
  screenshots/
  docs/
  dax/
  diagrams/
  assets/
~~~

## Documentation Flow

1. Open the PBIX in Power BI Desktop.
2. Export or capture page screenshots into screenshots/.
3. Copy safe DAX measures into dax/measures.dax.
4. Fill docs/report-pages.md with page purpose and visual notes.
5. Fill docs/data-model.md with table and relationship details.
6. Fill docs/measure-catalog.md with measure definitions.
7. Keep private credentials, raw tokens, and sensitive business data out of this repository.

## Feeder Scripts

Primary feeder script(s): shopify_daily.py

Related feeder script(s): ga4_daily.py, tcmb_daily.py, stoq_daily.py
