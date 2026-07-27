# Power BI Projects

This folder contains one documentation shell per Power BI report.

The PBIX files currently live in the private source repository and are not copied automatically.

## Projects

| Project | Source PBIX | Primary Pipeline |
| --- | --- | --- |
| [ADS Funnel Reports](01-ads-funnel-reports/) | ADS Funnel Reports.pbix | ads_funnel_daily.py |
| [Meta AD Reports](02-meta-ad-reports/) | Meta AD Reports.pbix | meta_daily.py |
| [Pinterest AD Reports](03-pinterest-ad-reports/) | Pinterest AD Reports.pbix | pinterest_daily.py |
| [Shopify Online Tracker](04-shopify-online-tracker/) | Shopify Online Tracker.pbix | shopify_daily.py |
| [STR Reports](05-str-reports/) | STR Reports.pbix | str_daily.py |

## Standard Project Structure

~~~text
01-project-name/
  README.md
  source/
  screenshots/
  docs/
  dax/
  diagrams/
  assets/
~~~

## How To Continue

For each project:

1. Open the PBIX in Power BI Desktop.
2. Export screenshots into screenshots/.
3. Copy safe DAX measures into dax/measures.dax.
4. Fill documentation under docs/.
5. Add diagrams under diagrams/.
