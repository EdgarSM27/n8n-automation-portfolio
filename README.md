# n8n Automation Portfolio

Automation portfolio focused on business process automation using n8n, Airtable, REST APIs, JSON, webhooks, validation logic, Google Drive automation and workflow documentation.

This repository contains practical automation projects designed to solve real business problems such as lead capture, duplicate detection, client follow-up, file organization, reporting and API integrations.

## Main Skills Demonstrated

- Workflow automation with n8n
- Webhook-based data capture
- REST API integration
- GET and POST requests
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
└── docs/
    ├── security.md
    ├── error-handling.md
    └── api-integrations.md
```

## Security Note

All exported workflows included in this repository must be sanitized before publishing. API keys, Airtable personal access tokens, Google credentials, folder IDs and private identifiers must be replaced with placeholder values.

Example placeholders:

```text
Bearer AIRTABLE_TOKEN_HERE
PARENT_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Never commit real credentials to a public repository.

## Purpose

The purpose of this portfolio is to demonstrate practical automation skills using n8n and related tools. Each project includes the exported workflow, example inputs, example outputs, screenshots and documentation explaining the business problem, solution and technical implementation.
