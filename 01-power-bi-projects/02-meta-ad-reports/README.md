# Meta AD Reports

Meta advertising report project. Use this project to document paid social performance, spend, impressions, clicks, conversions, and campaign efficiency.

## Project Status

This folder is a documentation-ready shell for the private Power BI file:

- Source PBIX: Meta AD Reports.pbix
- Original private location: D:\Projects\Private-DataPlatform\powerbi_projects\publish\Meta AD Reports.pbix
- PBIX exists in private source: True
- Private PBIX size: 9065078 bytes

The PBIX file is not copied automatically to avoid moving private report data into the repository by accident.

## Folder Structure

~~~text
02-meta-ad-reports/
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

Primary feeder script(s): meta_daily.py

Related feeder script(s): ads_funnel_daily.py
