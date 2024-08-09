# `String literal` vs `String Identifier`

En `SQLite` usamos 

- #### Comillas simples: `'literal string'`

    Para las cadenas de texto, cualquier valor de texto que deseas **insertar** o **comparar**

    ```sql
    -- Insertar un valor de texto
    INSERT INTO empleados (nombre) VALUES ('Juan Pérez');

    -- Comparar un valor de texto
    SELECT * FROM empleados WHERE nombre = 'Juan Pérez';
    ```

<br>

- #### Comillas dobles: `"identifier string"`

    Para definir **identificadores**, como nombres de **tablas**, **columnas**, o **cualquier objeto de la base de datos**

    ```sql
    -- Crear una tabla
    CREATE TABLE "Mis Empleados" ("ID Empleado" INTEGER PRIMARY KEY, "Nombre Completo" TEXT);

    -- Insertar datos
    INSERT INTO "Mis Empleados" ("Nombre Completo") VALUES ('Indiana Jones');

    -- Seleccionar datos de una tabla
    SELECT "Nombre Completo" FROM "Mis Empleados" WHERE "ID Empleado" = 1;
    ```

<br>


### Otra forma de usar identificadores

Tambien podemos usar para los **indentificadores**

- #### Backticks: `` `identifier string` ``

    ```sql
    SELECT `Nombre Completo` FROM `Mis Empleados` WHERE `ID Empleado` = 2;
    ```
    Porque es compatible con `MySQL`

<br>

- #### Corchetes: `[identifier string]`

    ```sql
    SELECT [Nombre Completo] FROM [Mis Empleados] WHERE [ID Empleado] = 1;
    ```
    Porque es compatible con `SQL Server` y `MS Access`

<br>


#### Docs

- [SQLite Keywords](https://www.sqlite.org/lang_keywords.html)