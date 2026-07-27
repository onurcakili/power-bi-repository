# Data Pipeline

This report is connected to private feeder scripts from:

~~~text
D:\Projects\Private-DataPlatform\python_projects\scripts
~~~

## Script Mapping

| Script | Role | Private Source Path |
| --- | --- | --- |
| ads_funnel_daily.py | Primary feeder | D:\Projects\Private-DataPlatform\python_projects\scripts\ads_funnel_daily.py |
| meta_daily.py | Related feeder | D:\Projects\Private-DataPlatform\python_projects\scripts\meta_daily.py |
| pinterest_daily.py | Related feeder | D:\Projects\Private-DataPlatform\python_projects\scripts\pinterest_daily.py |
| ga4_daily.py | Related feeder | D:\Projects\Private-DataPlatform\python_projects\scripts\ga4_daily.py |
| shopify_daily.py | Related feeder | D:\Projects\Private-DataPlatform\python_projects\scripts\shopify_daily.py |

## Pipeline Documentation Checklist

- What source system does each script pull from?
- Where does the script write the processed data?
- How often is the script expected to run?
- Which tables or files does Power BI consume?
- Are there dependencies between scripts?
- Are API keys, credentials, or tokens excluded from documentation?

## Current Decision

The scripts are not copied into this repository at this stage. They are private data feeders and should be documented carefully before any code is moved.
