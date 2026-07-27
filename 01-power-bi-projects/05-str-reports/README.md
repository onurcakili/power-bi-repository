# STR Reports

STR reporting project. Use this project to document operational reporting, periodic performance, and source-system metrics.

## Project Status

This folder is a documentation-ready shell for the private Power BI file:

- Source PBIX: STR Reports.pbix
- Original private location: D:\Projects\Private-DataPlatform\powerbi_projects\publish\STR Reports.pbix
- PBIX exists in private source: True
- Private PBIX size: 2855558 bytes

The PBIX file is not copied automatically to avoid moving private report data into the repository by accident.

## Folder Structure

~~~text
05-str-reports/
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

Primary feeder script(s): str_daily.py

Related feeder script(s): tcmb_daily.py
