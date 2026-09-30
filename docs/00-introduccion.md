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

!!! tip "💡 Consejo antes de seguir"

    No te agobies con la cantidad de temas. El curso está diseñado para ir **paso a paso**. Si algo no queda claro, sigue adelante y vuelve después. La comprensión llega con la práctica, no con la repetición teórica.

    **Recuerda:** el 90% de tu trabajo como analista será **hacer preguntas a los datos**. SQL es el idioma para hacerlo. Ahora mismo estás aprendiendo el idioma, no las frases.

---