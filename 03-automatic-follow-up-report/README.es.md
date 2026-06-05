[English](./README.md) | [Español](./README.es.md)

# 03 - Reporte Automático de Seguimiento

## Objetivo

Construir una automatización en n8n que genere un reporte automático de seguimiento utilizando datos de Airtable, calcule métricas de negocio y guarde el reporte como archivo de texto en Google Drive.

## Problema de negocio

La creación manual de reportes consume tiempo, puede introducir errores y dificulta mantener un seguimiento constante de leads y clientes. Este workflow automatiza el proceso al recopilar datos desde Airtable, procesar métricas y guardar un reporte estructurado en Google Drive.

## Solución

El workflow se ejecuta manualmente o puede adaptarse para ejecutarse con una programación. Consulta registros de leads y clientes en Airtable, calcula métricas de resumen, genera un reporte de texto, lo sube a Google Drive y devuelve un resumen JSON estructurado.

## Herramientas utilizadas

- n8n
- Airtable
- Airtable REST API
- Google Drive
- Nodos HTTP Request
- Nodo JavaScript Code
- JSON
- Generación de archivo binario
- Credenciales Google OAuth2

## Lógica del workflow

```text
Manual Trigger
↓
Consultar Leads en Airtable
↓
Consultar Clientes en Airtable
↓
Procesar Métricas
↓
Crear Archivo de Reporte
↓
Subir Reporte a Google Drive
↓
Devolver Resumen Final
```

## Métricas generadas

- Total de leads
- Leads nuevos
- Leads contactados
- Leads en seguimiento
- Total de clientes
- Clientes con expediente creado
- Leads por estado
- Leads por prioridad
- Clientes por estado

## Ejemplo de reporte generado

```text
AUTOMATIC FOLLOW-UP REPORT

Report date: 2026-06-05

SUMMARY
- Total leads: 1
- New leads: 1
- Contacted leads: 0
- Leads in follow-up: 0
- Total clients: 3
- Clients with created file: 1

LEADS BY STATUS
- Nuevo: 1

LEADS BY PRIORITY
- Media: 1

CLIENTS BY STATUS
- Sin valor: 1
- Completo: 1
- Expediente creado: 1

BUSINESS NOTES
Reporte creado automaticamente desde n8n con informacion de Airtable
```

## Ejemplo de respuesta JSON final

```json
{
  "success": true,
  "message": "Reporte generado correctamente.",
  "report_date": "2026-06-05",
  "report_file_name": "follow-up-report-2026-06-05.txt",
  "report_file_id": "DRIVE_FILE_ID",
  "report_url": "https://drive.google.com/file/d/DRIVE_FILE_ID/view",
  "total_leads": 1,
  "total_clients": 3,
  "leads_by_status": {
    "Nuevo": 1
  },
  "leads_by_priority": {
    "Media": 1
  },
  "clients_by_status": {
    "Sin valor": 1,
    "Completo": 1,
    "Expediente creado": 1
  }
}
```

## Capturas

### Workflow completo en n8n

![Workflow completo en n8n](screenshots/01-n8n-workflow.png)

### Archivo de reporte en Google Drive

![Archivo de reporte en Google Drive](screenshots/02-google-drive-report-file.png)

### Contenido del reporte

![Contenido del reporte](screenshots/03-report-file-content.png)

### Salida del resumen final

![Salida del resumen final](screenshots/04-final-summary-output.png)

## Valor de negocio

- Reduce trabajo manual de reportes.
- Centraliza la información de seguimiento.
- Genera métricas consistentes de negocio.
- Guarda reportes automáticamente en Google Drive.
- Proporciona un resumen estructurado para revisión.
- Facilita auditoría y repetición del proceso.
- Puede adaptarse para ejecutarse diario, semanal o mensualmente.

## Nota de seguridad

El workflow exportado no debe incluir tokens reales, credenciales de Google, IDs de carpetas ni identificadores privados.

Antes de publicarlo, reemplaza credenciales e IDs privados con placeholders como:

```text
Bearer AIRTABLE_TOKEN_HERE
REPORTS_FOLDER_ID_HERE
GOOGLE_DRIVE_CREDENTIAL_PLACEHOLDER
```
