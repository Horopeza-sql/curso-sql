# Estado Actual del Proyecto — Curso SQL

**Última actualización:** 2025-09-30

## 🎯 Fase actual
Esqueleto del curso creado. Listo para empezar a escribir contenido.

## ✅ Completado
- Git 2.56.0 instalado y configurado
- Python 3.12.10 instalado (Microsoft Store)
- Cuenta GitHub: Horopeza-sql
- Repositorio `curso-sql` creado y clonado
- Sistema de continuidad `PROYECTO/` funcionando
- MkDocs 1.6.1 + Material 9.7.7 instalados
- `mkdocs.yml` configurado con tema, colores y navegación
- `docs/` con 8 archivos base (index + 7 secciones)
- Sitio funcionando en local (`python -m mkdocs serve`)

## 🔜 Próximos pasos
1. Publicar en GitHub Pages (`python -m mkdocs gh-deploy`)
2. Empezar a escribir la sección 0 (Introducción)
3. Luego sección 1 (Básicos)
4. Continuar con el resto

## 📁 Estructura actual
curso-sql/
├── mkdocs.yml
├── .gitignore
├── PROYECTO/
│   ├── 00-ESTADO-ACTUAL.md
│   └── HISTORIAL/
│       └── 2025-09-30.md
└── docs/
    ├── index.md
    ├── 00-introduccion.md
    ├── 01-basicos.md
    ├── 02-intermedios.md
    ├── 03-avanzados.md
    ├── 04-objetos-bd.md
    ├── 05-administracion.md
    └── 06-referencia-rapida.md

## ⚠️ Notas importantes
- **Comandos:** usar `python -m mkdocs` en lugar de `mkdocs` (Python de Microsoft Store no añade scripts al PATH).
- **Trabajo desde 2 PCs:** `git pull` al llegar, `git push` al salir.
- **Sistema de continuidad:** actualizar este archivo + crear uno nuevo en `HISTORIAL/` al final de cada sesión.