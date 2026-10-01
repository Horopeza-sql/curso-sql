# Estado Actual del Proyecto — SQL para Análisis de Datos

**Última actualización:** 2025-09-30 (sesión 4)

## 🎯 Fase actual
Escribiendo contenido de la Sección 0. Temas 0.1 a 0.5 completados. **Mitad de la sección.**

## ✅ Completado
- Todo lo de las sesiones 1, 2 y 3 (Git, Python, MkDocs, esqueleto, publicación, roadmap, portada, navegación, temas 0.1 a 0.5)
- Curso renombrado: "SQL para Análisis de Datos"
- Visión de programa completo (5 fases) definida
- Roadmap del programa creado (`docs/roadmap.md`)
- Portada actualizada (`docs/index.md`)
- `mkdocs.yml` actualizado con navegación agrupada
- **Sección 0: temas 0.1, 0.2, 0.3, 0.4, 0.5 completados con formato de pestañas**
- Videos recomendados en 0.1 y 0.2 (enlaces YouTube)

## 🔜 Próximos pasos
1. Escribir los 5 temas restantes de la Sección 0:
   - **0.6a Instalación de MySQL 8.4 LTS** ← siguiente tema
   - **0.6b Configuración inicial** (usuario, privilegios, BD, datos de práctica)
   - 0.7 Bases de datos relacionales
   - 0.8 Diseño de BD y normalización (básico)
   - 0.9 🎯 Definición del proyecto del curso
   - 0.10 Cómo usar esta guía + consejos
2. Sección 1 (Básicos)
3. Continuar con el resto

## 📌 Pendientes para el final de la Fase 1
- **Abrir enlaces externos en pestaña nueva:** actualmente los videos de YouTube se abren en la misma pestaña. Evaluar si migrar a HTML con `target="_blank"` (Opción 2) o JavaScript global (Opción 3). Revisar en TODOS los enlaces del curso.
- **Evaluar Mermaid para diagramas:** actualmente se usan diagramas ASCII. Revisar si conviene habilitar Mermaid en `mkdocs.yml` (requiere `pymdownx.superfences` con `custom_fences`) y decidir si vale la pena migrar los diagramas existentes. **Solo al final de la Fase 1** (para no tocar la configuración a mitad de curso).
- **Página "Índice del curso":** crear `docs/indice.md` con tabla de secciones y estado (completado/en progreso/pendiente). Actualización manual al final. Sin JavaScript, sin complicaciones (nivel 1).
- **Widget de progreso en portada:** mostrar en `index.md` un resumen del avance (ej: "5 de 80 temas completados"). Manual.
- **Certificado del curso:** evaluar al final de la Fase 1. Requiere análisis de legalidad (firma electrónica, sello de tiempo, verificación por código único). Considerar si se emite como "curso completado" sin aval institucional.
- Añadir más recursos gratuitos (videos, plataformas, PDFs) en todas las secciones.
- Revisar calidad de todos los ejemplos y ejercicios.
- Añadir capturas de pantalla/imágenes donde aporte valor.
- Verificar navegación móvil en todos los dispositivos.

## 📁 Estructura actual
```
curso-sql/
├── mkdocs.yml
├── .gitignore
├── PROYECTO/
│   ├── 00-ESTADO-ACTUAL.md
│   └── HISTORIAL/
│       ├── 2025-09-30.md
│       ├── 2025-09-30-sesion2.md
│       ├── 2025-09-30-sesion3.md
│       └── 2025-09-30-sesion4.md
└── docs/
    ├── index.md
    ├── roadmap.md
    ├── 00-introduccion.md ← 5 de 10 temas completados
    ├── 01-basicos.md
    ├── 02-intermedios.md
    ├── 03-avanzados.md
    ├── 04-objetos-bd.md
    ├── 05-administracion.md
    └── 06-referencia-rapida.md
```

## ⚠️ Notas importantes
- **Comandos:** usar `python -m mkdocs` (Python de Microsoft Store no añade scripts al PATH).
- **Trabajo desde 2 PCs:** `git pull` al llegar, `git push` al salir.
- **Sistema de continuidad:** actualizar este archivo + crear uno nuevo en `HISTORIAL/` al final de cada sesión.
- **Formato de contenido:** pestañas (💡 ¿Qué es? / 🔬 ¿Cómo funciona? / 📝 Sintaxis / 💻 Ejemplo / ⚠️ Errores comunes / 🎯 Ejercicio). **Nota:** en temas donde el molde no encaja (como 0.4 y 0.5), se adaptan los nombres de las pestañas al contenido sin romper la estructura general.
- **Regla pedagógica:** Sección 0 = cero código. Código real empieza en Sección 1.
- **Proyecto del curso:** Sistema de Ventas / Facturación / Cobranza.
- **Enlaces externos:** pendiente decidir si se abren en pestaña nueva (ver Pendientes).
- **Salarios:** decisión tomada en sesión 3 → **NO se publican cifras** en el curso (ni rangos). Motivo: envejecen mal y generan expectativas falsas.
- **MySQL:** versión **8.4 LTS** (no 9.x Innovation) por estabilidad y soporte a largo plazo.
- **Numeración del menú lateral:** sin números (limpio). Solo nombres de sección.
- **Numeración interna:** con números (0.1, 0.2, etc.) para referencia y progreso.