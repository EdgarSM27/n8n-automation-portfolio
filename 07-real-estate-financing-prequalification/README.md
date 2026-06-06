[English](./README.md) | [Español](./README.es.md)

# 07 - Real Estate Financing Prequalification Workflow

## Objective

Build an n8n automation for a real estate financing company that receives financing applications, validates applicant data, calculates a basic prequalification, classifies the case with OpenAI, creates a Google Drive folder, registers the application in Airtable, creates a follow-up task, stores automation logs and returns a structured JSON response.

## Business Problem

Real estate financing companies often receive applications through forms, messages or sales channels. These applications usually require manual review, basic financial validation, document organization, follow-up assignment and internal tracking.

Without automation, this process can become slow, inconsistent and difficult to audit.

## Solution

This workflow receives a financing application through a webhook, validates required data, calculates basic prequalification metrics, uses OpenAI to summarize and suggest the next action, creates a Google Drive folder for the applicant, registers the application in Airtable, creates a follow-up task and stores an automation log.

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
- AI-powered case analysis

## Workflow Logic

```text
Webhook - Receive Financing Application
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
└── True  → Calculate Financial Prequalification
              ↓
           Classify Application with OpenAI
              ↓
           Create Google Drive Folder
              ↓
           Register Financing Application in Airtable
              ↓
           Create Follow-Up Task
              ↓
           Create Automation Log
              ↓
           Return Prequalification Result
```

## Airtable Tables Used

### Financing Applications

Stores the financing application, applicant information, calculated financial metrics and AI analysis.

Main fields:

- Application ID
- Nombre
- Email
- Teléfono
- Ciudad
- Tipo de propiedad
- Valor propiedad
- Enganche disponible
- Porcentaje enganche
- Ingreso mensual
- Plazo deseado años
- Monto a financiar
- Pago estimado mensual
- Relación pago ingreso
- Resultado precalificación
- Prioridad
- Resumen IA
- Siguiente Acción
- Estado
- Expediente URL
- Carpeta Drive ID
- Fecha de registro
- JSON Original
- AI Raw Response

### Financing Follow Up Tasks

Stores the follow-up task generated for the financing application.

Main fields:

- Task ID
- Application ID
- Nombre
- Email
- Teléfono
- Prioridad
- Resultado precalificación
- Siguiente Acción
- Estado
- Fecha de creación
- Fecha sugerida de contacto

### Financing Automation Logs

Stores workflow events for traceability and auditing.

Main fields:

- Log ID
- Workflow
- Evento
- Estado
- Mensaje
- Application ID
- Fecha
- JSON

## Input Example

```json
{
  "nombre": "Carlos Ramirez",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "ciudad": "Culiacan",
  "tipo_propiedad": "Casa",
  "valor_propiedad": 1800000,
  "enganche_disponible": 300000,
  "ingreso_mensual": 45000,
  "plazo_deseado_anios": 15,
  "mensaje": "Me interesa comprar una casa y quiero saber si puedo aplicar a financiamiento."
}
```

## Successful Response

```json
{
  "success": true,
  "message": "Solicitud de financiamiento procesada correctamente.",
  "application_id": "FIN-APP-1780765243138",
  "nombre": "Carlos Ramirez",
  "monto_financiar": 1500000,
  "porcentaje_enganche": 16.67,
  "pago_estimado_mensual": 18002.52,
  "relacion_pago_ingreso": 40.01,
  "resultado_precalificacion": "Requiere revisión",
  "prioridad": "Media",
  "resumen_ia": "El solicitante busca financiamiento para una casa en Culiacan con un valor de 1,800,000 MXN y un enganche disponible de 300,000 MXN.",
  "siguiente_accion": "Revisar en detalle la capacidad de pago del solicitante y validar documentación financiera.",
  "expediente_url": "https://drive.google.com/drive/folders/DRIVE_FOLDER_ID",
  "task_created": true,
  "log_created": true,
  "note": "Esta es una precalificación automatizada demostrativa, no una aprobación crediticia final."
}
```

## Validation Error Response

```json
{
  "success": false,
  "message": "La solicitud tiene datos incompletos o inválidos.",
  "errores": [
    "Nombre inválido o vacío",
    "Email inválido o vacío",
    "Teléfono inválido o vacío",
    "Ciudad inválida o vacía",
    "Valor de propiedad inválido",
    "Ingreso mensual inválido",
    "Plazo deseado inválido",
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

### Validation error response

![Validation error response](screenshots/03-validation-error-response.png)

### Financing application record

![Financing application record](screenshots/04-financing-application-record.png)

### Financing follow-up task record

![Financing follow-up task record](screenshots/05-financing-follow-up-task-record.png)

### Financing automation log record

![Financing automation log record](screenshots/06-financing-automation-log-record.png)

### Google Drive folder

![Google Drive folder](screenshots/07-google-drive-folder.png)

## Business Value

- Automates initial real estate financing application intake.
- Validates applicant data before creating records.
- Calculates basic prequalification metrics.
- Estimates financing amount, down payment percentage and payment-to-income ratio.
- Uses AI to summarize the case and suggest the next action.
- Creates an organized Google Drive folder for the applicant.
- Registers the application in Airtable.
- Creates a follow-up task for the sales or financing team.
- Stores logs for traceability and audit purposes.
- Demonstrates a workflow aligned with real estate financing operations.

## Disclaimer

This workflow performs a basic automated prequalification for demonstration purposes only. It does not represent a final credit approval, legal advice or financial recommendation.

## Security Note

The exported workflow must not include real API tokens, OpenAI API keys, Airtable personal access tokens, Google credentials, folder IDs or private identifiers.

Before publishing the workflow, replace credentials and private IDs with placeholders such as:

```text
Bearer AIRTABLE_TOKEN_HERE
Bearer OPENAI_API_KEY_HERE
AIRTABLE_BASE_ID_HERE
FINANCING_APPLICATIONS_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Never commit real credentials to a public repository.
