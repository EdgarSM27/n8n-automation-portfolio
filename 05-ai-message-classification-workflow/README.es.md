# 05 - Clasificación de Mensajes con IA

## Objetivo

Construir una automatización en n8n que reciba un mensaje de prospecto mediante un webhook, valide los datos de entrada, envíe el mensaje a OpenAI para clasificarlo, guarde el resultado en Airtable y devuelva una respuesta JSON estructurada.

## Problema de negocio

Los equipos de ventas y atención al cliente suelen recibir mensajes no estructurados de prospectos. Revisar manualmente cada mensaje puede retrasar el seguimiento y dificultar la priorización de oportunidades. Este workflow utiliza IA para clasificar mensajes, asignar prioridad y sugerir la siguiente acción.

## Solución

El workflow recibe un mensaje de prospecto mediante un webhook POST. Normaliza y valida la información, envía el mensaje a OpenAI usando la API, interpreta la respuesta de la IA, guarda la clasificación en Airtable y devuelve una respuesta estructurada con categoría, prioridad, sentimiento, resumen y siguiente acción sugerida.

## Herramientas utilizadas

- n8n
- OpenAI API
- Airtable
- Airtable REST API
- Webhook
- Nodos HTTP Request
- Nodo JavaScript Code
- JSON
- Prompt engineering
- Salida estructurada con IA
- Autenticación basada en token

## Lógica del workflow

```text
Webhook - Recibir Mensaje
↓
Normalizar Datos
↓
Validar Datos
↓
¿Datos válidos?
├── False → Responder Error de Validación
└── True  → Clasificar Mensaje con OpenAI
              ↓
           Parsear Respuesta IA
              ↓
           Registrar Clasificación en Airtable
              ↓
           Responder Clasificación
```

## Ejemplo de entrada

```json
{
  "nombre": "Carlos Ramirez",
  "email": "carlos.ramirez@example.com",
  "telefono": "6671112233",
  "fuente": "Formulario web",
  "mensaje": "Hola, me interesa conocer precios y disponibilidad. También quisiera agendar una llamada para revisar detalles."
}
```

## Respuesta exitosa

```json
{
  "success": true,
  "message": "Mensaje clasificado correctamente.",
  "classification_id": "CLS-1780685683783",
  "nombre": "Carlos Ramirez",
  "categoria": "Solicita precio",
  "prioridad": "Alta",
  "sentimiento": "Interesado",
  "resumen": "Carlos Ramirez solicita conocer precios, disponibilidad y desea agendar una llamada para revisar detalles.",
  "siguiente_accion": "Contactar a Carlos para proporcionar precios y agendar la llamada."
}
```

## Respuesta por error de validación

```json
{
  "success": false,
  "message": "El mensaje tiene datos incompletos o inválidos.",
  "errores": [
    "Mensaje inválido o vacío",
    "Nombre inválido o vacío"
  ]
}
```

## Campos de clasificación IA

| Campo | Descripción |
|---|---|
| categoria | Intención principal detectada en el mensaje |
| prioridad | Prioridad asignada según urgencia y valor de negocio |
| sentimiento | Sentimiento general del mensaje |
| resumen | Resumen breve de la solicitud del prospecto |
| siguiente_accion | Acción sugerida para el equipo |

## Ejemplo de clasificación

```json
{
  "categoria": "Solicita precio",
  "prioridad": "Alta",
  "sentimiento": "Interesado",
  "resumen": "Carlos Ramirez solicita conocer precios, disponibilidad y desea agendar una llamada para revisar detalles.",
  "siguiente_accion": "Contactar a Carlos para proporcionar precios y agendar la llamada."
}
```

## Capturas

### Workflow completo en n8n

![Workflow completo en n8n](screenshots/01-n8n-workflow.png)

### Salida de clasificación de OpenAI

![Salida de clasificación de OpenAI](screenshots/02-openai-classification-output.png)

### Registro de clasificación en Airtable

![Registro de clasificación en Airtable](screenshots/03-airtable-classification-record.png)

### Respuesta exitosa

![Respuesta exitosa](screenshots/04-success-response.png)

### Respuesta por error de validación

![Respuesta por error de validación](screenshots/05-validation-error-response.png)

## Valor de negocio

- Reduce la revisión manual de mensajes.
- Ayuda a priorizar prospectos automáticamente.
- Convierte mensajes no estructurados en datos estructurados.
- Proporciona una siguiente acción sugerida para seguimiento.
- Guarda resultados de clasificación en Airtable.
- Mejora la velocidad de respuesta de equipos de ventas o soporte.
- Demuestra uso práctico de IA dentro de un flujo de negocio.

## Nota de seguridad

El workflow exportado no debe incluir tokens reales, API keys de OpenAI, tokens personales de Airtable ni credenciales privadas.

Antes de publicarlo, reemplaza credenciales por placeholders como:

```text
Bearer OPENAI_API_KEY_HERE
Bearer AIRTABLE_TOKEN_HERE
```

Nunca publiques credenciales reales en un repositorio público.
