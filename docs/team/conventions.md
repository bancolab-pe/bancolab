# Convenciones del equipo BancoLab

Reglas que sigue todo el equipo para que el código y el historial sean fáciles de entender y rastrear.

## 1. Ramas

**Formato:** `tipo/BANK-XX-descripcion-corta`

| Tipo | Cuándo se usa | Ejemplo |
|---|---|---|
| `feature` | Funcionalidad nueva | `feature/BANK-15-consultar-tasa` |
| `bugfix` | Corrección de un error | `bugfix/BANK-22-redondeo-montos` |
| `hotfix` | Corrección urgente en producción | `hotfix/BANK-30-timeout-pagos` |
| `docs` | Solo documentación | `docs/BANK-11-convenciones` |
| `chore` | Mantenimiento (dependencias, configuración) | `chore/BANK-40-actualizar-spring` |

**Reglas:**
- Todo en minúsculas y con palabras separadas por guiones.
- Siempre incluye la clave del ticket (`BANK-XX`), así Jira la vincula automáticamente.
- Se crea desde `main` actualizado (`git pull` antes de crear la rama).
- Nunca se hace push directo a `main`: está protegida.

## 2. Commits

Seguimos el estándar **Conventional Commits**.

**Formato:** `tipo(BANK-XX): descripción`

| Tipo | Significado |
|---|---|
| `feat` | Funcionalidad nueva |
| `fix` | Corrección de un error |
| `docs` | Documentación |
| `test` | Agregar o corregir tests |
| `refactor` | Mejorar el código sin cambiar su comportamiento |
| `chore` | Mantenimiento |
| `ci` | Cambios en el pipeline |

**Ejemplos:**
- `feat(BANK-15): agrega endpoint para consultar la tasa del día`
- `fix(BANK-22): corrige redondeo usando BigDecimal`

**Reglas:**
- La descripción va en presente: "agrega", no "agregué".
- Corta y clara (idealmente menos de 72 caracteres).
- Un cambio lógico por commit.

## 3. Pull Requests

**Título:** `BANK-XX: descripción`

**La descripción del PR debe responder:**
- **Qué** cambia.
- **Por qué** se hace.
- **Cómo probarlo.**

**Reglas:**
- Todo cambio a `main` entra por Pull Request.
- El pipeline debe estar en verde antes del merge.
- Debe pasar code review.
- Se mergea con **squash merge**: todos los commits del PR se juntan en uno solo al entrar a `main`, para mantener el historial limpio.
- La rama se borra después del merge.