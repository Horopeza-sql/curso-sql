# ¿Qué es SQL?

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

    <!-- VIDEO PENDIENTE: buscar video en YouTube sobre "¿Qué es SQL?" -->

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

    **No te preocupes si no entiendes esto aún.** Lo verás paso a paso en la sección de **Consultas Esenciales**.

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
