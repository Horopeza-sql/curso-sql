# Estado Actual del Proyecto — Programa de Análisis de Datos desde Cero

**Última actualización:** 2025-10-02 (sesión 5b)

## 🎯 Fase actual
Migración de contenido completada. Sección "Introducción y Entorno" con 6 temas individuales. Listo para crear Matriz de Competencias.

## ✅ Completado
- Todo lo de las sesiones 1-4 (infraestructura, sitio online, temas 0.1-0.5, 0.6a escrito)
- **Reorganización completa de la estructura:**
  - 11 secciones nuevas definidas
  - 11 carpetas creadas en `docs/`
  - Páginas índice creadas por sección
  - Página índice de Fase 1 (`fase-1.md`)
- **`mkdocs.yml` actualizado:**
  - Título: "Programa de Análisis de Datos desde Cero"
  - Features: `navigation.sections`, `navigation.expand`, `navigation.indexes`, `navigation.prune`
  - `toc_depth: 2`
  - Nav con 2 grupos: "Programa" y "Fase 1 · SQL"
- **Migración de contenido (tema 0.1 a 0.6a):**
  - `docs/01-introduccion/que-es-base-de-datos.md`
  - `docs/01-introduccion/que-es-sql.md`
  - `docs/01-introduccion/por-que-aprender-sql.md`
  - `docs/01-introduccion/alcance.md`
  - `docs/01-introduccion/trabajos.md`
  - `docs/01-introduccion/instalacion-mysql.md`
  - `docs/01-introduccion/index.md` actualizado con enlaces
- **Archivos antiguos eliminados:** `00-introduccion.md`, `01-basicos.md`, `02-intermedios.md`, `03-avanzados.md`, `04-objetos-bd.md`, `05-administracion.md`, `06-referencia-rapida.md`
- **Sitio online actualizado** con la nueva estructura

## 🔜 Próximos pasos
1. **Crear la Matriz Maestra de Competencias** (siguiente paso inmediato)
2. **Migrar 0.6a** (instalación de MySQL) a sección independiente si se decide
3. **Escribir temas pendientes** (0.6b a 0.10)
4. **Empezar Sección de Consultas SQL**

## 📌 Decisiones importantes tomadas
- **Arquitectura:** 11 secciones + 2 grupos ("Programa" y "Fase 1 · SQL")
- **Sin números en el menú visible** (números solo en nombres de archivos internos)
- **Plantilla pedagógica:** 13 pasos (Objetivo → Problema → Cuándo → Concepto → Sintaxis → Ejemplo → Errores → Práctica 3 niveles → Validación → Aplicación → Criterio de éxito → Resumen → Siguiente)
- **Práctica en 3 niveles:** 🟢 Guiada / 🟡 Autónoma / 🔴 Caso de negocio
- **Proyecto transversal:** Ventas / Facturación / Cobranza
- **Tres entornos:** `world` → `employees` → proyecto propio
- **Sin cifras de salario** ni afirmaciones de mercado sin fuente
- **No es un curso de DBA** ni de backend ni ERP
- **MySQL 8.4 LTS**
- **Enlaces externos** en misma pestaña (pendiente revisar al final)
- **Mermaid** descartado por ahora (diagramas ASCII)
- **Videos:** placeholders `<!-- VIDEO PENDIENTE -->` para buscar y añadir después
- **Diseño visual y navegación se pueden cambiar después** sin afectar al contenido

## 📌 Pendientes para el final de la Fase 1
- **Abrir enlaces externos en pestaña nueva:** evaluar HTML o JS global.
- **Mermaid:** evaluar activación para diagramas.
- **Página "Índice del curso":** crear con tabla de avance.
- **Widget de progreso en portada:** manual.
- **Certificado del curso:** evaluar legalidad al final.
- **Recursos gratuitos:** añadir más videos, PDFs, plataformas.
- **Revisar calidad** de ejemplos y ejercicios.
- **Añadir capturas/imágenes.**
- **Verificar navegación móvil.**

## 📁 Estructura actual
```
curso-sql/
├── mkdocs.yml
├── mkdocs.yml.backup
├── .gitignore
├── PROYECTO/
│   ├── 00-ESTADO-ACTUAL.md
│   ├── manual-continuidad.html
│   ├── REVISION-EXTERNA.md
│   └── HISTORIAL/
│       ├── 2025-09-30.md
│       ├── 2025-09-30-sesion2.md
│       ├── 2025-09-30-sesion3.md
│       ├── 2025-09-30-sesion4.md
│       ├── 2025-10-02-sesion5.md
│       └── 2025-10-02-sesion5b.md (pendiente crear)
└── docs/
    ├── index.md
    ├── roadmap.md
    ├── fase-1.md
    ├── 01-introduccion/
    │   ├── index.md
    │   ├── que-es-base-de-datos.md
    │   ├── que-es-sql.md
    │   ├── por-que-aprender-sql.md
    │   ├── alcance.md
    │   ├── trabajos.md
    │   └── instalacion-mysql.md
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
```

## ⚠️ Notas importantes
- **Comandos:** usar `python -m mkdocs` (Python de Microsoft Store no añade scripts al PATH).
- **Trabajo desde 2 PCs:** `git pull` al llegar, `git push` al salir.
- **Sistema de continuidad:** actualizar este archivo + crear uno nuevo en `HISTORIAL/` al final de cada sesión.
- **Formato de contenido:** pestañas flexibles + admonitions + ejercicios desplegables.
- **Regla pedagógica:** "Tratar lo menos posible el código que aún no se ha visto. Si es necesario para el tema, se toca de forma controlada y con disclaimer."
- **Proyecto del curso:** Sistema de Ventas / Facturación / Cobranza.
- **Salarios:** NO se publican cifras.
- **MySQL:** 8.4 LTS.