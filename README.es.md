# Portafolio de Automatización con n8n

Portafolio enfocado en automatización de procesos de negocio utilizando n8n, Airtable, Google Drive, OpenAI API, APIs REST, JSON, webhooks, validación de datos y documentación técnica de workflows.

Este repositorio contiene proyectos prácticos de automatización diseñados para resolver problemas reales de negocio, como captación de leads, detección de duplicados, seguimiento de clientes, organización de expedientes, reportes automáticos, integración de APIs y clasificación de mensajes con IA.

## Habilidades demostradas

- Automatización de flujos con n8n
- Captura de datos mediante webhooks
- Integración con APIs REST
- Solicitudes GET, POST y PUT
- Manejo y transformación de JSON
- Integración con Airtable
- Automatización con Google Drive
- Detección de duplicados
- Validación de datos de entrada
- Manejo de errores
- Respuestas API estructuradas
- Documentación de procesos de negocio
- Autenticación basada en token
- Integración con Google OAuth2
- Clasificación de mensajes con IA
- Integración con OpenAI API
- Prompt engineering para salidas JSON estructuradas

## Proyectos

### [01 - Captación de Leads con Detección de Duplicados](./01-lead-capture-duplicate-detection)

Este workflow recibe información de leads mediante un webhook, valida los campos requeridos, busca duplicados en Airtable, crea un nuevo registro solo cuando el lead no existe y devuelve una respuesta JSON estructurada.

Herramientas principales:

- n8n
- Webhook
- Airtable API
- Nodos HTTP Request
- Nodo JavaScript Code
- JSON
- Lógica REST API

Estado: Completado

---

### [02 - Automatización de Expedientes de Clientes con Google Drive](./02-client-file-automation)

Este workflow recibe información de clientes mediante un webhook, valida los datos, crea un expediente estructurado en Google Drive, registra el cliente en Airtable y devuelve la URL de la carpeta generada.

Herramientas principales:

- n8n
- Google Drive
- Airtable API
- Webhook
- Nodos HTTP Request
- Nodo JavaScript Code
- JSON
- Google OAuth2

Estado: Completado

---

### [03 - Reporte Automático de Seguimiento](./03-automatic-follow-up-report)

Este workflow genera un reporte automático de seguimiento utilizando datos de Airtable, calcula métricas de negocio, crea un archivo de texto y lo guarda en Google Drive.

Herramientas principales:

- n8n
- Airtable API
- Google Drive
- Nodos HTTP Request
- Nodo JavaScript Code
- JSON
- Generación de archivo binario
- Google OAuth2

Estado: Completado

---

### [04 - Workflow de Integración con API REST](./04-rest-api-integration-workflow)

Este workflow demuestra integración con APIs REST utilizando solicitudes GET, POST y PUT, payloads JSON, headers, autenticación tipo Bearer token y validación de respuestas.

Herramientas principales:

- n8n
- Nodos HTTP Request
- Nodo JavaScript Code
- Métodos REST API
- Solicitudes GET, POST y PUT
- JSON
- Header Bearer token
- Validación de respuestas

Estado: Completado

---

### [05 - Clasificación de Mensajes con IA](./05-ai-message-classification-workflow)

Este workflow recibe un mensaje de prospecto mediante un webhook, valida los datos, envía el mensaje a OpenAI para clasificarlo, guarda el resultado en Airtable y devuelve una respuesta JSON estructurada con categoría, prioridad, sentimiento, resumen y siguiente acción sugerida.

Herramientas principales:

- n8n
- OpenAI API
- Airtable API
- Webhook
- Nodos HTTP Request
- Nodo JavaScript Code
- JSON
- Prompt engineering
- Salida estructurada con IA
- Autenticación basada en token

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
PARENT_FOLDER_ID_HERE
REPORTS_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```

Nunca publiques credenciales reales en un repositorio público.

## Propósito

El propósito de este portafolio es demostrar habilidades prácticas de automatización utilizando n8n y herramientas relacionadas. Cada proyecto incluye el workflow exportado, entradas de ejemplo, salidas de ejemplo, capturas de pantalla y documentación que explica el problema de negocio, la solución y la implementación técnica.
