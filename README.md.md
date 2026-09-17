# AI Data Analyst Automation using n8n

An AI-powered dataset analysis workflow built with **n8n**. Users can upload a CSV, Excel, or JSON dataset, optionally ask a natural-language question, and receive an AI-generated analysis through the result page and Gmail.

## Workflow

```text
Dataset Upload
      ↓
Detect Format
      ↓
Route by Format
   ├── CSV
   ├── Excel
   └── JSON
      ↓
Build Dataset
      ↓
Data Analyst Agent
      ↓
Build CSV Attachment
      ↓
Email Report
      ↓
Show Result
```

## Features

- Upload datasets in **CSV, XLSX, XLS, or JSON** format
- Automatically detect the uploaded file format
- Extract and prepare dataset rows for analysis
- Calculate basic per-column statistics
- Accept natural-language questions about the uploaded data
- Generate plain-language insights using an AI Data Analyst Agent
- Send the analysis through Gmail
- Generate a cleaned CSV attachment
- Display the final analysis on the completion page

## Technologies Used

- **n8n** — workflow automation
- **OpenAI** — AI-powered dataset analysis
- **JavaScript** — dataset processing and CSV generation
- **Gmail** — email delivery

## Example Use Case

A user can upload a banking transaction dataset and ask:

> Analyze the transaction data and provide the total number of transactions, total transaction amount, average transaction amount, fraud rate, and identify which payment channel has the highest number of transactions.

The workflow processes the uploaded file and generates a readable analysis report.

## Dataset Processing

The workflow detects the file extension and routes the dataset to the appropriate extraction node.

For large datasets, the workflow processes a maximum of **10,000 rows** for analysis. If a file contains more rows, the workflow indicates that the analysis is based on the first 10,000 rows.

The workflow also generates basic statistics for numeric columns, including:

- Total
- Average
- Minimum
- Maximum

For text columns, it records sample distinct values.

## AI Analyst

The AI Agent is instructed to:

- Answer the user's question directly when provided
- Use simple, non-technical language
- Avoid inventing numbers or trends
- Clearly state when the available data is insufficient
- Return the result as clean HTML for the report

## Project Structure

```text
AI-Data-Analyst-n8n/
│
├── workflow/
│   └── AI_Data_Analyst_Automation_GitHub.json
│
├── screenshots/
│   ├── 01-workflow.png
│   ├── 02-upload-form.png
│   └── 03-email-report.png
│
├── sample-data/
│
└── README.md
```

## Setup

1. Install or open an n8n instance.
2. Import the workflow JSON from the `workflow` folder.
3. Configure your own OpenAI/AI model credentials.
4. Configure your own Gmail credentials if email delivery is required.
5. Test the workflow with a CSV, Excel, or JSON dataset.
6. Submit a question and an email address through the form.

**Important:** Credentials are not included in this repository. Configure your own credentials after importing the workflow.

## Screenshots

### Workflow

The complete n8n workflow showing file parsing, AI analysis, CSV generation, Gmail delivery, and result display.

### Dataset Upload Form

The user-facing form used to upload a dataset and enter an optional analysis question.

### Email Report

The generated dataset analysis delivered through Gmail.

## Limitations

- Analysis is limited to the first 10,000 rows for large datasets.
- The AI can only answer questions supported by the statistics and sample data provided to it.
- Gmail and AI credentials must be configured by the user after importing the workflow.

## Author

**Aditya Salunke**

B.E. Artificial Intelligence & Data Science
