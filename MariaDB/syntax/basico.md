# Tablas


### CONSTRAINTS / Restricciones para las columnas

- `NOT NULL`

    Los valores en la `columna` no pueden ser **nulos**

    ```sql
    CREATE TABLE table_name (
        c1 TEXT(50) NOT NULL
    );
    ```

- `UNIQUE`

    Los valores en la `columna` deber ser **unicos** en toda la `tabla`

    ```sql
    CREATE TABLE table_name (
        c1 INTEGER UNIQUE
    );
    ```

- `DEFAULT`

    Los valores en la `columna` tienen el **valor por defecto** indicado

    ```sql
    CREATE TABLE table_name (
        c1 VARCHAR(50) DEFAULT 'XXX XXX-XXXX'
    );
    ```

- `CHECK`

    Los valores en la columna tiene que cumplir la **condicion** indicada

    ```sql
    CREATE TABLE table_name (
        c1 REAL CHECK (c1 >= 10)
    );
    ``` 

- `PRIMARY KEY`

    Implica `NOT NULL` y `UNIQUE`

- `FOREIGN KEY`

## Crear una Tabla

####  PRYMARY KEY

El **campo** o **conjuntos de campos** que `identifica de manera unica` a cada `fila` de la **tabla**

- Tiene que ser `unico` para cada `fila`

- No puede ser `NULL`

- Tiene que ser `inmutable`, no puede cambiarse una vez que se ha establecido

<br>

Ejemplos:

- `PRIMARY KEY` simple, formada por 1 campo o columna
  
    ```sql
    CREATE TABLE table_name (
        id INTEGER PRIMARY KEY AUTO_INCREMENT,
        c1 VARCHAR(50),
        c2 TINYINT(2)
    );
    ```

    ```sql
    CREATE TABLE table_name (
        id INTEGER AUTO_INCREMENT,
        c1 VARCHAR(50),
        c2 TINYINT(2),

        PRIMARY KEY(id) 
    );
    ```

- `PRIMARY KEY` compuesta, formada por 2 o mas columnas
  
    ```sql
    CREATE TABLE table_name (
        id INTEGER AUTO_INCREMENT,
        uuid VARCHAR(50),
        c2 TINYINT(2),

        PRIMARY KEY(id, uuid) 
    );
    ```



  
```sql
-- Crear una tabla solo si no existe ya
CREATE TABLE IF NOT EXISTS table_name (
    /*...table columns...*/
);

-- Crear una tabla en otra base de datos
CREATE TABLE db_name.table_name (
    /*...table columns...*/s
);
```



<br>

### Borrar una Tabla

```sql
-- Borrar tabla
DROP TABLE table_name;

-- Borrar tabla en otra base de datos
DROP TABLE db_name.table_name;

-- Borrar tabla solo si existe
DROP TABLE IF EXISTS table_name;
```

<br>

### Ver la estructura de la Tabla

```sql
-- Ver los tipos y restricciones de cada columna
> DESCRIBE table_name;

-- Ver los tipos y restricciones de cada columna
> SHOW COLUMNS FROM table_name;

-- Ver el comando SQL con el que se contruyo la tabla
> SHOW CREATE TABLE table_name;
```

<br>

### Modificar una tabla

```sql

```