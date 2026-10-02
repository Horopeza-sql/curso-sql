# Estado Actual del Proyecto — Programa de Análisis de Datos desde Cero

**Última actualización:** 2025-10-02 (sesión 5c)

## 🎯 Fase actual
Matriz Maestra de Competencias creada (borrador inicial). Sección "Introducción y Entorno" con 6 temas migrados. Pendiente: definir temas 0.6b–0.10 y empezar Consultas Esenciales.

## ✅ Completado
- Todo lo de las sesiones 1–4 (infraestructura, sitio online, temas 0.1–0.5, 0.6a escrito)
- **Sesión 5:** arquitectura de 11 secciones, reorganización de `docs/`, `mkdocs.yml` con 2 grupos ("Programa" y "Fase 1 · SQL")
- **Sesión 5b:** migración de 0.1–0.6a a archivos individuales en `docs/01-introduccion/`
- **Sesión 5c (hoy):**
  - Validación cruzada: detectado y corregido bug de indentación en `features` de `mkdocs.yml` (estaba dentro de `palette`)
  - `navigation.prune` eliminado (había secciones vacías que conviene ver)
  - Creada `PROYECTO/matriz-competencias.md` (borrador inicial, con Sección 1 detallada y esqueleto 2–11)
  - Definido: 0.6a (instalación MySQL) se queda en `01-introduccion/`, no se mueve a sección propia
  - Definido: reescritura de temas a plantilla de 13 pasos se hará después de cerrar la matriz

## 🔜 Próximos pasos
1. Definir los temas 0.6b–0.10 (Sección 1) y añadirlos a la matriz
2. Definir la lista de temas de Sección 3 · Consultas Esenciales
3. Reescribir 1.1–1.6 con la plantilla de 13 pasos
4. Empezar a escribir la Sección de Consultas Esenciales
5. Actualizar `manual-continuidad.html` (sección de pendientes + añadir "cómo pasar archivos a la IA por CMD")

## 📌 Decisiones firmes
- **Arquitectura:** 11 secciones + 2 grupos
- **Sin números** en el menú visible
- **Plantilla pedagógica:** 13 pasos
- **Práctica en 3 niveles:** 🟢 🟡 🔴
- **Proyecto transversal:** Ventas / Facturación / Cobranza
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
│ └── 2025-10-02-sesion5b.md
└── docs/
├── index.md
├── roadmap.md
├── fase-1.md
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