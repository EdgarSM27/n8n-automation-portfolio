[English](./README.md) | [Español](./README.es.md)

# 06 - Advanced Lead Operations Workflow

## Objective

Build an advanced n8n automation that receives a sales lead, validates the input data, detects duplicates in Airtable, classifies the message with OpenAI, creates a Google Drive client folder, registers the lead, creates a follow-up task, stores automation logs and returns a structured JSON response.

## Business Problem

Sales and operations teams often manage leads across multiple tools manually. This can cause duplicated records, slow follow-up, missing documentation, inconsistent prioritization and lack of traceability. This workflow combines multiple automation steps into one end-to-end process to improve lead handling and operational visibility.

## Solution

The workflow receives lead data through a webhook. It normalizes and validates the data, checks Airtable for existing leads, classifies the message using OpenAI, creates a Google Drive folder for the lead, registers the lead in Airtable, creates a follow-up task, stores an automation log and returns a complete response.

## Tools Used

- n8n
- Airtable
- Airtable REST API
- Google Drive
- OpenAI API
- Webhook
- HTTP Request nodes
- JavaScript Code node
- JSON
- Google OAuth2
- Token-based authentication
- Prompt engineering
- AI-powered classification

## Workflow Logic

```text
Webhook - Receive Advanced Lead
↓
Normalize Data
↓
Validate Data
↓
Is Data Valid?
├── False → Create Validation Error Log
│            ↓
│         Return Validation Error
│
└── True  → Search Duplicate in Airtable
              ↓
           Does Duplicate Exist?
           ├── True → Create Duplicate Log
           │          ↓
           │       Return Duplicate Response
           │
           └── False → Classify Lead with OpenAI
                         ↓
                      Parse AI Response and Prepare Operation
                         ↓
                      Create Google Drive Folder
                         ↓
                      Register Advanced Lead in Airtable
                         ↓
                      Create Follow-Up Task
                         ↓
                      Create Success Log
                         ↓
                      Return Processed Lead Response
```

## Airtable Tables Used

### Advanced Leads

Stores the processed lead and AI classification result.

Main fields:

- Lead ID
- Nombre
- Email
- Teléfono
- Empresa
- Fuente
- Mensaje
- Categoría
- Prioridad
- Sentimiento
- Resumen
- Siguiente Acción
- Estado
- Expediente URL
- Carpeta Drive ID
- Fecha de registro
- JSON Original
- AI Raw Response

### Follow Up Tasks

Stores the follow-up task created based on the AI priority.

Main fields:

- Task ID
- Lead ID
- Nombre
- Email
- Teléfono
- Prioridad
- Tipo de seguimiento
- Siguiente Acción
- Estado
- Fecha de creación
- Fecha sugerida de contacto

### Automation Logs

Stores workflow events for traceability and auditing.

Main fields:

- Log ID
- Workflow
- Evento
- Estado
- Mensaje
- Lead ID
- Fecha
- JSON

## Input Example

```json
{
  "nombre": "Carlos Ramirez",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "empresa": "Empresa Demo",
  "fuente": "Formulario web",
  "mensaje": "Hola, me interesa conocer precios y disponibilidad. También quisiera agendar una llamada esta semana."
}
```

## Successful Response

```json
{
  "success": true,
  "message": "Lead processed successfully.",
  "lead_id": "ADV-LEAD-178069119145",
  "duplicated": false,
  "categoria": "Solicita llamada",
  "prioridad": "Alta",
  "sentimiento": "Interesado",
  "resumen": "Carlos Ramirez de Empresa Demo solicita precios, disponibilidad y agendar una llamada esta semana.",
  "siguiente_accion": "Contactar a Carlos para proporcionar información solicitada y coordinar llamada.",
  "expediente_url": "https://drive.google.com/drive/folders/DRIVE_FOLDER_ID",
  "task_created": true,
  "log_created": true
}
```

## Duplicate Response

```json
{
  "success": true,
  "duplicated": true,
  "message": "El lead ya existe en Airtable. No se creó un nuevo registro.",
  "lead_id": "ADV-LEAD-178069119145",
  "airtable_record_id": "recXXXXXXXXXXXX",
  "nombre": "Carlos Ramirez",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "log_created": true
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
    "Teléfono inválido o vacío",
    "Mensaje inválido o vacío"
  ],
  "log_created": true
}
```

## Screenshots

### Complete n8n workflow

![Complete n8n workflow](screenshots/01-n8n-workflow.png)

### Successful response

![Successful response](screenshots/02-success-response.png)

### Duplicate response

![Duplicate response](screenshots/03-duplicate-response.png)

### Validation error response

![Validation error response](screenshots/04-validation-error-response.png)

### Advanced lead record

![Advanced lead record](screenshots/05-advanced-leads-record.png)

### Follow-up task record

![Follow-up task record](screenshots/06-follow-up-task-record.png)

### Automation log record

![Automation log record](screenshots/07-automation-log-record.png)

### Google Drive folder

![Google Drive folder](screenshots/08-google-drive-folder.png)

## Business Value

- Reduces manual lead processing.
- Prevents duplicated lead records.
- Uses AI to classify intent, priority and sentiment.
- Creates structured Google Drive folders automatically.
- Registers leads in Airtable with full context.
- Creates follow-up tasks based on priority.
- Stores automation logs for auditing.
- Provides a reusable CRM-style automation structure.
- Combines validation, AI, storage, task creation and logging in one workflow.

## Security Note

The exported workflow must not include real API tokens, OpenAI API keys, Airtable personal access tokens, Google credentials, folder IDs or private identifiers.

Before publishing the workflow, replace credentials and private IDs with placeholders such as:

```text
Bearer AIRTABLE_TOKEN_HERE
Bearer OPENAI_API_KEY_HERE
ADVANCED_LEADS_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Never commit real credentials to a public repository.
