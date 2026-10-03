# Matriz Maestra de Competencias — Fase 1 · SQL

**Última actualización:** 2025-10-02 (sesión 5d)
**Estado:** Borrador inicial
**Ubicación:** `PROYECTO/matriz-competencias.md` (interno)

---

## Cómo leer esta matriz

| Campo | Significado |
|---|---|
| **Código** | Identificador del tema dentro de la sección (sección.tema) |
| **Código original** | Referencia a la numeración antigua (0.1, 0.6b, etc.) |
| **Competencia** | Verbo + objeto + condición. Una frase. |
| **Nivel** | Básico / Intermedio / Avanzado |
| **Entorno** | `world` · `employees` · proyecto |
| **Evidencia** | Entregable concreto y verificable |
| **Práctica** | 🟢 Guiada / 🟡 Autónoma / 🔴 Caso de negocio |
| **Criterio** | Cómo saber que la competencia se logró |
| **Estado** | ⬜ no empezado · 🟨 borrador · 🟩 revisado · ✅ publicado |

---

## Sección 1 · Introducción y Entorno

| Código | Cód. orig. | Tema | Competencia | Nivel | Entorno | Evidencia | Práctica | Criterio | Estado |
|---|---|---|---|---|---|---|---|---|---|
| 1.1 | 0.1 | ¿Qué es una base de datos? | Explicar qué es una BD relacional y sus componentes (tabla, fila, columna, clave) con un ejemplo propio | Básico | — | Glosario personal con 5 términos | 🟢 | Define los 5 términos sin mirar apuntes | 🟨 |
| 1.2 | 0.2 | ¿Qué es SQL? | Diferenciar SQL (lenguaje) de MySQL (motor) y clasificar SQL en DDL / DML / DQL | Básico | — | Cuadro comparativo SQL vs MySQL | 🟢 | Distingue ambos conceptos en un test corto | 🟨 |
| 1.3 | 0.3 | ¿Por qué aprender SQL? | Identificar 3 contextos reales donde SQL aporta valor en análisis de datos | Básico | — | Lista de 3 casos propios | 🟢 | Los 3 casos son concretos, no genéricos | 🟨 |
| 1.4 | 0.4 | Alcance del curso | Delimitar qué cubre y qué no cubre el programa, y ubicar la Fase 1 dentro del roadmap | Básico | — | Nota personal "qué espero / qué no espero" | 🟢 | Reconoce los 3 límites (no DBA, no backend, no ERP) | 🟨 |
| 1.5 | 0.5 | Trabajos y roles | Describir 4 roles donde se usa SQL a diario, sin mencionar salarios | Básico | — | Ficha por rol | 🟢 | Nombra 4 roles y una tarea típica de cada uno | 🟨 |
| 1.6 | 0.6a | Instalación de MySQL 8.4 LTS | Instalar MySQL 8.4 LTS, conectar con cliente y ejecutar `SELECT VERSION()` | Básico | local | Captura + consulta ejecutada | 🟢 | Devuelve `8.4.x` en consola | 🟨 |
| 1.7 | 0.6b | Configuración inicial | Crear usuario `analista` con privilegios limitados, crear BD `ventas` en utf8mb4 y cargar `world` y `employees` | Básico | local | Script `.sql` con la creación + bases cargadas visibles | 🟢 | Existe usuario `analista`, BD `ventas`, y `world` y `employees` consultables | ⬜ |
| 1.8 | 0.9 | Definición del proyecto del curso | Describir el sistema Ventas/Facturación/Cobranza y sus entidades principales | Básico | proyecto | Diagrama ASCII del modelo + lista de entidades | 🟢 | Nombra las 4 entidades núcleo y sus relaciones | ⬜ |
| 1.9 | 0.10 | Cómo usar esta guía | Aplicar el flujo de estudio (leer, practicar, validar, avanzar) a las secciones del curso | Básico | — | Nota personal de rutina de estudio | 🟢 | Define su propia rutina y la sigue durante una sección | ⬜ |

---

## Sección 2 · Fundamentos de BD

| Código | Cód. orig. | Tema | Competencia | Nivel | Entorno | Evidencia | Práctica | Criterio | Estado |
|---|---|---|---|---|---|---|---|---|---|
| 2.1 | 0.7 | Bases de datos relacionales | Explicar PK, FK e integridad referencial, e identificar los tres tipos de relaciones (1:1, 1:N, N:M) | Básico | world / employees | Diagrama ASCII de relaciones + ejemplos reales | 🟢 | Identifica PK y FK en una tabla de `world` | ⬜ |
| 2.2 | 0.8 | Diseño de BD y normalización | Aplicar 1FN, 2FN y 3FN a un caso simple, justificando cada paso | Básico | proyecto | Tabla antes/después normalizada | 🟢 | Normaliza una tabla hasta 3FN sin omitir pasos | ⬜ |

---

## Secciones 3 a 11 — esqueleto provisional

Sin temas definidos aún.

| Sección | Temas definidos | Temas escritos | Estado global |
|---|---|---|---|
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

## Notas de estructura

- **0.6a (Instalación) y 0.6b (Configuración inicial) son dos temas distintos.** El primero instala; el segundo crea usuario, BD y carga datos.
- **0.9 (Definición del proyecto) se queda en Introducción**, no en Proyecto Final. Motivo: el proyecto es transversal y el estudiante debe conocerlo desde el principio. La sección 10 hará la integración final, no la presentación.
- **0.10 (Cómo usar la guía) va al final de Introducción**, como cierre de la sección.

---

## Reglas de uso de esta matriz

1. Una fila por **tema**, no por sección.
2. Toda fila con estado ✅ debe tener: competencia, evidencia, práctica y criterio.
3. El campo **entorno** solo aplica desde la sección 3 en adelante con datos reales; en Sección 1 va `—` salvo instalación (local) y proyecto.
4. Los cambios de estado se registran en el historial de la sesión.
5. Esta matriz es **interna**. Si en el futuro se publica, se extrae una versión simplificada a `docs/`.

---

## Próximos pasos de la matriz

1. Definir la lista de temas de la Sección 3 (Consultas Esenciales).
2. Escribir los temas 1.7 a 1.9 (0.6b, 0.9, 0.10) y los temas 2.1 y 2.2 (0.7, 0.8).
3. Reescribir 1.1 a 1.6 con la plantilla de 13 pasos.
4. Pasar estados de 🟨 a 🟩 cuando cada tema esté revisado.

---

## Decisión transversal: IA en el curso

- La IA **no se aborda como eje transversal** ni se integra en cada tema.
- Se enseña **una sola clase al final**, dentro de la sección **10 · Proyecto Final**, como tema 10.x.
- Enfoque: **principios, no herramientas**. Se enseñan principios (verificar, criticar, entender antes de aplicar) y solo se mencionan herramientas concretas como ejemplos.
- Motivo: los modelos y herramientas de IA cambian cada pocos meses; los principios, no.
- En **1.9 · Cómo usar esta guía** se incluirá una mención breve a que la IA se verá al final del programa.
- Contenido previsto del tema 10.x:
  - Cómo pedir a la IA que **explique** una consulta que no entiendes (no que la escriba).
  - Cómo pedir que **critique** tu consulta en lugar de reescribirla.
  - Errores típicos de la IA en SQL: JOINs mal planteados, NULLs ignorados, agregaciones sin GROUP BY correcto, filtros mal ubicados.
  - Cuándo **NO** usar IA: datos sensibles, decisiones críticas sin verificar, cuando no entiendes el resultado.
  - Ejercicio final: la IA te da una consulta con un error sutil, encuéntralo.