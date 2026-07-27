# Publishing And Governance

A Power BI report is not finished when the visuals are ready.

For professional usage, the report must be refreshable, understandable, secure, and maintainable.

## Publishing Checklist

- Is the data source clear?
- Is refresh behavior documented?
- Are sensitive fields protected?
- Are measure names understandable?
- Are report pages named clearly?
- Is there a README explaining the project?

## Data Refresh

Refresh problems often come from unclear data sources, broken credentials, changed column names, or local file paths.

For portfolio projects, keep datasets simple and document how they should be refreshed.

## Security

Power BI reports may contain business-sensitive information. Even a screenshot can reveal private data.

Use sample or anonymized datasets when publishing to GitHub.

## Maintenance

Every project should explain:

- What the report is for.
- Which data it uses.
- Which measures are important.
- How someone can continue the work later.
