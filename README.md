[English](./README.md) | [Español](./README.es.md)

# n8n Automation Portfolio

Portfolio focused on business process automation using n8n, Airtable, Google Drive, OpenAI API, REST APIs, JSON, webhooks, data validation and technical workflow documentation.

This repository contains practical automation projects designed to solve real business problems such as lead capture, duplicate detection, client file organization, automatic reporting, REST API integration, AI-powered message classification, advanced CRM-style lead operations, real estate financing prequalification, and document/risk review automation for financing workflows.

## Main Skills Demonstrated

* Workflow automation with n8n
* Webhook-based data capture
* REST API integration
* GET, POST and PUT requests
* JSON parsing and transformation
* Airtable integration
* Google Drive automation
* Duplicate detection
* Input validation
* Error handling
* Structured API responses
* Business process documentation
* Token-based authentication
* Google OAuth2 integration
* AI-powered message classification
* OpenAI API integration
* Prompt engineering for structured JSON output
* Advanced lead operations automation
* CRM-style workflow architecture
* Follow-up task creation
* Automation logging and audit trail
* Real estate financing prequalification
* Basic financial validation logic
* Payment-to-income ratio calculation
* Financing application workflow automation
* Document checklist automation
* Risk review workflow automation
* Word-compatible report generation
* Excel-compatible report generation
* Google Drive folder structure automation
* Airtable interface design
* Operational dashboard creation
* Case review dashboard
* Document tracking dashboard

## Projects

### [01 - Lead Capture with Duplicate Detection](./01-lead-capture-duplicate-detection)

This workflow receives lead information through a webhook, validates the required fields, searches for duplicates in Airtable, creates a new record only when the lead does not already exist and returns a structured JSON response.

Main tools used:

* n8n
* Webhook
* Airtable API
* HTTP Request nodes
* JavaScript Code node
* JSON
* REST API logic

Status: Completed

---

### [02 - Client File Automation](./02-client-file-automation)

This workflow receives client information through a webhook, validates the data, creates a structured client folder in Google Drive, registers the client in Airtable and returns the generated folder URL.

Main tools used:

* n8n
* Google Drive
* Airtable API
* Webhook
* HTTP Request nodes
* JavaScript Code node
* JSON
* Google OAuth2

Status: Completed

---

### [03 - Automatic Follow-Up Report](./03-automatic-follow-up-report)

This workflow generates an automatic follow-up report using Airtable data, calculates business metrics, creates a text file and saves it in Google Drive.

Main tools used:

* n8n
* Airtable API
* Google Drive
* HTTP Request nodes
* JavaScript Code node
* JSON
* Binary file generation
* Google OAuth2

Status: Completed

---

### [04 - REST API Integration Workflow](./04-rest-api-integration-workflow)

This workflow demonstrates REST API integration using GET, POST and PUT requests, JSON payloads, headers, Bearer token-style authentication and response validation.

Main tools used:

* n8n
* HTTP Request nodes
* JavaScript Code node
* REST API methods
* GET, POST and PUT requests
* JSON
* Bearer token header
* Response validation

Status: Completed

---

### [05 - AI Message Classification Workflow](./05-ai-message-classification-workflow)

This workflow receives a prospect message through a webhook, validates the data, sends the message to OpenAI for classification, stores the result in Airtable and returns a structured JSON response with category, priority, sentiment, summary and suggested next action.

Main tools used:

* n8n
* OpenAI API
* Airtable API
* Webhook
* HTTP Request nodes
* JavaScript Code node
* JSON
* Prompt engineering
* Structured AI output
* Token-based authentication

Status: Completed

---

### [06 - Advanced Lead Operations Workflow](./06-advanced-lead-operations-workflow)

This advanced workflow receives a sales lead through a webhook, validates the data, detects duplicates in Airtable, classifies the message with OpenAI, creates a Google Drive folder, registers the lead, creates a follow-up task, stores automation logs and returns a structured JSON response.

Main tools used:

