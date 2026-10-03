# Estado Actual del Proyecto — Programa de Análisis de Datos desde Cero

**Última actualización:** 2025-10-03 (sesión 5e)

## 🎯 Fase actual
Matriz Maestra de Competencias con Sección 1 y 2 detalladas. Los 9 temas de Introducción y Entorno están definidos (falta escribirlos). Siguiente gran bloque: definir temas de Consultas Esenciales.

## ✅ Completado
- Todo lo de sesiones 1 a 5c
- **Sesión 5d (hoy):**
  - Definidos los temas 0.6b–0.10 (existían de una conversación anterior)
  - Decidida su ubicación:
    - 0.6b → `01-introduccion/`
    - 0.7 y 0.8 → `02-fundamentos-bd/`
    - 0.9 → `01-introduccion/` (definición del proyecto, NO en Proyecto Final)
    - 0.10 → `01-introduccion/`
  - Matriz Maestra reescrita con:
    - Sección 1 completa (9 temas, 1.1 a 1.9)
    - Sección 2 completa (2 temas, 2.1 y 2.2)
    - Columna "código original" para trazabilidad
- **Sesión 5e (hoy):**
  - Reescrito `docs/index.md` como portada del **programa** (no de la Fase 1)
  - Decisión firme: IA se aborda como **tema final en Proyecto Final (10.x)**, no como eje transversal
  - Enfoque IA: **principios, no herramientas**
  - Mención breve sobre IA en 1.9 cuando se reescriba

## 🔜 Próximos pasos
1. Definir la lista de temas de Sección 3 · Consultas Esenciales
2. Escribir los temas 0.6b, 0.9 y 0.10
3. Escribir los temas 0.7 y 0.8 en `02-fundamentos-bd/`
4. Reescribir 1.1 a 1.6 con la plantilla de 13 pasos
5. Actualizar `manual-continuidad.html`

## 📌 Decisiones firmes
- **Arquitectura:** 11 secciones + 2 grupos
- **Sin números** en el menú visible
- **Plantilla pedagógica:** 13 pasos
- **Práctica en 3 niveles:** 🟢 🟡 🔴
- **Proyecto transversal:** Ventas / Facturación / Cobranza
- **Proyecto:** se presenta en Introducción (0.9), se integra en Proyecto Final (sección 10)
- **Tres entornos:** `world` → `employees` → proyecto propio
- **MySQL 8.4 LTS**
- **Sin cifras de salario** ni afirmaciones de mercado sin fuente
- **No es un curso de DBA** ni de backend ni ERP
- **Enlaces externos** en misma pestaña (pendiente revisar)
- **Mermaid** descartado por ahora (diagramas ASCII)
- **Videos:** placeholders `<!-- VIDEO PENDIENTE -->`
- **Diseño visual y navegación** se pueden cambiar después sin afectar al contenido

## 📌 Pendientes para el final de la Fase 1
- Abrir enlaces externos en pestaña nueva: evaluar HTML o JS global
- Mermaid: evaluar activación
- **IA:** se enseña al final, en Proyecto Final (10.x). Principios, no herramientas. No es eje transversal.
- Página "Índice del curso" con tabla de avance
- Widget de progreso en portada
- Certificado del curso (evaluar legalidad al final)
- Recursos gratuitos: añadir más videos, PDFs, plataformas
- Revisar calidad de ejemplos y ejercicios
- Añadir capturas/imágenes
- Verificar navegación móvil
- Revisar plantilla de 13 pasos en los temas ya migrados (1.1–1.6)

## 📁 Estructura actual
curso-sql/
├── mkdocs.yml
├── mkdocs.yml.backup
├── .gitignore
├── PROYECTO/
│ ├── 00-ESTADO-ACTUAL.md
│ ├── matriz-competencias.md
│ ├── manual-continuidad.html
│ ├── REVISION-EXTERNA.md
│ └── HISTORIAL/
│ ├── 2025-09-30.md
│ ├── 2025-09-30-sesion2.md
│ ├── 2025-09-30-sesion3.md
│ ├── 2025-09-30-sesion4.md
│ ├── 2025-10-02-sesion5.md
│ ├── 2025-10-02-sesion5b.md
│ └── 2025-10-02-sesion5c.md
└── docs/
├── index.md
├── roadmap.md
├── fase-1/
│ └── index.md
├── 01-introduccion/
│ ├── index.md
│ ├── que-es-base-de-datos.md
│ ├── que-es-sql.md
│ ├── por-que-aprender-sql.md
│ ├── alcance.md
│ ├── trabajos.md
│ └── instalacion-mysql.md
├── 02-fundamentos-bd/index.md
├── 03-consultas/index.md
├── 04-analisis/index.md
├── 05-relaciones/index.md
├── 06-diseno-objetos/index.md
├── 07-sql-avanzado/index.md
├── 08-calidad/index.md
├── 09-administracion/index.md
├── 10-proyecto/index.md
└── 11-referencia/index.md

## ⚠️ Notas importantes
- **Comandos:** usar `python -m mkdocs`
- **Trabajo desde 2 PCs:** `git pull` al llegar, `git push` al salir
- **Continuidad:** actualizar este archivo + crear uno nuevo en `HISTORIAL/` al final de cada sesión
- **Formato de contenido:** pestañas flexibles + admonitions + ejercicios desplegables
- **Regla pedagógica:** "Tratar lo menos posible el código que aún no se ha visto"
- **Proyecto del curso:** Sistema de Ventas / Facturación / Cobranza
- **Salarios:** NO se publican cifras
- **MySQL:** 8.4 LTS
- **Matriz de Competencias:** en `PROYECTO/matriz-competencias.md`, uso interno
- **Al mover archivos `.md`:** revisar enlaces relativos internos (nos pasó con `fase-1.md`)
