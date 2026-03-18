# Business Operations Team

Process, validate, approve, and report pipeline for business workflows.

## Who is this for?

Operations teams and business analysts who need to process unstructured data into structured reports with validation and quality checks.

## Agent Team

| Role | Model | Responsibility |
|------|-------|---------------|
| Data Processor | claude-haiku-4-5 | Extract structured data from unstructured inputs, flag anomalies |
| Validator | claude-haiku-4-5 | Check completeness and accuracy, conservatively flag anything uncertain |
| Report Generator | claude-haiku-4-5 | Create clear operational reports with stats, exceptions, and action items |

## Example Goal

```
Process Q1 expense reports and generate summary report
```

## Estimated Cost

~$0.05 per run

## Requirements

This template requires webhook configuration (`requiresWebhook: true`) for integration with external business systems.

## Tips for Best Results

- Provide clear input format descriptions in your goal
- The validator is intentionally conservative — it flags rather than guesses
- Reports are formatted for non-technical stakeholders
- Use for batch processing workflows where human review of exceptions is expected