* n8n
* OpenAI API
* Airtable API
* Google Drive
* Webhook
* HTTP Request nodes
* JavaScript Code node
* JSON
* Google OAuth2
* Duplicate detection
* Follow-up task creation
* Automation logs

Status: Completed

---

### [07 - Real Estate Financing Prequalification Workflow](./07-real-estate-financing-prequalification)

This workflow receives a real estate financing application through a webhook, validates applicant data, calculates a basic prequalification, analyzes the case with OpenAI, creates a Google Drive folder, registers the application in Airtable, creates a follow-up task, stores automation logs and returns a structured JSON response.

Main tools used:

* n8n
* OpenAI API
* Airtable API
* Google Drive
* Webhook
* HTTP Request nodes
* JavaScript Code node
* JSON
* Google OAuth2
* Financial prequalification logic
* Payment-to-income ratio calculation
* Follow-up task creation
* Automation logs

Status: Completed

---

### [08 - Real Estate Financing Document & Risk Review Workflow](./08-real-estate-financing-document-risk-review)

This advanced workflow receives a real estate financing review case through a webhook, validates applicant data, creates a Google Drive folder structure, evaluates a document checklist, calculates financial risk metrics, analyzes the case with OpenAI, creates review tasks, generates Word-compatible and Excel-compatible reports, stores automation logs and returns a structured JSON response.

This project also includes an Airtable dashboard/interface for reviewing financing cases, document status, follow-up tasks, generated reports and automation logs.

Main tools used:

* n8n
* OpenAI API
* Airtable API
* Airtable Interface
* Google Drive
* Webhook
* HTTP Request nodes
* JavaScript Code node
* JSON
* Google OAuth2
* Document checklist automation
* Financial risk review logic
* AI-powered risk analysis
* Word-compatible report generation
* Excel-compatible report generation
* Airtable dashboard design
* Follow-up task creation
* Automation logs

Dashboard pages included:

* General Summary
* Cases by Status
* Case Detail
* Documents
* Pending Documents
* Follow-Up Tasks
* High Risk Cases
* Logs
* Reports

Status: Completed

## Repository Structure

```text
n8n-automation-portfolio/
│
├── README.md
├── README.es.md
│
├── 01-lead-capture-duplicate-detection/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-output-new-lead.json
│   ├── sample-output-duplicated.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 02-client-file-automation/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 03-automatic-follow-up-report/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-output-report-summary.json
│   ├── sample-report.txt
│   └── screenshots/
│
├── 04-rest-api-integration-workflow/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-output-summary.json
│   └── screenshots/
│
├── 05-ai-message-classification-workflow/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 06-advanced-lead-operations-workflow/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-duplicated.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-success-response.png
│       ├── 03-duplicate-response.png
│       ├── 04-validation-error-response.png
│       ├── 05-advanced-leads-record.png
│       ├── 06-follow-up-task-record.png
│       ├── 07-automation-log-record.png
│       └── 08-google-drive-folder.png
│
├── 07-real-estate-financing-prequalification/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-success-response.png
│       ├── 03-validation-error-response.png
│       ├── 04-financing-application-record.png
│       ├── 05-financing-follow-up-task-record.png
│       ├── 06-financing-automation-log-record.png
│       └── 07-google-drive-folder.png
│
├── 08-real-estate-financing-document-risk-review/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-success-response.png
│       ├── 03-validation-error-response.png
│       ├── 04-financing-case-review-record.png
│       ├── 05-document-checklist-records.png
│       ├── 06-risk-review-task-record.png
│       ├── 07-risk-automation-log-record.png
│       ├── 08-google-drive-folder-structure.png
│       ├── 09-generated-word-reports.png
│       ├── 10-generated-excel-reports.png
│       ├── 11-airtable-dashboard-summary.png
│       ├── 12-airtable-cases-by-status.png
│       ├── 13-airtable-case-detail.png
│       ├── 14-airtable-document-checklist.png
│       ├── 15-airtable-follow-up-tasks.png
│       ├── 16-airtable-reports-view.png
│       └── 17-airtable-automation-logs.png
│
└── docs/
    ├── security.md
    ├── error-handling.md
    └── api-integrations.md
```

