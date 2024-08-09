# AUTOINCREMENT y PRIMARY KEY

- `INTEGER PRIMARY KEY`
  
    ```sql
    CREATE TABLE (
        id INTEGER PRIMARY KEY, 
        word TEXT
    );
    ```

    Cuando creamos una **tabla** cuyo campo principal es: `INTEGER PRIMARY KEY`

    Cada vez que hagamos un `INSERT` si **no le damos un valor explitico** al campo

    `SQLite` le **asignara un valor** tomando el **valor mas grande** de la columna y incrementandolo en $1$

<br>

- `INTEGER PRIMARY KEY AUTOINCREMENT`

     ```sql
    CREATE TABLE (
        id INTEGER PRIMARY KEY AUTOINCREMENT, 
        word TEXT
    );
    ```

    `AUTOINCREMENT` modificara el **algoritmo de asignacion automatica** haciendo que **no se usen valores previamente utilizados** en `filas` que fueron **eliminadas**

    Con `AUTOINCREMENT` se garantiza que las `filas` que se **insertan** tengan `ROWID` generados automaticamente que:
    
    - Nunca hayan sido utilizados antes en la `tabla`

    - Aumenten de forma monotona: $1, 2, 3, 4, 5, \cdots$

    Obteniendo el mismo comportamiento que en otras **base de datos SQL**

    Pero consumiendo mas **recursos**
<br>

<br>

### AUTOINCREMENT

`AUTOINCREMENT` solo puede aplicarse a una columna que sea `INTEGER PRIMARY KEY`

- No puede aplicarse a otras columnas 

    ```sql
    -- Esto da error de syntaxis:
    CREATE TABLE table_name3 (
        id INTEGER PRIMARY KEY,
        c1 TEXT,
        c2 INTEGER AUTOINCREMENT,
    );

    > Error while executing SQL query on database 'DB': near "AUTOINCREMENT": syntax error
    ```

- No puede aplicarse en una `PRIMARY KEY` compuesta

    
    ```sql
    -- Esto da error de syntaxis:
    CREATE TABLE table_name (
        id INTEGER AUTOINCREMENT,
        uuid TEXT,
        c2 INTEGER,

        PRIMARY KEY(id, uuid) 
    );

    > Error while executing SQL query on database 'DB': near "AUTOINCREMENT": syntax error
    ```

    ```sql
    -- Esto funciona
    CREATE TABLE table_name (
        id INTEGER,
        uuid TEXT,
        c2 INTEGER,

        PRIMARY KEY(id, uuid) 
    );
    ```
<br>

#### Docs

- [SQLite AUTOINCREMENT](https://www.sqlite.org/autoinc.html)