# Instalación de MySQL 8.4 LTS

Antes de empezar a consultar datos, necesitas tener MySQL instalado en tu equipo. En este tema lo instalamos **paso a paso**, según tu sistema operativo.

!!! info "📌 Nota"
    Aquí verás algunos comandos técnicos. No te preocupes si no entiendes la sintaxis aún — la verás en detalle a partir de la sección de **Consultas Esenciales**. Por ahora solo necesitas **ejecutarlos** para verificar que todo funciona.

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

    <!-- VIDEO PENDIENTE: buscar video en YouTube sobre "Instalación de MySQL en Windows" -->

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

    <!-- VIDEO PENDIENTE: buscar video en YouTube sobre "Instalación de MySQL en macOS" -->

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

    <!-- VIDEO PENDIENTE: buscar video en YouTube sobre "Instalación de MySQL en Linux" -->

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
        a partir de la sección de **Consultas Esenciales**.

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

    En el siguiente tema vamos a **configurarlo para el curso**: crear un usuario dedicado, crear la base de datos del proyecto y cargar los datos de práctica (`world` y `employees`).

    **No avances hasta que MySQL funcione.** Si tienes problemas, revisa los errores comunes o pide ayuda.