## Security Note

All exported workflows included in this repository must be cleaned before publishing. API keys, Airtable personal access tokens, OpenAI API keys, Google credentials, folder IDs and private identifiers must be replaced with placeholder values.

Example placeholders:

```text
Bearer AIRTABLE_TOKEN_HERE
Bearer OPENAI_API_KEY_HERE
AIRTABLE_BASE_ID_HERE
PARENT_FOLDER_ID_HERE
REPORTS_FOLDER_ID_HERE
ADVANCED_LEADS_FOLDER_ID_HERE
FINANCING_APPLICATIONS_FOLDER_ID_HERE
RISK_REVIEW_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Never commit real credentials to a public repository.

## Purpose

The purpose of this portfolio is to demonstrate practical automation skills using n8n and related tools. Each project includes the exported workflow, sample inputs, sample outputs, screenshots and documentation explaining the business problem, the solution and the technical implementation.

This portfolio is oriented toward demonstrating practical experience in process automation, system integration, technical documentation and measurable workflow design for areas such as sales, administration, commercial follow-up, operations and real estate financing.

---

# README.es.md principal

[English](./README.md) | [Español](./README.es.md)

# Portafolio de Automatización con n8n

Portafolio enfocado en automatización de procesos de negocio utilizando n8n, Airtable, Google Drive, OpenAI API, APIs REST, JSON, webhooks, validación de datos y documentación técnica de workflows.

Este repositorio contiene proyectos prácticos de automatización diseñados para resolver problemas reales de negocio, como captación de leads, detección de duplicados, seguimiento de clientes, organización de expedientes, reportes automáticos, integración con APIs, clasificación de mensajes con IA, operaciones avanzadas tipo CRM, precalificación para financiamiento inmobiliario y revisión documental/riesgo para procesos de financiamiento.

## Habilidades demostradas

* Automatización de flujos con n8n
* Captura de datos mediante webhooks
* Integración con APIs REST
* Solicitudes GET, POST y PUT
* Manejo y transformación de JSON
* Integración con Airtable
* Automatización con Google Drive
* Detección de duplicados
* Validación de datos de entrada
* Manejo de errores
* Respuestas API estructuradas
* Documentación de procesos de negocio
* Autenticación basada en token
* Integración con Google OAuth2
* Clasificación de mensajes con IA
* Integración con OpenAI API
* Prompt engineering para salidas JSON estructuradas
* Automatización avanzada de operaciones de leads
* Arquitectura de workflows tipo CRM
* Creación de tareas de seguimiento
* Registro de logs y trazabilidad de automatizaciones
* Precalificación para financiamiento inmobiliario
* Lógica básica de validación financiera
* Cálculo de relación pago-ingreso
* Automatización de solicitudes de financiamiento
* Automatización de checklist documental
* Automatización de revisión de riesgo
* Generación de reportes compatibles con Word
* Generación de reportes compatibles con Excel
* Automatización de estructura de carpetas en Google Drive
* Diseño de interfaces en Airtable
* Creación de paneles operativos
* Panel de revisión de casos
* Panel de seguimiento documental

## Proyectos

### [01 - Captación de Leads con Detección de Duplicados](./01-lead-capture-duplicate-detection)

Este workflow recibe información de leads mediante un webhook, valida los campos requeridos, busca duplicados en Airtable, crea un nuevo registro solo cuando el lead no existe y devuelve una respuesta JSON estructurada.

Herramientas principales:

* n8n
* Webhook
* Airtable API
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Lógica REST API

Estado: Completado

---

### [02 - Automatización de Expedientes de Clientes con Google Drive](./02-client-file-automation)

Este workflow recibe información de clientes mediante un webhook, valida los datos, crea un expediente estructurado en Google Drive, registra el cliente en Airtable y devuelve la URL de la carpeta generada.

Herramientas principales:

* n8n
* Google Drive
* Airtable API
* Webhook
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Google OAuth2

Estado: Completado

---

### [03 - Reporte Automático de Seguimiento](./03-automatic-follow-up-report)

Este workflow genera un reporte automático de seguimiento utilizando datos de Airtable, calcula métricas de negocio, crea un archivo de texto y lo guarda en Google Drive.

Herramientas principales:

* n8n
* Airtable API
* Google Drive
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Generación de archivo binario
* Google OAuth2

Estado: Completado

---

### [04 - Workflow de Integración con API REST](./04-rest-api-integration-workflow)

Este workflow demuestra integración con APIs REST utilizando solicitudes GET, POST y PUT, payloads JSON, headers, autenticación tipo Bearer token y validación de respuestas.

Herramientas principales:

* n8n
* Nodos HTTP Request
* Nodo JavaScript Code
* Métodos REST API
* Solicitudes GET, POST y PUT
* JSON
* Header Bearer token
* Validación de respuestas

Estado: Completado

---

### [05 - Clasificación de Mensajes con IA](./05-ai-message-classification-workflow)

Este workflow recibe un mensaje de prospecto mediante un webhook, valida los datos, envía el mensaje a OpenAI para clasificarlo, guarda el resultado en Airtable y devuelve una respuesta JSON estructurada con categoría, prioridad, sentimiento, resumen y siguiente acción sugerida.

Herramientas principales:

* n8n
* OpenAI API
* Airtable API
* Webhook
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Prompt engineering
* Salida estructurada con IA
* Autenticación basada en token

Estado: Completado

---

### [06 - Workflow Avanzado de Operaciones de Leads](./06-advanced-lead-operations-workflow)

Este workflow avanzado recibe un lead de ventas mediante un webhook, valida los datos, detecta duplicados en Airtable, clasifica el mensaje con OpenAI, crea una carpeta en Google Drive, registra el lead, crea una tarea de seguimiento, almacena logs de automatización y devuelve una respuesta JSON estructurada.

Herramientas principales:

* n8n
* OpenAI API
* Airtable API
* Google Drive
* Webhook
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Google OAuth2
* Detección de duplicados
* Creación de tareas de seguimiento
* Registro de logs de automatización

Estado: Completado

---

### [07 - Workflow de Precalificación para Financiamiento Inmobiliario](./07-real-estate-financing-prequalification)

Este workflow recibe una solicitud de financiamiento inmobiliario mediante un webhook, valida los datos del prospecto, calcula una precalificación básica, analiza el caso con OpenAI, crea un expediente en Google Drive, registra la solicitud en Airtable, crea una tarea de seguimiento, almacena logs de automatización y devuelve una respuesta JSON estructurada.

Herramientas principales:

* n8n
* OpenAI API
* Airtable API
* Google Drive
* Webhook
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Google OAuth2
* Lógica de precalificación financiera
* Cálculo de relación pago-ingreso
* Creación de tareas de seguimiento
* Registro de logs de automatización

Estado: Completado

---

### [08 - Workflow de Revisión Documental y Riesgo para Financiamiento Inmobiliario](./08-real-estate-financing-document-risk-review)

Este workflow avanzado recibe un caso de revisión de financiamiento inmobiliario mediante un webhook, valida los datos del solicitante, crea una estructura de carpetas en Google Drive, evalúa un checklist documental, calcula métricas financieras de riesgo, analiza el caso con OpenAI, crea tareas de revisión, genera reportes compatibles con Word y Excel, almacena logs de automatización y devuelve una respuesta JSON estructurada.

Este proyecto también incluye un panel/interfaz en Airtable para revisar casos de financiamiento, estado documental, tareas de seguimiento, reportes generados y logs de automatización.

Herramientas principales:

* n8n
* OpenAI API
* Airtable API
* Interfaz de Airtable
* Google Drive
* Webhook
* Nodos HTTP Request
* Nodo JavaScript Code
* JSON
* Google OAuth2
* Automatización de checklist documental
* Lógica de revisión de riesgo financiero
* Análisis de riesgo con IA
* Generación de reportes compatibles con Word
* Generación de reportes compatibles con Excel
* Diseño de panel en Airtable
* Creación de tareas de seguimiento
* Registro de logs de automatización

Páginas incluidas en el panel:

* Resumen General
* Casos por Estado
* Detalle del Caso
* Documentos
* Documentos Pendientes
* Tareas de Seguimiento
* Casos de Riesgo Alto
* Logs
* Reportes

Estado: Completado

## Estructura del repositorio

```text
n8n-automation-portfolio/
│
├── README.md
├── README.es.md
│
├── 01-lead-capture-duplicate-detection/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-output-new-lead.json
│   ├── sample-output-duplicated.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 02-client-file-automation/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 03-automatic-follow-up-report/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-output-report-summary.json
│   ├── sample-report.txt
│   └── screenshots/
│
├── 04-rest-api-integration-workflow/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-output-summary.json
│   └── screenshots/
│
├── 05-ai-message-classification-workflow/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│
├── 06-advanced-lead-operations-workflow/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-duplicated.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-success-response.png
│       ├── 03-duplicate-response.png
│       ├── 04-validation-error-response.png
│       ├── 05-advanced-leads-record.png
│       ├── 06-follow-up-task-record.png
│       ├── 07-automation-log-record.png
│       └── 08-google-drive-folder.png
│
├── 07-real-estate-financing-prequalification/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-success-response.png
│       ├── 03-validation-error-response.png
│       ├── 04-financing-application-record.png
│       ├── 05-financing-follow-up-task-record.png
│       ├── 06-financing-automation-log-record.png
│       └── 07-google-drive-folder.png
│
├── 08-real-estate-financing-document-risk-review/
│   ├── README.md
│   ├── README.es.md
│   ├── workflow.json
│   ├── sample-input.json
│   ├── sample-input-invalid.json
│   ├── sample-output-success.json
│   ├── sample-output-validation-error.json
│   └── screenshots/
│       ├── 01-n8n-workflow.png
│       ├── 02-success-response.png
│       ├── 03-validation-error-response.png
│       ├── 04-financing-case-review-record.png
│       ├── 05-document-checklist-records.png
│       ├── 06-risk-review-task-record.png
│       ├── 07-risk-automation-log-record.png
│       ├── 08-google-drive-folder-structure.png
│       ├── 09-generated-word-reports.png
│       ├── 10-generated-excel-reports.png
│       ├── 11-airtable-dashboard-summary.png
│       ├── 12-airtable-cases-by-status.png
│       ├── 13-airtable-case-detail.png
│       ├── 14-airtable-document-checklist.png
│       ├── 15-airtable-follow-up-tasks.png
│       ├── 16-airtable-reports-view.png
│       └── 17-airtable-automation-logs.png
│
└── docs/
    ├── security.md
    ├── error-handling.md
    └── api-integrations.md
