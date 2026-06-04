# 01 - Lead Capture with Duplicate Detection

## Objective

Build an n8n workflow that receives lead information through a webhook, validates the input data, checks for duplicated records in Airtable and creates a new lead only when the contact does not already exist.

## Business Problem

Manual lead registration can cause duplicated records, missing information and delayed follow-up. This workflow helps standardize the capture process and ensures that each lead is validated before being stored.

## Solution

The workflow receives lead data using a POST webhook. It normalizes the input, validates required fields, searches Airtable by email or phone number and decides whether to create a new record or return a duplicate response.

## Tools Used

- n8n
- Airtable
- Airtable REST API
- Webhook
- HTTP Request
- JavaScript Code node
- JSON
- REST API methods
- Token-based authentication

## Workflow Logic

```text
Webhook - Receive Lead
↓
Normalize Data
↓
Validate Data
↓
Is Data Valid?
├── False → Return Validation Error
└── True  → Search Duplicate in Airtable
              ↓
           Does Duplicate Exist?
           ├── True  → Return Duplicate Response
           └── False → Create Lead in Airtable
                         ↓
                      Return Success Response
