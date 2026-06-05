[English](./README.md) | [Español](./README.es.md)

# 02 - Client File Automation with Google Drive

## Objective

Build an n8n automation that receives client information through a webhook, validates the input data, creates a structured client file in Google Drive, registers the client in Airtable and returns the generated folder URL.

## Business Problem

Manual client file creation can cause inconsistent folder names, missing subfolders, duplicated administrative work and difficulty tracking client documentation. This workflow standardizes the creation of client files and improves document organization.

## Solution

The workflow receives client data using a POST webhook. It normalizes and validates the input, creates a main Google Drive folder for the client, generates predefined subfolders and stores the client record in Airtable with the Google Drive folder URL.

## Tools Used

- n8n
- Google Drive
- Airtable
- Airtable REST API
- Webhook
- HTTP Request
- JavaScript Code node
- JSON
- Token-based authentication
- Google OAuth2 credentials

## Workflow Logic

```text
Webhook - Receive Client
↓
Normalize Data
↓
Validate Data
↓
Is Data Valid?
├── False → Return Validation Error
└── True  → Create Main Folder in Google Drive
              ↓
           Create Subfolder 01 - Identificacion
              ↓
           Create Subfolder 02 - Contratos
              ↓
           Create Subfolder 03 - Comprobantes
              ↓
           Create Subfolder 04 - Seguimiento
              ↓
           Create Subfolder 05 - Reportes
              ↓
           Register Client in Airtable
              ↓
           Return Success Response
```

## Input Example

```json
{
  "nombre": "Carlos Ramirez",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "empresa": "Empresa Demo",
  "fuente": "Formulario web"
}
```

## Successful Response

```json
{
  "success": true,
  "message": "Expediente creado correctamente.",
  "cliente_id": "CLIENT-1780614429782",
  "nombre": "Carlos Ramirez",
  "expediente_url": "https://drive.google.com/drive/folders/DRIVE_FOLDER_ID",
  "carpeta_drive_id": "DRIVE_FOLDER_ID",
  "subcarpetas": [
    "01 - Identificacion",
    "02 - Contratos",
    "03 - Comprobantes",
    "04 - Seguimiento",
    "05 - Reportes"
  ]
}
```

## Validation Error Response

```json
{
  "success": false,
  "message": "El cliente tiene datos incompletos o inválidos.",
  "errores": [
    "Nombre inválido o vacío",
    "Email inválido o vacío",
    "Teléfono inválido o vacío"
  ]
}
```

## Generated Google Drive Structure

```text
n8n Client Files Portfolio/
└── EXP-CLIENT-1780614429782 - Carlos Ramirez/
    ├── 01 - Identificacion/
    ├── 02 - Contratos/
    ├── 03 - Comprobantes/
    ├── 04 - Seguimiento/
    └── 05 - Reportes/
```

## Screenshots

### Successful response

![Successful response](screenshots/01-success-response.png)

### Validation error response

![Validation error response](screenshots/02-validation-error-response.png)

### Google Drive main folder

![Google Drive main folder](screenshots/03-google-drive-main-folder.png)

### Google Drive subfolders

![Google Drive subfolders](screenshots/04-google-drive-subfolders.png)

### Complete n8n workflow

![Complete n8n workflow](screenshots/05-n8n-workflow.png)

## Business Value

- Reduces manual folder creation.
- Standardizes client file structure.
- Improves document organization.
- Creates a traceable client record in Airtable.
- Reduces administrative errors.
- Provides a structured API response with the generated Drive URL.
- Makes the process easier to audit and maintain.

## Security Note

The exported workflow must not include real API tokens, Google credentials or private identifiers.

Before publishing the workflow, replace credentials with placeholders such as:

```text
Bearer AIRTABLE_TOKEN_HERE
PARENT_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Never commit real credentials to a public repository.