```

## Nota de seguridad

Todos los workflows exportados incluidos en este repositorio deben ser limpiados antes de publicarse. Las API keys, tokens personales de Airtable, API keys de OpenAI, credenciales de Google, IDs de carpetas e identificadores privados deben reemplazarse por valores de ejemplo.

Ejemplos de placeholders:

```text
Bearer AIRTABLE_TOKEN_HERE
Bearer OPENAI_API_KEY_HERE
AIRTABLE_BASE_ID_HERE
PARENT_FOLDER_ID_HERE
REPORTS_FOLDER_ID_HERE
ADVANCED_LEADS_FOLDER_ID_HERE
FINANCING_APPLICATIONS_FOLDER_ID_HERE
RISK_REVIEW_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Nunca publiques credenciales reales en un repositorio público.

## Propósito

El propósito de este portafolio es demostrar habilidades prácticas de automatización utilizando n8n y herramientas relacionadas. Cada proyecto incluye el workflow exportado, entradas de ejemplo, salidas de ejemplo, capturas de pantalla y documentación que explica el problema de negocio, la solución y la implementación técnica.

Este portafolio está orientado a demostrar experiencia práctica en automatización de procesos, integración de sistemas, documentación técnica y diseño de flujos medibles para áreas como ventas, administración, seguimiento comercial, operaciones y financiamiento inmobiliario.
