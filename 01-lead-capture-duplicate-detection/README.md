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
```

## Input Example

```json
{
  "nombre": "Carlos Ramirez",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "fuente": "Formulario web",
  "mensaje": "Quiero mas informacion.",
  "responsable": "Ventas"
}
```

## Successful Response

```json
{
  "success": true,
  "duplicated": false,
  "message": "Lead recibido y registrado correctamente.",
  "lead_id": "LEAD-178061022002",
  "estado": "Nuevo"
}
```

## Duplicate Response

```json
{
  "success": true,
  "duplicated": true,
  "message": "El lead ya existe en Airtable. No se creó un nuevo registro.",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "airtable_record_id": "recXXXXXXXXXXXX",
  "estado_actual": "Nuevo"
}
```

## Validation Error Response

```json
{
  "success": false,
  "message": "El lead tiene datos incompletos o inválidos.",
  "errores": [
    "Nombre inválido o vacío",
    "Email inválido o vacío",
    "Teléfono inválido o vacío"
  ]
}
```

## Screenshots

### Complete n8n workflow

![Complete n8n workflow](screenshots/01-n8n-workflow.png)

### Airtable record created

![Airtable record created](screenshots/02-airtable-lead-created.png)

### Successful response for new lead

![Successful response](screenshots/03-success-response-new-lead.png)

### Duplicate lead response

![Duplicate response](screenshots/04-duplicate-response.png)

### Validation error response

![Validation error response](screenshots/05-validation-error-response.png)

## Business Value

- Reduces manual data entry.
- Prevents duplicated leads.
- Validates required information before storing records.
- Creates a consistent lead registration process.
- Improves follow-up reliability.
- Provides structured API responses.
- Makes the process easier to audit and maintain.

## Security Note

The exported workflow must not include real API tokens, personal access tokens or private credentials.

Before publishing the workflow, replace credentials with placeholders such as:

```text
Bearer AIRTABLE_TOKEN_HERE
```
