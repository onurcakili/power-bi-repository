# Private Data Platform Feeder Scripts

The private Python scripts are data feeders for the Power BI reports.

They are not copied into this repository at this stage. This file documents how they relate to the Power BI projects.

## Script Inventory

| Script | Likely Area |
| --- | --- |
| ads_funnel_daily.py | Ads funnel reporting |
| ga4_daily.py | Web analytics / GA4 |
| meta_daily.py | Meta Ads |
| pinterest_daily.py | Pinterest Ads |
| shopify_daily.py | Shopify commerce |
| stoq_daily.py | Operations or inventory source |
| str_daily.py | STR reporting |
| tcmb_daily.py | Exchange rate / financial reference data |

## Project Mapping

| Project | Source PBIX | Primary Pipeline |
| --- | --- | --- |
| [ADS Funnel Reports](../projects/01-ads-funnel-reports/) | ADS Funnel Reports.pbix | ads_funnel_daily.py |
| [Meta AD Reports](../projects/02-meta-ad-reports/) | Meta AD Reports.pbix | meta_daily.py |
| [Pinterest AD Reports](../projects/03-pinterest-ad-reports/) | Pinterest AD Reports.pbix | pinterest_daily.py |
| [Shopify Online Tracker](../projects/04-shopify-online-tracker/) | Shopify Online Tracker.pbix | shopify_daily.py |
| [STR Reports](../projects/05-str-reports/) | STR Reports.pbix | str_daily.py |

## Rule

Treat these scripts as private pipeline source. Document their purpose first; copy code only after secrets, credentials, and private identifiers are removed.
