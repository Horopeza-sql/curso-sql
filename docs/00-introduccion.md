# 0. Introducción

Bienvenido a la **Fase 1** del programa **Análisis de Datos desde Cero**.

Antes de escribir una sola línea de SQL, vamos a entender **qué estamos haciendo y por qué**. Esta sección es la base de todo lo que viene después.

!!! info "📌 Nota importante"
    En esta sección **no verás código SQL todavía**. Solo conceptos, analogías y ejemplos de **qué podrás hacer** cuando termines el curso. El código real empieza en la Sección 1.

---

## 0.1 ¿Qué es una base de datos?

=== "💡 ¿Qué es?"

    Una **base de datos** es un lugar donde guardamos información de forma **organizada** para poder encontrarla, actualizarla y relacionarla fácilmente.

    Piensa en una **agenda de contactos**. Tienes nombres, teléfonos, correos. Si buscas "Juan", lo encuentras rápido porque están ordenados. Eso, llevado a un sistema informático, es una base de datos.

    Ejemplos cotidianos:
    - 📱 Los contactos de tu teléfono.
    - 🏦 Los movimientos de tu cuenta bancaria.
    - 🛒 Los productos de una tienda online.
    - 📊 Los KPIs de una empresa (ventas, clientes, márgenes).

    Como **analista de datos**, tu trabajo consistirá en **hacer preguntas** a esas bases de datos y obtener respuestas útiles para el negocio.

    !!! tip "📺 Video recomendado"
        ¿Prefieres una explicación en video? Mira este short:
        [🔗 ¿Qué es exactamente una base de datos?](https://youtube.com/shorts/L9hJYVCFOB8?si=yW9dq8elKvYJImlC)

=== "🔬 ¿Cómo funciona?"

    Técnicamente, una base de datos es un **conjunto de datos almacenados sistemáticamente** en un soporte informático, diseñado para:

    1. **Almacenar** información de forma persistente (no se pierde al apagar el equipo).
    2. **Organizar** los datos en estructuras (tablas, columnas, filas).
    3. **Relacionar** datos entre sí (un cliente tiene facturas, una factura tiene productos).
    4. **Consultar** los datos de forma rápida y eficiente.
    5. **Garantizar** la integridad y consistencia (que no haya datos contradictorios).

    Una base de datos **no es un archivo de Excel**. La diferencia clave:
    - Excel: piensa en **celdas**.
    - Base de datos: piensa en **relaciones entre tablas**.

    Y aquí está el punto clave para un **analista de datos**: una base de datos bien diseñada te permite **cruzar información** para descubrir patrones que en Excel serían imposibles.

=== "💻 Ejemplo"

    Imagina la base de datos `world` que usaremos en el curso. Tiene tres tablas principales:

    **Tabla `country`** (países):
    ```
    Code  | Name         | Continent      | Population
    ------|--------------|----------------|------------
    ESP   | Spain        | Europe         | 39441700
    VEN   | Venezuela    | South America  | 28562000
    JPN   | Japan        | Asia           | 126714000
    ```

    **Tabla `city`** (ciudades):
    ```
    ID    | Name         | CountryCode | Population
    ------|--------------|-------------|------------
    1     | Caracas      | VEN         | 2500000
    2     | Madrid       | ESP         | 3100000
    3     | Tokio        | JPN         | 8200000
    ```

    **Tabla `countrylanguage`** (idiomas por país):
    ```
    CountryCode | Language   | IsOfficial | Percentage
    ------------|------------|------------|------------
    VEN         | Spanish    | T          | 96.7
    ESP         | Spanish    | T          | 99.9
    JPN         | Japanese   | T          | 99.9
    ```

    Fíjate en algo importante: **las tablas están relacionadas**. La tabla `city` tiene una columna `CountryCode` que conecta con `country`. Eso es lo que hace **relacional** a una base de datos.

    Como analista, podrías preguntar:
    > "¿Qué ciudades de Sudamérica tienen más de 1 millón de habitantes?"

    Y obtener una respuesta como:

    ```
    Name      | CountryCode | Population
    ----------|-------------|------------
    Caracas   | VEN         | 2500000
    Bogotá    | COL         | 6268000
    Lima      | PER         | 6464000
    ```

    **Fíjate que solo vemos el resultado, no cómo se obtiene.** Eso es el poder de las bases de datos: haces la pregunta y obtienes la respuesta.

=== "⚠️ Errores comunes"

    !!! warning "Confundir base de datos con tabla"
        Una **base de datos** es el conjunto completo. Una **tabla** es una parte dentro de ella. Es como confundir una biblioteca con un estante.

    !!! warning "Pensar que una BD es un Excel"
        Excel es una hoja de cálculo. Una base de datos es un sistema con **relaciones**, **integridad** y **consultas optimizadas**. No son lo mismo.

    !!! warning "Creer que una BD es solo para programadores"
        Las bases de datos las usan analistas, contadores, gerentes, médicos, científicos... Cualquier persona que trabaje con datos. **Tú, como analista, es tu herramienta principal.**

=== "🎯 Ejercicio"

    Piensa en **3 ejemplos de bases de datos** que uses en tu día a día (apps, webs, sistemas).

    Y responde:
    - ¿Qué tipo de preguntas le harías a cada una?
    - ¿Qué información podrías extraer para tomar decisiones?

    ??? success "Ver posible respuesta"
        - 🎵 **Spotify:** canciones, artistas, álbumes, playlists.
          *Preguntas:* ¿Cuáles son mis artistas más escuchados del mes? ¿Qué género escucho más?
        - 📚 **Amazon:** productos, clientes, pedidos, reseñas.
          *Preguntas:* ¿Qué productos se venden más? ¿Qué clientes compran más seguido?
        - 🏦 **Tu banco:** cuentas, movimientos, clientes, sucursales.
          *Preguntas:* ¿En qué categorías gasto más? ¿Cuál es mi promedio de gasto mensual?

        Cada uno guarda millones de registros relacionados entre sí. **El analista convierte esos datos en decisiones.**

---

## 0.2 ¿Qué es SQL?

=== "💡 ¿Qué es?"

    **SQL** son las siglas de **Structured Query Language** (Lenguaje de Consulta Estructurado).

    Es el **idioma** que usamos para hablar con las bases de datos. Con SQL podemos:
    - **Preguntar** cosas ("dame todos los clientes de Caracas").
    - **Insertar** datos nuevos.
    - **Actualizar** datos existentes.
    - **Borrar** datos que ya no sirven.
    - **Crear** tablas y relaciones.

    Si una base de datos fuera un archivador, **SQL sería el idioma** en el que le pides las cosas.

    Para un **analista de datos**, SQL es **la herramienta #1**. El 90% de tu trabajo empezará con una consulta SQL.

    !!! tip "📺 Video recomendado"
        ¿Prefieres una explicación en video? Mira este:
        [🔗 ¿Qué es SQL? 🤓](https://youtu.be/Atpj2UsF65M)

=== "🔬 ¿Cómo funciona?"

    SQL es un lenguaje **declarativo**. Eso significa que **tú dices QUÉ quieres**, no **CÓMO conseguirlo**.

    Imagina que vas a un restaurante:
    - **En un lenguaje imperativo (Python):** le explicas al chef cómo cortar las cebollas, cómo calentar la sartén, en qué orden...
    - **En SQL:** simplemente dices *"quiero una tortilla de patatas"* y el chef se encarga del resto.

    **Eso es SQL.** Tú describes lo que quieres, el motor de la base de datos decide cómo conseguirlo de la forma más eficiente.

    **SQL es un estándar** (ISO). Pero cada motor (MySQL, PostgreSQL, SQL Server, Oracle) tiene sus pequeñas variaciones. En este curso usamos **MySQL**, el más popular del mundo en proyectos web y análisis.

=== "📝 Vista previa (no te preocupes si no lo entiendes)"

    A modo de **adelanto**, así se ve una consulta SQL:

    ```sql
    SELECT nombre FROM clientes WHERE ciudad = 'Caracas';
    ```

    **No te preocupes si no entiendes esto aún.** Lo verás paso a paso en la Sección 1.

    Por ahora, quédate con la idea:
    - `SELECT` = "quiero ver..."
    - `FROM` = "...de la tabla..."
    - `WHERE` = "...donde se cumpla que..."

    Y con eso ya estarás consultando datos.

=== "💻 Ejemplo"

    Mira el **resultado** de una consulta (sin el código):

    **Pregunta:** "Dame el nombre de los clientes de Caracas."

    **Resultado:**

    ```
    nombre
    --------------------------
    Distribuidora El Sol
    Panadería La Espiga
    Ferretería Central
    Supermercado Don Pedro
    ```

    **¿Ves?** Solo ves la respuesta. No necesitas saber cómo el motor la obtuvo. Eso es lo que harás como analista: **hacer preguntas y obtener respuestas.**

    Más adelante aprenderás a hacerlo tú mismo.

=== "⚠️ Errores comunes"

    !!! warning "Confundir SQL con MySQL"
        **SQL** es el lenguaje. **MySQL** es un motor que lo implementa. Es como confundir "español" (idioma) con "España" (país).

    !!! warning "Pensar que SQL es solo para programadores"
        SQL lo usan analistas, contadores, gerentes, marketers. Es una habilidad **transversal**. Si trabajas con datos, necesitas SQL.

    !!! warning "Intentar aprender todo de golpe"
        SQL se aprende **por capas**. Primero `SELECT`, luego `WHERE`, luego `JOIN`, etc. **No intentes memorizar todo de una vez.** La comprensión llega con la práctica.

=== "🎯 Ejercicio"

    Reflexiona y responde:

    1. ¿Qué diferencias crees que hay entre SQL y un lenguaje como Python?
    2. ¿En qué situaciones crees que es mejor usar SQL que Excel?
    3. ¿Qué tipo de preguntas le harías a una base de datos de una tienda online?

    ??? success "Ver posible respuesta"
        1. SQL es **declarativo** (dices qué quieres), Python es **imperativo** (dices cómo hacerlo paso a paso). SQL es ideal para **consultar datos**, Python para **automatizar y transformar**.

        2. SQL es mejor cuando:
           - Hay **muchos datos** (millones de filas).
           - Necesitas **cruzar varias tablas**.
           - Los datos **cambian constantemente**.
           - Varias personas necesitan **acceder al mismo tiempo**.

        3. Preguntas típicas a una tienda online:
           - ¿Cuáles son los productos más vendidos?
           - ¿Qué clientes compran más seguido?
           - ¿Cuál es el ticket promedio por compra?
           - ¿Qué categorías generan más ingresos?

---

## 0.3 ¿Por qué aprender SQL?

=== "💡 ¿Qué es?"

    Aprender SQL **no es solo aprender un lenguaje**. Es aprender a **pensar en datos**.

    Hoy en día, **casi todo** se guarda en bases de datos:
    - Tu cuenta de banco.
    - Tu historial médico.
    - Tus compras online.
    - Tus redes sociales.
    - Los sistemas de tu empresa.

    Saber SQL te permite **entender y controlar** esa información.

    Y para un **analista de datos**, SQL no es opcional: es el **requisito #1** de cualquier oferta laboral.

=== "🔬 ¿Cómo funciona?"

    SQL es una de las habilidades **más demandadas y mejor pagadas** en tecnología y análisis de datos. Razones:

    1. **Universal:** se usa en todos los sectores (banca, salud, retail, educación, gobierno).
    2. **Atemporal:** lleva 50 años y sigue siendo el estándar. No va a desaparecer.
    3. **Fácil de aprender:** su sintaxis es muy cercana al inglés natural.
    4. **Combina con todo:** data science, business intelligence, desarrollo web, análisis financiero.
    5. **No requiere ser programador:** contadores, analistas, gerentes lo usan a diario.

    Según LinkedIn, SQL aparece en el **top 5 de habilidades más solicitadas** año tras año. Y en el mundo del **análisis de datos**, es **el requisito #1**.

=== "💻 Ejemplo"

    **Lo que podrás hacer al terminar este curso:**

    Imagina que eres analista de datos en una empresa. Tu gerente te pide:

    > "Necesito saber **cuáles fueron los 10 productos más vendidos en el último trimestre**, con su ingreso total."

    **Antes de este curso:** no sabrías por dónde empezar.
    **Después de este curso:** podrás obtener una tabla como esta en segundos:

    ```
    Producto               | Unidades vendidas | Ingreso total
    -----------------------|-------------------|---------------
    Aceite de girasol      | 12,450            | $124,500.00
    Harina de trigo        | 10,230            | $71,610.00
    Arroz blanco           | 9,870             | $59,220.00
    Azúcar refinada        | 8,540             | $42,700.00
    Leche en polvo         | 7,320             | $87,840.00
    ...
    ```

    **Eso es poder real con datos.** Y lo vas a aprender en este curso.

    No importa si hoy no sabes cómo se hace. **Paso a paso, lo lograrás.**

=== "⚠️ Errores comunes"

    !!! warning "Pensar que SQL es solo para programadores"
        SQL lo usan analistas, contadores, gerentes, marketers, médicos, científicos. Es una habilidad transversal. **Si trabajas con datos, necesitas SQL.**

    !!! warning "Creer que SQL es cosa del pasado"
        SQL nació en 1974 y sigue siendo el estándar. Nuevas herramientas (BigQuery, Snowflake, Databricks, Power BI) usan SQL como base.

    !!! warning "Aprender solo la sintaxis sin practicar"
        SQL se aprende **haciendo**. Leer sobre SQL no sirve. Hay que escribir consultas, equivocarse, corregir. Por eso este curso tiene ejercicios en cada tema.

    !!! warning "Saltarse la teoría para ir al código"
        Aunque parezca lento, entender **qué es una base de datos** y **cómo funciona SQL** te ahorrará horas de frustración más adelante. La teoría es la base de la práctica.

=== "🎯 Ejercicio"

    Reflexiona y responde en tu cuaderno (o mentalmente):

    1. ¿En qué áreas de tu vida laboral crees que SQL te podría ayudar?
    2. ¿Qué tipo de preguntas te gustaría poder responder con datos?
    3. ¿Qué expectativa tienes de este curso?

    No hay respuesta correcta o incorrecta. Es para que **tengas claro tu objetivo**. Eso te ayudará a mantenerte motivado.

    ??? success "Reflexión"
        Escribir tus objetivos **te ayuda a mantenerte enfocado**. Cuando llegues a temas difíciles (Window Functions, CTEs), recordar **por qué** estás aprendiendo SQL te dará fuerzas para seguir.

        Mi recomendación: **escribe tus 3 respuestas en un lugar visible**. Vuelve a ellas cada vez que te sientas perdido.

---

## 0.4 Alcance de aprender SQL

Antes de meterte de lleno, necesitas saber **qué vas a poder hacer** cuando termines esta Fase 1, y **qué no**. Esto evita frustraciones y expectativas equivocadas.

=== "🎯 ¿Qué podrás hacer?"

    Al terminar la Fase 1 serás capaz de:

    - **Consultar** cualquier base de datos relacional con confianza.
    - **Filtrar, ordenar y agrupar** datos para responder preguntas de negocio.
    - **Combinar tablas** (`JOIN`) para cruzar información de varias fuentes.
    - **Crear, modificar y eliminar** estructuras de datos (`CREATE`, `ALTER`, `DROP`).
    - **Diseñar** una base de datos pequeña desde cero (tu proyecto del curso).
    - **Optimizar** consultas básicas para que no se vuelvan lentas.
    - **Trabajar** con MySQL, y adaptarte a PostgreSQL, SQL Server o SQLite sin empezar de cero.

    !!! tip "Lo más importante"
        No vas a memorizar SQL. Vas a aprender a **pensar en datos**: qué pregunta quiero responder, qué tablas necesito, cómo las uno.

=== "🚫 ¿Qué NO cubre este curso?"

    Para que no te lleves una sorpresa, esto **no** lo verás en la Fase 1:

    - **Big Data** (millones de filas, Hadoop, Spark). Eso es otra liga.
    - **Administración avanzada** de servidores (replicación, backups, tuning profundo).
    - **PL/SQL, T-SQL** o procedimientos almacenados avanzados (se mencionan, no se profundiza).
    - **Python, R, Power BI o Tableau**. Eso viene en las siguientes fases del programa.
    - **ETL** y pipelines de datos. Fase posterior.

    !!! warning "Sé honesto contigo mismo"
        SQL es una herramienta, no una carrera completa. Si tu meta es ser **Analista de Datos**, SQL es la base, pero no el techo.

=== "📊 Niveles de dominio"

    Así se ve el camino típico de un analista con SQL:

    | Nivel | Qué sabes hacer | Tiempo (realista) | Tiempo (intensivo) |
    |---|---|---|---|
    | **Básico** | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT` | 3-4 semanas | 1-2 semanas |
    | **Intermedio** | `JOIN`, `GROUP BY`, subconsultas, funciones | 2-3 meses | 1 mes |
    | **Avanzado** | CTEs, window functions, optimización | 4-6 meses | 2-3 meses |
    | **Experto** | Modelado, tuning, arquitectura | 1+ año | 6+ meses |

    !!! info "¿Dónde vas a estar al terminar la Fase 1?"
        Entre **Básico sólido** e **Intermedio**. Es suficiente para aplicar a puestos junior de análisis de datos.

    !!! tip "¿Qué ritmo elegir?"
        - **Ritmo realista:** 1-2 horas al día, 5 días a la semana. Compatible con trabajo/estudios.
        - **Ritmo intensivo:** 3-4 horas al día, 6 días a la semana. Solo si tienes tiempo y quieres acelerar.

        No hay premio por ir rápido. **Lo importante es que entiendas, no que termines.**

=== "💼 Aplicación real"

    SQL no vive solo. Encaja en un ecosistema:

    ```
    SQL (extraer)  →  Python/R (analizar)  →  Power BI/Tableau (visualizar)
    ```

    - **SQL** responde *"¿qué pasó?"* (consultas, agregaciones).
    - **Python/R** responde *"¿por qué pasó?"* (estadística, modelos).
    - **Power BI/Tableau** responde *"¿cómo lo muestro?"* (dashboards).

    Aprender SQL primero tiene sentido: **es la puerta de entrada a los datos**. Sin datos, no hay análisis.

    !!! tip "Conexión con el proyecto del curso"
        En la sección **0.9** definirás el proyecto que construirás paso a paso: un sistema de ventas, facturación y cobranza. Ahí aplicarás todo lo que aprendas aquí.
---

## 0.5 Posibles trabajos al dominar SQL

Ahora que sabes **qué vas a poder hacer**, la pregunta natural es: *"¿y esto para qué me sirve laboralmente?"*.

La respuesta corta: **SQL abre puertas en casi cualquier área que toque datos**. La respuesta larga está en las pestañas.

=== "💼 Perfiles que usan SQL"

    SQL no es exclusivo de "analistas de datos". Lo usan a diario:

    | Perfil | Qué hace con SQL |
    |---|---|
    | **Analista de Datos** | Extrae, limpia y analiza datos para responder preguntas de negocio. |
    | **Analista BI** | Construye dashboards y reportes para la empresa. |
    | **Data Engineer** | Diseña y mantiene los pipelines que mueven los datos. |
    | **Científico de Datos** | Extrae datos para modelos estadísticos y de machine learning. |
    | **Analista de Marketing** | Mide campañas, segmenta clientes, calcula ROI. |
    | **Product Analyst** | Analiza el comportamiento de usuarios en un producto digital. |
    | **Analista Financiero** | Reportes, conciliaciones, proyecciones. |
    | **Analista de Operaciones** | Métricas de producción, logística, inventario. |
    | **QA / Soporte técnico** | Valida datos, diagnostica incidencias. |
    | **Gerentes y directores** | Toman decisiones basadas en datos que ellos mismos consultan. |

    !!! tip "Lo importante"
        No necesitas ser "analista de datos" para que SQL te sirva. Si tu trabajo **toca datos**, SQL te hace mejor en lo que ya haces.

=== "🌎 Mercado real (sin humo)"

    Aquí es donde muchos cursos mienten. Vamos con la verdad:

    - **SQL aparece en la mayoría de ofertas** de datos, BI, análisis y afines. Es **requisito**, no plus.
    - **No basta con SQL** para conseguir trabajo. Necesitas además: Excel, una herramienta de visualización (Power BI/Tableau), y saber contar una historia con datos. Python y R suman, pero no son obligatorios para empezar.
    - **El mercado hispanohablante es heterogéneo.** Lo que piden en España, México, Colombia, Argentina, Chile o Venezuela varía en herramientas, nivel y expectativas.
    - **El inglés suma mucho.** Muchas ofertas remotas bien pagadas están en inglés.
    - **La experiencia pesa más que los títulos.** Un portafolio con 3 proyectos reales vale más que 10 certificados.

    !!! warning "Sobre salarios"
        No vas a encontrar cifras en este curso. **Es a propósito.** Los salarios varían por país, industria, tamaño de empresa, nivel de inglés y experiencia. Cualquier número que veas en internet (incluidos otros cursos) es un promedio que probablemente no aplica a tu caso. **Investiga el mercado de tu país y tu sector** cuando estés listo para buscar trabajo.

    !!! tip "Dónde buscar ofertas (nombres, sin links)"
        - **LinkedIn** (el estándar global).
        - **Torre** e **Ideas en Red** (Latinoamérica).
        - **GetOnBoard** (tech, LATAM + remoto).
        - **RemoteOK** y **Wellfound** (remoto internacional).
        - **Ofertas de tu país** en portales locales de empleo.

        **Tip:** busca "analista de datos", "BI analyst", "data analyst" y lee **20 ofertas reales**. Anota qué piden. Eso te dirá exactamente qué aprender después de SQL.

=== "🎯 SQL como habilidad transversal"

    El mayor error al hablar de SQL es pensar que es **un destino**. No lo es. Es una **habilidad transversal** que se combina con lo que ya sabes:

    ```
    Tu área actual  +  SQL  =  Perfil potenciado
    ```

    Ejemplos concretos:

    - **Contador + SQL** → puede auditar y conciliar datos masivos sin depender de TI.
    - **Marketero + SQL** → segmenta clientes y mide campañas por sí mismo.
    - **Médico + SQL** → analiza historiales clínicos para investigación.
    - **Vendedor + SQL** → detecta patrones de compra y prioriza clientes.
    - **RRHH + SQL** → analiza rotación, desempeño y contratación.

    !!! tip "La regla de oro"
        **No compites contra analistas de datos. Compites contra personas de tu área que no saben SQL.** Esa es tu ventaja real.

=== "⚠️ Lo que NO te van a decir"

    Verdades incómodas que otros cursos omiten:

    !!! warning "SQL no te hace analista por sí solo"
        Saber `SELECT`, `JOIN` y `GROUP BY` es el **piso**, no el techo. Un analista completo también sabe Excel, visualización, estadística básica y comunicación.

    !!! warning "El primer trabajo es el más difícil"
        Vas a necesitar paciencia. Muchas ofertas piden 2-3 años de experiencia para puestos junior. **Contrarresta con portafolio, proyectos reales y networking.**

    !!! warning "Aprender SQL no garantiza trabajo remoto bien pagado"
        El trabajo remoto internacional existe, pero exige **inglés fluido**, **portfolio sólido** y muchas veces **zona horaria compatible**. No es para todos, y no llega el primer mes.

    !!! warning "La IA no reemplaza SQL (todavía)"
        Herramientas como ChatGPT escriben SQL, sí. Pero **alguien tiene que validar, adaptar y decidir**. Ese alguien es quien entiende SQL. La IA es una calculadora, no un analista.

    !!! danger "Desconfía de promesas mágicas"
        Si un curso, canal o influencer te promete **trabajo garantizado en 3 meses**, desconfía. El aprendizaje real toma tiempo, y el mercado laboral no funciona con garantías. **Este curso no te promete trabajo: te da las bases para que tú lo consigas.**

---

!!! tip "💡 Consejo antes de seguir"

    No te agobies con la cantidad de temas. El curso está diseñado para ir **paso a paso**. Si algo no queda claro, sigue adelante y vuelve después. La comprensión llega con la práctica, no con la repetición teórica.

    **Recuerda:** el 90% de tu trabajo como analista será **hacer preguntas a los datos**. SQL es el idioma para hacerlo. Ahora mismo estás aprendiendo el idioma, no las frases.

---

## 0.6a Instalación de MySQL 8.4 LTS

Antes de empezar a consultar datos, necesitas tener MySQL instalado en tu equipo. En este tema lo instalamos **paso a paso**, según tu sistema operativo.

!!! info "📌 Nota"
    Aquí verás algunos comandos técnicos. No te preocupes si no entiendes la sintaxis aún — la verás en detalle a partir de la **Sección 1**. Por ahora solo necesitas **ejecutarlos** para verificar que todo funciona.

---

=== "💡 ¿Qué es MySQL?"

    **MySQL** es un **motor de bases de datos relacionales**. Es el software que almacena los datos, los organiza en tablas y responde a las consultas que le hagamos con SQL.

    Piensa en MySQL como el **motor de un coche**. Tú no ves el motor, pero sin él el coche no se mueve. Con MySQL pasa lo mismo: tú escribes SQL, y MySQL se encarga de buscar, ordenar y devolver los datos.

    ### ¿Por qué MySQL en este curso?

    - ✅ **Gratuito y open source.** No pagas licencia.
    - ✅ **El más usado del mundo** en proyectos web y análisis de datos.
    - ✅ **Fácil de instalar** en Windows, macOS y Linux.
    - ✅ **Compatible con casi todas las herramientas** de análisis (Python, Power BI, Tableau, etc.).
    - ✅ **Documentación abundante** y comunidad enorme.

    ### ¿Y las alternativas?

    | Motor | Uso principal | ¿Por qué no en este curso? |
    |---|---|---|
    | **MySQL** | Web, análisis, aplicaciones | ✅ Es el elegido |
    | **PostgreSQL** | Análisis avanzado, GIS | Más complejo para empezar |
    | **SQL Server** | Empresas (Microsoft) | De pago, atado a Windows |
    | **SQLite** | Apps móviles, prototipos | Sin servidor, limitado |
    | **Oracle** | Banca, grandes empresas | Caro, complejo |

    **MySQL es el mejor punto de partida.** Una vez lo domines, migrar a otro motor es cuestión de días.

    ### Versión: MySQL 8.4 LTS

    Vamos a usar **MySQL 8.4 LTS** (Long-Term Support).

    - **LTS** significa **soporte a largo plazo**: recibirá actualizaciones de seguridad hasta **2032**.
    - Es la versión **recomendada para producción** y para aprender.
    - La versión 9.x (Innovation) cambia cada pocos meses y **puede romper compatibilidad**. No la usaremos.

    ### Componentes que instalaremos

    - **MySQL Server** → el motor (obligatorio).
    - **MySQL Workbench** → interfaz gráfica para gestionar la BD (recomendado).
    - **MySQL Shell** → terminal avanzada (opcional).

    Con **Server + Workbench** tienes todo lo necesario para el curso.

=== "🪟 Instalación en Windows"

    ### Paso 1 — Descargar el instalador

    1. Ve a: [https://dev.mysql.com/downloads/installer/](https://dev.mysql.com/downloads/installer/)
    2. Descarga **MySQL Installer for Windows** (versión **8.4 LTS**, archivo `mysql-installer-community-8.4.x.msi`).
    3. Tamaño: ~450 MB. Elige la opción **"Windows (x86, 32-bit), MSI Installer"** o **"Windows (x86, 64-bit)"** según tu sistema.

    !!! tip "💡 ¿32 o 64 bits?"
        Casi todos los PCs modernos son **64 bits**. Si tienes dudas, pulsa `Windows + Pausa` y mira "Tipo de sistema".

    ### Paso 2 — Ejecutar el instalador

    1. Doble clic en el archivo `.msi` descargado.
    2. Si Windows pide permisos de administrador, acepta.
    3. En la pantalla **"Choosing a Setup Type"**, selecciona:
       - ✅ **Developer Default** (instala Server + Workbench + Shell + connectors).
    4. Clic en **Next**.

    ### Paso 3 — Instalar dependencias

    El instalador puede pedir instalar **Visual C++ Redistributable** y **Python**. Acepta todo lo que pida.

    ### Paso 4 — Configurar MySQL Server

    1. En **"Type and Networking"**:
       - **Config Type:** Development Computer.
       - **Port:** `3306` (el estándar).
       - **X Protocol Port:** `33060` (déjalo como está).
    2. En **"Authentication Method"**:
       - ✅ Selecciona **"Use Strong Password Encryption"** (recomendado).
    3. En **"Accounts and Roles"**:
       - **Root Password:** elige una contraseña **segura** (mínimo 8 caracteres, mayúscula, minúscula, número y símbolo).
       - **⚠️ Anótala en un lugar seguro.** La necesitarás más adelante.
    4. En **"Windows Service"**:
       - ✅ **Configure MySQL Server as a Windows Service.**
       - ✅ **Start the MySQL Server at System Startup.**
       - **Service Name:** `MySQL84` (déjalo por defecto).
    5. Clic en **Next** → **Execute** → espera a que termine.

    ### Paso 5 — Finalizar

    1. El instalador aplicará la configuración.
    2. Clic en **Finish**.
    3. Se abrirá **MySQL Workbench** automáticamente. Ciérralo por ahora (lo usaremos después).

    ### Paso 6 — Verificar que el servicio está corriendo

    1. Pulsa `Windows + R`, escribe `services.msc` y Enter.
    2. Busca **"MySQL84"** en la lista.
    3. Debe estar **"Running"** (En ejecución).

    ✅ **MySQL Server está instalado y funcionando.**

    !!! tip "📺 Video recomendado"
        Si prefieres seguir la instalación en video, mira este tutorial:
        [🔗 Instalación de MySQL en Windows](https://www.youtube.com/watch?v=nv9GCue0YwM)

=== "🍎 Instalación en macOS"

    ### Opción A — Homebrew (recomendado)

    **Requisito previo:** tener **Homebrew** instalado. Si no lo tienes, abre Terminal y ejecuta:

    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

    **Instalar MySQL 8.4:**

    ```bash
    brew install mysql@8.4
    ```

    **Iniciar el servicio:**

    ```bash
    brew services start mysql@8.4
    ```

    **Asegurar la instalación:**

    ```bash
    mysql_secure_installation
    ```

    Te pedirá:
    - Establecer contraseña de root (elige una **segura** y anótala).
    - Eliminar usuarios anónimos (Sí).
    - Deshabilitar login remoto de root (Sí).
    - Eliminar base de datos de prueba (Sí).
    - Recargar privilegios (Sí).

    ### Opción B — DMG oficial

    1. Ve a: [https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/)
    2. Descarga el **DMG** para macOS (versión **8.4 LTS**).
    3. Abre el DMG y ejecuta el instalador `.pkg`.
    4. Sigue los pasos (contraseña root, configuración, etc.).
    5. Al final, el instalador te dará una **contraseña temporal** de root. **Anótala** y cámbiala después.

    ### Instalar MySQL Workbench

    1. Ve a: [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)
    2. Descarga el DMG para macOS.
    3. Arrastra MySQL Workbench a la carpeta **Aplicaciones**.

    ✅ **MySQL Server + Workbench instalados.**

    !!! tip "📺 Video recomendado"
        Si prefieres seguir la instalación en video, mira este tutorial:
        [🔗 Instalación de MySQL Workbench en macOS](https://www.youtube.com/watch?v=npt01LZMCVc)

=== "🐧 Instalación en Linux"

    ### Ubuntu / Debian

    **Paso 1 — Actualizar repositorios:**

    ```bash
    sudo apt update
    ```

    **Paso 2 — Instalar MySQL Server:**

    ```bash
    sudo apt install mysql-server
    ```

    **Paso 3 — Iniciar el servicio:**

    ```bash
    sudo systemctl start mysql
    sudo systemctl enable mysql
    ```

    **Paso 4 — Asegurar la instalación:**

    ```bash
    sudo mysql_secure_installation
    ```

    Te pedirá:
    - Configurar validación de contraseñas (elige "Y" y nivel 1 o 2).
    - Establecer contraseña de root (elige una **segura** y anótala).
    - Eliminar usuarios anónimos (Sí).
    - Deshabilitar login remoto de root (Sí).
    - Eliminar base de datos de prueba (Sí).
    - Recargar privilegios (Sí).

    ### Fedora / RHEL / CentOS

    ```bash
    sudo dnf install mysql-server
    sudo systemctl start mysqld
    sudo systemctl enable mysqld
    sudo mysql_secure_installation
    ```

    ### Instalar MySQL Workbench (opcional)

    ```bash
    sudo apt install mysql-workbench
    ```

    En Fedora:

    ```bash
    sudo dnf install mysql-workbench
    ```

    ✅ **MySQL Server instalado.**

    !!! tip "📺 Video recomendado"
        Si prefieres seguir la instalación en video, mira este tutorial:
        [🔗 Instalación de MySQL/MariaDB en Linux](https://www.youtube.com/watch?v=aI9ETqjqyVo)

=== "🔧 Verificar instalación"

    ### 1. Verificar que MySQL está instalado

    Abre una terminal (CMD en Windows, Terminal en macOS/Linux) y ejecuta:

    ```bash
    mysql --version
    ```

    Deberías ver algo como:

    ```
    mysql  Ver 8.4.x for Win64 on x86_64 (MySQL Community Server - GPL)
    ```

    ✅ Si ves la versión 8.4.x → **MySQL está instalado.**

    ### 2. Conectar al servidor

    ```bash
    mysql -u root -p
    ```

    Te pedirá la **contraseña de root** (la que pusiste durante la instalación).

    Si todo va bien, verás el prompt de MySQL:

    ```
    mysql>
    ```

    ### 3. Confirmar la versión dentro de MySQL

    ```sql
    SELECT VERSION();
    ```

    Resultado esperado:

    ```
    +-----------+
    | VERSION() |
    +-----------+
    | 8.4.x     |
    +-----------+
    ```

    ### 4. Salir de MySQL

    ```sql
    EXIT;
    ```

    ### 5. Abrir MySQL Workbench

    1. Abre **MySQL Workbench** desde el menú de aplicaciones.
    2. Verás una pantalla con **"MySQL Connections"**.
    3. Haz clic en **"+"** para crear una nueva conexión.
    4. Rellena:
       - **Connection Name:** `Local - MySQL 8.4`
       - **Hostname:** `127.0.0.1`
       - **Port:** `3306`
       - **Username:** `root`
    5. Clic en **"Test Connection"** → te pedirá la contraseña → guarda la contraseña.
    6. Si dice **"Successfully made the MySQL connection"** → ✅ **todo funciona.**

    !!! info "📌 Nota"
        Estos comandos son solo para verificar que MySQL está funcionando. 
        No te preocupes si no entiendes la sintaxis SQL aún — la verás en detalle 
        a partir de la **Sección 1**.

=== "⚠️ Errores comunes"

    !!! warning "`mysql` no se reconoce como comando"

        **Causa:** MySQL no está en el PATH de Windows.

        **Solución:**
        1. Busca "Variables de entorno" en el menú Inicio.
        2. En "Variables del sistema", busca `Path` → Editar → Nuevo.
        3. Añade: `C:\Program Files\MySQL\MySQL Server 8.4\bin`
        4. Acepta y **cierra la terminal**. Abre una nueva.
        5. Prueba `mysql --version` de nuevo.

    !!! warning "Access denied for user 'root'@'localhost'"

        **Causa:** contraseña incorrecta u olvidada.

        **Solución (Windows):**
        1. Detén el servicio MySQL desde `services.msc`.
        2. Abre CMD como administrador y ejecuta:
           ```bash
           mysqld --skip-grant-tables
           ```
        3. En otra terminal: `mysql -u root`
        4. Ejecuta:
           ```sql
           ALTER USER 'root'@'localhost' IDENTIFIED BY 'NuevaPasswordSegura';
           FLUSH PRIVILEGES;
           ```
        5. Cierra todo, reinicia el servicio desde `services.msc`.

    !!! warning "Port 3306 already in use"

        **Causa:** otro programa está usando el puerto 3306 (otro MySQL, MariaDB, etc.).

        **Solución:**
        1. Abre CMD como admin:
           ```bash
           netstat -ano | findstr :3306
           ```
        2. Verás el PID del proceso que lo usa.
        3. Mátalo:
           ```bash
           taskkill /PID <numero_pid> /F
           ```
        4. Reinicia el servicio MySQL.

    !!! warning "El servicio MySQL no inicia"

        **Causas posibles:**
        - Falta de permisos.
        - Archivos corruptos de la instalación.
        - Antivirus bloqueando.

        **Solución:**
        1. Abre `services.msc`, busca `MySQL84`, clic derecho → **Reiniciar**.
        2. Si falla, revisa el log de errores en:
           `C:\ProgramData\MySQL\MySQL Server 8.4\Data\*.err`
        3. Como último recurso, **reinstala MySQL** desde el instalador.

    !!! warning "No puedo instalar Workbench en Linux"

        **Causa:** Workbench no siempre está en los repositorios.

        **Solución:**
        - Descarga el `.deb` oficial desde:
          [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)
        - O usa **DBeaver** como alternativa (gratis, compatible con MySQL).

---

!!! tip "💡 Consejo antes de seguir"

    Si llegaste hasta aquí y `mysql --version` te devuelve la versión 8.4, **ya tienes MySQL instalado y funcionando.** 🎉

    En el siguiente tema (**0.6b**) vamos a **configurarlo para el curso**: crear un usuario dedicado, crear la base de datos del proyecto y cargar los datos de práctica (`world` y `employees`).

    **No avances hasta que MySQL funcione.** Si tienes problemas, revisa los errores comunes o pide ayuda.

---