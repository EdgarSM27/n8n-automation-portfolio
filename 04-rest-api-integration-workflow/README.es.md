# 04 - Workflow de Integración con API REST

## Objetivo

Construir un workflow en n8n que demuestre integración con APIs REST utilizando solicitudes GET, POST y PUT, payloads JSON, headers, autenticación basada en token y validación de respuestas.

## Problema de negocio

Muchos procesos de automatización requieren conectar sistemas externos mediante APIs REST. Estas integraciones suelen necesitar solicitudes autenticadas, payloads JSON estructurados, validación de respuestas y documentación clara para mantenimiento.

## Solución

Este workflow simula una integración con API REST utilizando una API pública de prueba. Realiza una solicitud GET para consultar datos, una solicitud POST para crear un recurso, una solicitud PUT para actualizar un recurso existente y después valida las respuestas recibidas.

## Herramientas utilizadas

- n8n
- Nodos HTTP Request
- Nodo JavaScript Code
- Métodos REST API
- Solicitud GET
- Solicitud POST
- Solicitud PUT
- Payloads JSON
- Header Bearer token
- Validación de respuestas

## Lógica del workflow

```text
Manual Trigger
↓
Preparar Datos de Prueba
↓
GET - Consultar Recurso
↓
POST - Crear Recurso
↓
PUT - Actualizar Recurso
↓
Validar Respuestas
↓
Devolver Resumen Final
```

## Métodos API demostrados

| Método | Propósito | Endpoint |
|---|---|---|
| GET | Consultar un recurso existente | /posts/1 |
| POST | Crear un nuevo recurso | /posts |
| PUT | Actualizar un recurso existente | /posts/1 |

## Ejemplo de autenticación

El workflow incluye un ejemplo de header Bearer token:

```text
Authorization: Bearer DEMO_API_TOKEN
```

Este token es solo un placeholder usado para demostrar cómo se estructuran las solicitudes autenticadas.

## Ejemplo de payload POST

```json
{
  "title": "New automation record",
  "body": "This record was created from an n8n REST API workflow.",
  "userId": 1
}
```

## Ejemplo de payload PUT

```json
{
  "id": 1,
  "title": "Updated automation record",
  "body": "This record was updated from an n8n REST API workflow using PUT.",
  "userId": 1
}
```

## Ejemplo de respuesta JSON final

```json
{
  "success": true,
  "message": "REST API integration workflow completed successfully.",
  "request_id": "REQ-1234567890",
  "api_base_url": "https://jsonplaceholder.typicode.com",
  "methods_used": ["GET", "POST", "PUT"],
  "authentication_type": "Bearer token header",
  "content_type": "application/json",
  "get_request": "completed",
  "post_request": "completed",
  "put_request": "completed"
}
```

## Capturas

### Workflow completo en n8n

![Workflow completo en n8n](screenshots/01-n8n-workflow.png)

### Salida de solicitud GET

![Salida GET](screenshots/02-get-request-output.png)

### Salida de solicitud POST

![Salida POST](screenshots/03-post-request-output.png)

### Salida de solicitud PUT

![Salida PUT](screenshots/04-put-request-output.png)

### Salida del resumen final

![Salida del resumen final](screenshots/05-final-summary-output.png)

## Valor de negocio

- Demuestra habilidades de integración con APIs REST.
- Muestra uso de métodos GET, POST y PUT.
- Utiliza payloads JSON estructurados.
- Demuestra autenticación mediante Bearer token.
- Valida respuestas de API.
- Proporciona una estructura reutilizable para conectar sistemas externos.
- Ayuda a documentar el comportamiento de una API para mantenimiento.

## Nota de seguridad

Este workflow utiliza un token de demostración.

Antes de publicar cualquier workflow, reemplaza credenciales reales por placeholders como:

```text
Bearer DEMO_API_TOKEN
API_TOKEN_HERE
```

Nunca publiques API keys, access tokens ni credenciales privadas en un repositorio público.
