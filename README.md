# Power BI Learning Repository

This repository is prepared as a professional Power BI learning and project workspace.

The goal is not only to collect dashboard files, but to document the thinking behind them: data modeling, DAX, report design, publishing, and governance.

## Why PBIP?

Power BI Desktop can save work as a Power BI Project (`.pbip`). In this format, report and semantic model metadata are stored as folders and text-based files, which makes the project easier to review with Git.

Microsoft documents PBIP as a project structure that supports source control, text editor workflows, and separated report/model folders:

- Power BI Desktop projects: https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-overview
- Power BI report folder and PBIR format: https://learn.microsoft.com/en-us/power-bi/developer/projects/projects-report

## Repository Structure

~~~text
PowerBI-Repository/
  docs/
  projects/
  datasets/
  assets/
~~~

## Learning Path

| Order | Topic | File |
| --- | --- | --- |
| 00 | Roadmap | [docs/00-power-bi-roadmap.md](docs/00-power-bi-roadmap.md) |
| 01 | Project structure | [docs/01-power-bi-project-structure.md](docs/01-power-bi-project-structure.md) |
| 02 | Data modeling | [docs/02-data-modeling.md](docs/02-data-modeling.md) |
| 03 | DAX fundamentals | [docs/03-dax-fundamentals.md](docs/03-dax-fundamentals.md) |
| 04 | Report design | [docs/04-report-design.md](docs/04-report-design.md) |
| 05 | Publishing and governance | [docs/05-publishing-and-governance.md](docs/05-publishing-and-governance.md) |

## Recommended Project Format

When Power BI Desktop is available, save reports as Power BI Project files:

~~~text
project-name/
  project-name.pbip
  project-name.Report/
  project-name.SemanticModel/
~~~

Avoid treating `.pbix` as the only project artifact. `.pbix` is useful for sharing a packaged report, but `.pbip` is more suitable for Git-based project organization.
