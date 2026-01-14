---
name: jira-context
description: Obtener contexto de tickets de Jira para implementar código. Usar cuando necesites ver especificaciones de un ticket, criterios de aceptación, o detalles para implementar una tarea. Invocar con /jira-context o cuando se mencione un ticket como PROJ-123.
---

# Jira Context para Desarrollo

Skill para obtener el contexto de tickets de Jira y usar sus especificaciones para guiar la implementación de código.

## Propósito

Conectar las especificaciones de tickets de Jira con el trabajo de desarrollo, permitiendo:
- Obtener descripción completa del ticket
- Ver criterios de aceptación
- Entender los requisitos técnicos
- Implementar código basado en las especificaciones

## Cómo usar

### Obtener contexto de un ticket
```
/jira-context PROJ-123
```

### Ver mis tickets asignados
```
/jira-context mis tickets
```

### Implementar basado en ticket
```
Ayúdame a implementar el ticket PROJ-123
```

## Información que se obtiene de cada ticket

- **Título**: Resumen del ticket
- **Descripción**: Detalles completos de la tarea
- **Criterios de aceptación**: Lo que debe cumplirse
- **Tipo**: Story, Bug, Task, etc.
- **Prioridad**: Critical, High, Medium, Low
- **Sprint**: Sprint actual asignado
- **Etiquetas**: Labels relacionados
- **Subtareas**: Tareas hijas si existen

## Flujo de trabajo recomendado

1. **Obtener contexto**: Consultar el ticket para entender los requisitos
2. **Analizar codebase**: Identificar archivos relevantes a modificar
3. **Planificar**: Crear un plan de implementación basado en las especificaciones
4. **Implementar**: Escribir código que cumpla los criterios de aceptación
5. **Verificar**: Confirmar que la implementación cumple con el ticket

## Configuración

Esta skill requiere el MCP server de Jira. Configurar con:

```bash
claude mcp add jira -- npx -y @anthropic/mcp-remote \
  --url https://TU-INSTANCIA.atlassian.net/jira/mcp \
  --header "Authorization: Basic BASE64(email:api_token)"
```

### Obtener API Token
1. Ir a https://id.atlassian.com/manage-profile/security/api-tokens
2. Crear nuevo token
3. Guardar el token de forma segura

## Ejemplos

"Dame el contexto del ticket MOBILE-456 para implementarlo"
"¿Cuáles son los criterios de aceptación de BACKEND-789?"
"Muéstrame mis tickets del sprint actual"
"Implementa la funcionalidad descrita en MOBILE-123"
