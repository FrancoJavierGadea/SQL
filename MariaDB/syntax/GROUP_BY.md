## GROUP BY

Nos permite **agrupar las filas** segun una **propiedad**

para luego realizar **operaciones sobre los grupos** con `Aggregate Functions`


### Aggregate Functions

- `COUNT`

    Contar la cantidad de elementos por cada grupo

    ```sql
    SELECT club, COUNT(id) AS `count`
    FROM futbol_argentino
    GROUP BY club;
    ```
<br>

- `GROUP_CONCAT`

    ```sql
    GROUP_CONCAT(
        property    
        ORDER BY property ASC
        SEPARATOR ','
        LIMIT 10 OFFSET 2
    )
    ```

    ```sql
    SELECT debut_club, 
        GROUP_CONCAT(
            CONCAT(first_name, ' ',last_name) 
            ORDER BY first_name ASC
            SEPARATOR ',\n'
            LIMIT 10 OFFSET 0
        ) AS `names`
    FROM futbol_argentino
    GROUP BY debut_club;
    ```

    Podmemos 
    
    - Ordenar con `ORDER BY` y `ASC` `DESC`
    - Indicar el separador, por ejemplo `SEPARATOR '-'`
    - Limitar la cantidad de resultados con `LIMIT n` y `OFFSET m`

<br>

- `JSON_ARRAYAGG`

    Retora un `string json array` con los elementos de cada grupo 
    
    ejemplo: `["value_1", "value_2", "value_3", "value_3"]`

    ```sql
    JSON_ARRAYAGG(
        property    
        ORDER BY property ASC
        LIMIT 10 OFFSET 2
    )
    ```

    Ademas podemos 
    
    - Ordenar con `ORDER BY` y `ASC` `DESC`
    - Limitar la cantidad de resultados con `LIMIT n` y `OFFSET m`

    <br>

    ```sql
    SELECT club, 
        JSON_ARRAYAGG(
            CONCAT(first_name, ' ',last_name) 
            ORDER BY first_name ASC
            LIMIT 2 OFFSET 0
        ) AS `json names`
    FROM futbol_argentino
    GROUP BY club;
    ```

<br>

- `JSON_OBJECTAGG`

    ```sql
    JSON_OBJECTAGG(expr_key, expr_value)
    ```

    ```sql
    SELECT club, 
        JSON_OBJECTAGG(
            id,
            CONCAT(first_name, ' ',last_name)  
        ) AS `object names`
    FROM futbol_argentino
    GROUP BY club;
    ```

<br>

- `MIN` `MAX` y `AVG`

    Nos permiten encontrar el valor **minimo**, **maximo** y **promedio** de cada grupo

    ```sql
    SELECT debut_club, 
        MIN(debut_age) AS `min debut age`,
        MAX(debut_age) AS `max debut age`,
        AVG(debut_age) AS `average debut age`
    FROM futbol_argentino
    GROUP BY debut_club;
    ```

<br><br>

#### Docs

- [aggregate-functions](https://mariadb.com/kb/en/aggregate-functions/)
- [group_concat](https://mariadb.com/kb/en/group_concat/)
- [json_arrayagg](https://mariadb.com/kb/en/json_arrayagg/)
- [json_objectagg](https://mariadb.com/kb/en/json_objectagg/)
- [](https://mariadb.com/kb/en/min/)
- [](https://mariadb.com/kb/en/max/)
- [](https://mariadb.com/kb/en/avg/)