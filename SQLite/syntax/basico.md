### Crear una Tabla

#### PRYMARY KEY

El **campo** o **conjuntos de campos** que `identifica de manera unica` a cada `fila` de la **tabla**

- Tiene que ser `unico` para cada `fila`

- No puede ser `NULL`

- Tiene que ser `inmutable`, no puede cambiarse una vez que se ha establecido

<br>

Ejemplos:

- `PRIMARY KEY` simple, formada por 1 campo o columna
  
    ```sql
    CREATE TABLE table_name (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        c1 TEXT,
        c2 REAL
    );
    ```

    ```sql
    CREATE TABLE table_name (
        id INTEGER,
        c1 TEXT,
        c2 REAL,

        PRIMARY KEY(id) 
    );
    ```

- `PRIMARY KEY` compuesta, formada por 2 o mas columnas
  
    ```sql
    CREATE TABLE table_name (
        id INTEGER,
        uuid TEXT,
        c2 REAL,

        PRIMARY KEY(id, uuid) 
    );
    ```