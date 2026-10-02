# Estado Actual del Proyecto — Programa de Análisis de Datos desde Cero

**Última actualización:** 2025-10-02 (sesión 5)

## 🎯 Fase actual
Arquitectura reorganizada. Navegación redefinida. Listo para crear Matriz de Competencias y empezar contenido.

## ✅ Completado
- Todo lo de las sesiones 1-4 (infraestructura, sitio online, temas 0.1-0.5, 0.6a escrito)
- Reorganización completa de la estructura del proyecto:
  - **11 secciones nuevas** definidas
  - **Carpetas creadas:** `01-introduccion/`, `02-fundamentos-bd/`, `03-consultas/`, `04-analisis/`, `05-relaciones/`, `06-diseno-objetos/`, `07-sql-avanzado/`, `08-calidad/`, `09-administracion/`, `10-proyecto/`, `11-referencia/`
  - **Páginas índice** creadas en cada sección (`index.md`)
  - **Página índice de Fase 1** creada (`docs/fase-1.md`)
- `mkdocs.yml` actualizado:
  - Título: "Programa de Análisis de Datos desde Cero"
  - Features: `navigation.instant`, `navigation.tracking`, `navigation.sections`, `navigation.expand`, `navigation.indexes`, `navigation.top`, `navigation.prune`
  - `toc_depth: 2` (para limitar el TOC a `##`)
  - Nav reorganizado en 2 grupos: "Programa" y "Fase 1 · SQL"
- Backup del `mkdocs.yml` original en `mkdocs.yml.backup`

## 🔜 Próximos pasos
1. **Crear la Matriz Maestra de Competencias** (siguiente paso inmediato)
2. **Migrar contenido** de `00-introduccion.md` (temas 0.1-0.5) a la nueva estructura (`01-introduccion/`)
3. **Migrar 0.6a** a `02-preparacion/` (o sección correspondiente)
4. **Escribir temas pendientes** (0.6b a 0.10)
5. **Empezar Sección de Consultas SQL**

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
│   ├── BLUEPRINT.md (pendiente guardar)
│   ├── REVISION-EXTERNA.md
│   └── HISTORIAL/
│       ├── 2025-09-30.md
│       ├── 2025-09-30-sesion2.md
│       ├── 2025-09-30-sesion3.md
│       └── 2025-09-30-sesion4.md
└── docs/
    ├── index.md
    ├── roadmap.md
    ├── fase-1.md
    ├── 00-introduccion.md (contenido antiguo, pendiente migrar)
    ├── 01-basicos.md (antiguo, pendiente eliminar)
    ├── 02-intermedios.md (antiguo)
    ├── 03-avanzados.md (antiguo)
    ├── 04-objetos-bd.md (antiguo)
    ├── 05-administracion.md (antiguo)
    ├── 06-referencia-rapida.md (antiguo)
    ├── 01-introduccion/index.md
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