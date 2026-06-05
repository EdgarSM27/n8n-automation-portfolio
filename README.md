[English](./README.md) | [Español](./README.es.md)

# n8n Automation Portfolio

Automation portfolio focused on business process automation using n8n, Airtable, Google Drive, OpenAI API, REST APIs, JSON, webhooks, validation logic and workflow documentation.

This repository contains practical automation projects designed to solve real business problems such as lead capture, duplicate detection, client follow-up, file organization, automatic reporting, API integrations and AI-powered message classification.

## Main Skills Demonstrated

- Workflow automation with n8n
- Webhook-based data capture
- REST API integration
- GET, POST and PUT requests
- JSON parsing and transformation
- Airtable integration
- Google Drive automation
- Duplicate detection
- Input validation
- Error handling
- Structured API responses
- Business process documentation
- Token-based authentication
- Google OAuth2 integration
- AI-powered message classification
- OpenAI API integration
- Prompt engineering for structured JSON output

## Projects

### [01 - Lead Capture with Duplicate Detection](./01-lead-capture-duplicate-detection)

This workflow receives lead information through a webhook, validates the required fields, searches Airtable to detect duplicates, creates a new record only when the lead does not already exist and returns a structured JSON response.

Main tools used:

- n8n
- Webhook
- Airtable API
- HTTP Request nodes
- JavaScript Code node
- JSON
- REST API logic

Status: Completed

---

### [02 - Client File Automation with Google Drive](./02-client-file-automation)

This workflow receives client information through a webhook, validates the data, creates a structured client file in Google Drive, registers the client in Airtable and returns the generated folder URL.

Main tools used:

- n8n
- Google Drive
- Airtable API
- Webhook
- HTTP Request nodes
- JavaScript Code node
- JSON
- Google OAuth2

Status: Completed

---

### [03 - Automatic Follow-Up Report](./03-automatic-follow-up-report)

This workflow generates an automatic follow-up report using Airtable data, calculates business metrics, creates a text report and saves it in Google Drive.

Main tools used:

- n8n
- Airtable API
- Google Drive
- HTTP Request nodes
- JavaScript Code node
- JSON
- Binary file generation
- Google OAuth2

Status: Completed

---

### [04 - REST API Integration Workflow](./04-rest-api-integration-workflow)

This workflow demonstrates REST API integration using GET, POST and PUT requests, JSON payloads, headers, token-based authentication and response validation.

Main tools used:

- n8n
- HTTP Request nodes
- JavaScript Code node
- REST API methods
- GET, POST and PUT requests
- JSON
- Bearer token header
- Response validation

Status: Completed

---

### [05 - AI Message Classification Workflow](./05-ai-message-classification-workflow)

This workflow receives a prospect message through a webhook, validates the input data, sends the message to OpenAI for classification, stores the result in Airtable and returns a structured JSON response with category, priority, sentiment, summary and suggested next action.

Main tools used:

- n8n
- OpenAI API
- Airtable API
- Webhook
- HTTP Request nodes
- JavaScript Code node
- JSON
- Prompt engineering
- Structured AI output
- Token-based authentication

Status: Completed

## Repository Structure

```text
n8n-automation-portfolio/
│
├── README.md
│
├── 01-lead-capture-duplicate-detection/
│   ├── README.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-output-new-lead.json
│   ├── sample-output-duplicated.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 02-client-file-automation/
│   ├── README.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 03-automatic-follow-up-report/
│   ├── README.md
│   ├── workflow.json
│   ├── sample-output-report-summary.json
│   ├── sample-report.txt
│   └── screenshots/
│
├── 04-rest-api-integration-workflow/
│   ├── README.md
│   ├── workflow.json
│   ├── sample-output-summary.json
│   └── screenshots/
│
├── 05-ai-message-classification-workflow/
│   ├── README.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-openai-classification-output.png
│       ├── 03-airtable-classification-record.png
│       ├── 04-success-response.png
│       └── 05-validation-error-response.png
│
└── docs/
    ├── security.md
    ├── error-handling.md
    └── api-integrations.md
```

## Security Note

All exported workflows included in this repository must be sanitized before publishing. API keys, Airtable personal access tokens, OpenAI API keys, Google credentials, folder IDs and private identifiers must be replaced with placeholder values.

Example placeholders:

```text
Bearer AIRTABLE_TOKEN_HERE
Bearer OPENAI_API_KEY_HERE
PARENT_FOLDER_ID_HERE
REPORTS_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

## Purpose

The purpose of this portfolio is to demonstrate practical automation skills using n8n and related tools. Each project includes the exported workflow, example inputs, example outputs, screenshots and documentation explaining the business problem, solution and technical implementation.
