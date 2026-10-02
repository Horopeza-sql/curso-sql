# Matriz Maestra de Competencias — Fase 1 · SQL

**Última actualización:** 2025-10-02 (sesión 5c)
**Estado:** Borrador inicial
**Ubicación:** `PROYECTO/matriz-competencias.md` (interno)

---

## Cómo leer esta matriz

| Campo | Significado |
|---|---|
| **Código** | Identificador del tema (sección.tema) |
| **Competencia** | Verbo + objeto + condición. Una frase. |
| **Nivel** | Básico / Intermedio / Avanzado |
| **Entorno** | `world` · `employees` · proyecto |
| **Evidencia** | Entregable concreto y verificable |
| **Práctica** | 🟢 Guiada / 🟡 Autónoma / 🔴 Caso de negocio |
| **Criterio** | Cómo saber que la competencia se logró |
| **Estado** | ⬜ no empezado · 🟨 borrador · 🟩 revisado · ✅ publicado |

---

## Sección 1 · Introducción y Entorno

| Código | Tema | Competencia | Nivel | Entorno | Evidencia | Práctica | Criterio | Estado |
|---|---|---|---|---|---|---|---|---|
| 1.1 | ¿Qué es una base de datos? | Explicar qué es una BD relacional y sus componentes (tabla, fila, columna, clave) con un ejemplo propio | Básico | — | Glosario personal con 5 términos | 🟢 | Define los 5 términos sin mirar apuntes | 🟨 |
| 1.2 | ¿Qué es SQL? | Diferenciar SQL (lenguaje) de MySQL (motor) y clasificar SQL en DDL / DML / DQL | Básico | — | Cuadro comparativo SQL vs MySQL | 🟢 | Distingue ambos conceptos en un test corto | 🟨 |
| 1.3 | ¿Por qué aprender SQL? | Identificar 3 contextos reales donde SQL aporta valor en análisis de datos | Básico | — | Lista de 3 casos propios | 🟢 | Los 3 casos son concretos, no genéricos | 🟨 |
| 1.4 | Alcance del curso | Delimitar qué cubre y qué no cubre el programa, y ubicar la Fase 1 dentro del roadmap | Básico | — | Nota personal "qué espero / qué no espero" | 🟢 | Reconoce los 3 límites (no DBA, no backend, no ERP) | 🟨 |
| 1.5 | Trabajos y roles | Describir 4 roles donde se usa SQL a diario, sin mencionar salarios | Básico | — | Ficha por rol | 🟢 | Nombra 4 roles y una tarea típica de cada uno | 🟨 |
| 1.6 | Instalación de MySQL 8.4 LTS | Instalar MySQL 8.4 LTS, conectar con cliente y ejecutar `SELECT VERSION()` | Básico | local | Captura + consulta ejecutada | 🟢 | Devuelve `8.4.x` en consola | 🟨 |
| 1.7 | (pendiente 0.6b) | — | — | — | — | — | — | ⬜ |
| 1.8 | (pendiente 0.7) | — | — | — | — | — | — | ⬜ |
| 1.9 | (pendiente 0.8) | — | — | — | — | — | — | ⬜ |
| 1.10 | (pendiente 0.9) | — | — | — | — | — | — | ⬜ |
| 1.11 | (pendiente 0.10) | — | — | — | — | — | — | ⬜ |

**Nota:** los códigos 1.7 a 1.11 corresponden a 0.6b–0.10, aún no definidos. No se inventan.

---

## Secciones 2 a 11 — esqueleto provisional

Sin temas definidos aún. Esta tabla se rellena cuando cada sección tenga su lista de temas cerrada.

| Sección | Temas definidos | Temas escritos | Estado global |
|---|---|---|---|
| 2 · Fundamentos de BD | 0 | 0 | ⬜ |
| 3 · Consultas Esenciales | 0 | 0 | ⬜ |
| 4 · Análisis y Agregaciones | 0 | 0 | ⬜ |
| 5 · Relaciones y Modelado | 0 | 0 | ⬜ |
| 6 · Diseño y Objetos | 0 | 0 | ⬜ |
| 7 · SQL Avanzado | 0 | 0 | ⬜ |
| 8 · Calidad y Trabajo Profesional | 0 | 0 | ⬜ |
| 9 · Administración Básica | 0 | 0 | ⬜ |
| 10 · Proyecto Final | 0 | 0 | ⬜ |
| 11 · Referencia Rápida | 0 | 0 | ⬜ |

---

## Reglas de uso de esta matriz

1. Una fila por **tema**, no por sección.
2. Toda fila con estado ✅ debe tener: competencia, evidencia, práctica y criterio.
3. El campo **entorno** solo aplica desde la sección 3 en adelante; en Sección 1 va `—` salvo instalación (que es `local`).
4. Los cambios de estado se registran en el historial de la sesión.
5. Esta matriz es **interna**. Si en el futuro se publica, se extrae una versión simplificada a `docs/`.

---

## Próximos pasos de la matriz

1. Definir los temas 0.6b–0.10 (Sección 1).
2. Definir la lista de temas de la Sección 3 (Consultas Esenciales), que es la siguiente a escribir.
3. Revisar y reescribir 1.1–1.6 con la plantilla de 13 pasos.
4. Pasar estados de 🟨 a 🟩 cuando cada tema esté revisado.