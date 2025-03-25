# n8n Workflows

This directory contains exported n8n workflows that can be imported into your n8n instance.

## Organization

- `samples/`: Contains example workflows to demonstrate n8n capabilities
- Add more directories as needed to organize your workflows by function or purpose

## How to Import Workflows

1. In your n8n instance, go to the Workflows page
2. Click on the "Import from File" button
3. Select the workflow JSON file you want to import
4. Review and save the imported workflow

## How to Export Workflows

1. In your n8n instance, open the workflow you want to export
2. Click on the "..." (three dots) menu in the top right
3. Select "Download"
4. Save the JSON file to the appropriate directory in this repository

## Workflow Naming Convention

Use descriptive names for your workflow files following this pattern:

`<function>-<description>.json`

Examples:

- `slack-daily-report.json`
- `github-issue-notification.json`
