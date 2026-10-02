# ¿Qué es una base de datos?

=== "💡 ¿Qué es?"

    Una **base de datos** es un lugar donde guardamos información de forma **organizada** para poder encontrarla, actualizarla y relacionarla fácilmente.

    Piensa en una **agenda de contactos**. Tienes nombres, teléfonos, correos. Si buscas "Juan", lo encuentras rápido porque están ordenados. Eso, llevado a un sistema informático, es una base de datos.

    Ejemplos cotidianos:
    - 📱 Los contactos de tu teléfono.
    - 🏦 Los movimientos de tu cuenta bancaria.
    - 🛒 Los productos de una tienda online.
    - 📊 Los KPIs de una empresa (ventas, clientes, márgenes).

    Como **analista de datos**, tu trabajo consistirá en **hacer preguntas** a esas bases de datos y obtener respuestas útiles para el negocio.

    <!-- VIDEO PENDIENTE: buscar video en YouTube sobre "¿Qué es una base de datos?" -->

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