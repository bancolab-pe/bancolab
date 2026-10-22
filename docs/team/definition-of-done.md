# Definition of Done (DoD)

Un ticket está **terminado** solo cuando cumple todo lo siguiente:

## Código

- [ ] El código cumple los **criterios de aceptación** del ticket.
- [ ] Sigue las **convenciones** del equipo (ver `conventions.md`).
- [ ] **No hay datos sensibles** en el código ni en los logs (contraseñas, DNI, números de tarjeta).

## Pruebas

- [ ] Tiene **tests unitarios** de la lógica nueva o modificada.
- [ ] Todos los tests pasan.

## Revisión

- [ ] Entró por **Pull Request** con descripción completa (Qué / Por qué / Cómo probar).
- [ ] El **pipeline** está en verde (build, tests y calidad).
- [ ] Pasó **code review**.
- [ ] Se hizo **squash merge** a `main` y se borró la rama.

## Cierre

- [ ] Documentación actualizada, si el cambio lo requiere.
- [ ] Se respondieron las **preguntas de defensa** del ticket.
- [ ] El ticket está en **Listo** en Jira.

## Nota

Las reglas de pipeline y tests aplican a partir del momento en que exista el pipeline (Épica 2). Los tickets de documentación no requieren tests.