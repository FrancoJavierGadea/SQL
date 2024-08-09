

```sql
-- Seleccionar los campos c1, c2, c3 
SELECT c1, c2, c3 FROM table_name;

-- Seleccionar todos los campos
SELECT * FROM table_name;
```

### `WHERE`

```sql
SELECT * FROM table_name WHERE /*...conditions...*/;
```
Nos permite filtrar los resultados, mostrando unicamente los cumplan unas condiciones

Operadores:

- `=`: igual que
- `!=`: distinto que
- `<`: menor que
- `>`: mayor que
- `<=`: menor o igual que
- `>=`: mayor o igual que
  
- `NOT` `!`: 'no' logico
- `AND` `&&`: 'y' logico
- `OR` `||`: 'o' logico
- `XOR`: 'o' logico excluyente

- `IN` `NOT IN`
 
    ```sql
    -- El campo `c1` es igual a alguno de los valores: v1, v2, v3, ... 
    c1 IN (v1, v2, v3, ...)

    -- El campo `c1` no es igual a alguno de los valores: v1, v2, v3, ... 
    NOT c1 IN (v1, v2, v3, ...)

    -- El campo `c1` no es igual a alguno de los valores: v1, v2, v3, ... 
    c1 NOT IN (v1, v2, v3, ...)
    ```

- `BETWEEN AND`

    ```sql
    c1 BETWEEN min AND max

    c1 >= min AND c1 <= max
    ```

Ejemplos:

```sql
SELECT * FROM players 
WHERE age > 30 AND shirt_number = 10;

SELECT * FROM players 
WHERE shirt_number = 10 OR shirt_number = 9;

SELECT * FROM players 
WHERE shirt_number IN (11, 10, 9);


SELECT * FROM players 
WHERE age <= 25 AND age <= 30;

SELECT * FROM players 
WHERE age BETWEEN 25 AND 30;
```


<br>

### `LIMIT` y `OFFSET`

- `LIMIT` Nos permite limitar la cantidad de resultados, el numero de `filas` que se devuelven

- `OFFSET` Indica cuántas `filas` **omitir** antes de empezar a devolver los resultados 

```sql
-- Selecciona n filas a partir de la fila m 
SELECT * FROM table_name LIMIT n OFFSET m;
```

Ejemplo de **Paginacion de resultados**

```sql
-- n es la cantidad de filas por pagina
-- i es el numero de pagina: i = 1, 2, 3, 4, ...

SELECT * FROM table_name LIMIT n OFFSET (i - 1) * n;

-- Por ejemplo: Pagina 3, 10 resultados por pagina
-- (3 - 1) * 10 = 20
SELECT * FROM table_name LIMIT 10 OFFSET 20;
```

- [](https://mariadb.com/kb/en/operators/)
- [](https://mariadb.com/kb/en/between-and/)
- [](https://mariadb.com/kb/en/in/)
- [](https://mariadb.com/kb/en/not-in/)
- []()
- []()
- []()
- []()
- []()
- []()