# ADR-001: Jira para la gestión y GitHub para el código

- **Estado:** Aceptado
- **Fecha:** 2026-10-21

## Contexto

El equipo necesita una herramienta para planificar el trabajo con Scrum (épicas, historias, sprints) y otra para alojar el código con control de cambios y revisión. Además, cada cambio en el código debe poder rastrearse hasta el ticket que lo originó.

## Decisión

- **Jira** para la gestión ágil: backlog, sprints, épicas, historias y tareas.
- **GitHub** para el código, en la organización `bancolab-pe`, con la rama `main` protegida (todo cambio entra por Pull Request).
- **Integración GitHub for Atlassian** para vincular automáticamente ramas, commits y Pull Requests con sus tickets, usando la clave `BANK-XX`.

## Alternativas consideradas

- **GitHub Projects:** más simple e integrado con el código, pero con menos funciones de Scrum (estimaciones, reportes de sprint) y menos usado en el sector financiero.
- **Azure DevOps:** cubre gestión y código en una sola herramienta, pero se prefirió GitHub por su adopción y visibilidad.

## Consecuencias

- **Positivas:** trazabilidad completa entre ticket y código; flujo de trabajo similar al de equipos empresariales.
- **Negativas:** se trabaja con dos herramientas en lugar de una, y la integración depende de que todos usen la clave del ticket en ramas y commits.