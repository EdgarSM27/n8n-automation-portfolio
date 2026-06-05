# n8n Automation Portfolio

Automation portfolio focused on business process automation using n8n, Airtable, REST APIs, JSON, webhooks, validation logic and workflow documentation.

This repository contains practical automation projects designed to solve real business problems such as lead capture, client follow-up, file organization, reporting and API integrations.

## Main Skills Demonstrated

- Workflow automation with n8n
- Webhook-based data capture
- REST API integration
- GET and POST requests
- JSON parsing and transformation
- Airtable integration
- Duplicate detection
- Input validation
- Error handling
- Structured API responses
- Business process documentation

## Projects

### 01 - Lead Capture with Duplicate Detection

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
│   └── screenshots/
│
└── docs/
    ├── security.md
    ├── error-handling.md
    └── api-integrations.md


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

