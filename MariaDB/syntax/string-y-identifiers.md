# `String literal` vs `String Identifier`

En `MariaDB` por defecto usamos

- #### Comillas simples `'literal string'` y Comillas dobles `"literal string"`

    Para las cadenas de texto, cualquier valor de texto que deseas **insertar** o **comparar**

    ```sql
    -- Insertar un valor de texto
    INSERT INTO empleados (nombre) VALUES ('Juan Pérez');

    -- Comparar un valor de texto
    SELECT * FROM empleados WHERE nombre = "Juan Pérez";
    ```

<br>

- #### Backticks: `` `identifier string` ``

    Para definir **identificadores**, como nombres de **tablas**, **columnas**, o **cualquier objeto de la base de datos**

    ```sql
    -- Crear una tabla
    CREATE TABLE `Mis Empleados` (`ID Empleado` INT PRIMARY KEY AUTOINCREMENT, `Nombre Completo` TEXT);

    -- Insertar datos
    INSERT INTO `Mis Empleados` (`Nombre Completo`) VALUES ('Indiana Jones');

    -- Seleccionar datos de una tabla
    SELECT `Nombre Completo` FROM `Mis Empleados` WHERE `ID Empleado` = 1;
    ```

<br>


### SQL_MODE

Si establecemos la `varible del servidor`: `SQL_MODE` con `ANSI_QUOTES`

o algun otro valor que contenga `ANSI_QUOTES`

```text
ANSI DB2 MAXDB MSSQL ORACLE POSTGRESQL
```

Cambiamos el comportamiento de las comillas dobles `""`

Para que se interprenten como `identificadores` en vez de `string literals`

```sql
CREATE TABLE "SELECT" (i int);
> ERROR 1064 (42000): You have an error in your SQL syntax; 
  check the manual that corresponds to your MariaDB server version for the right syntax 
  to use near '"SELECT" (i int)' at line 1

SET sql_mode='ANSI_QUOTES';
> Query OK, 0 rows affected (0.03 sec)

CREATE TABLE "SELECT" (i int);
> Query OK, 0 rows affected (0.46 sec)
```

<br><br>

#### Docs

- [](https://mariadb.com/kb/en/string-literals/)
- [](https://mariadb.com/kb/en/identifier-names/)
- [](https://mariadb.com/kb/en/sql-mode/)