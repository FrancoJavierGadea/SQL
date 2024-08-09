# Tipos de datos Numericos

- `TINYINT` `INT1`
- `SMALLINT` `INT2`
- `MEDIUMINT` `INT3`
- `INT` `INTEGER` `INT4`
- `BIGINT` `INT8`
- `DECIMAL`
- `FLOAT`
- `DOUBLE` `REAL`
- `BIT`

<br>

#### Indicar la cantidad de digitos

- **Enteros**
  
    ```sql
    INT(n)  INTEGER(n)  TINYINT(n)
    ```
    > $n$ es la `longitud`, cantidad de digitos del numero

- **Decimales**

    ```sql
    FLOAT(n,d)  REAL(n,d)  DOUBLE(n,d)
    ```
    > $n$ es la cantidad de digitos antes de la coma
    > <br>
    > $d$ es la cantidad de digitos despues de la coma    



Por ejemplo:

```sql
> CREATE TABLE table1 (n1 INT(2), n2 SMALLINT(3), n3 REAL(3,2)); 
```

<br>


### `SIGNED` vs `UNSIGNED`

- `SIGNED` es un **numero entero con signo**

    Su rango es de:
    $$
    \text{Min}: -2^{n-1}
    \hspace{3em}
    \text{Max}: 2^{n-1}-1
    $$
    $n$ es el tamaño en `bits`

<br>

- `UNSIGNED` es un **numero entero sin signo**

    Su rango es de:
    $$
    \text{Min}: 0
    \hspace{3em}
    \text{Max}: 2^{n}-1
    $$
    $n$ es el tamaño en `bits`


<br>

> Por defecto son siempre: `SIGNED`

<br>

### ZEROFILL

Es una **feature** exclusiva de `MariaDB`

Funciona unicamente para los valores numericos `UNSIGNED`

Completa con $0$ a la izquierda los valores numericos

```sql
-- INT(4)
1  18  103
-- INT(4) ZEROFILL
0001  0018  0103
```

Las unicas combinaciones soportadas son:

```sql
ZEROFILL

UNSIGNED ZEROFILL

ZEROFILL UNSIGNED
```
`ZEROFILL` solo, incluye tambien el `UNSIGNED`


<br><br>

## En Detalle

### `TINYINT` `INT1`

**Tamaño:** $1 \text{ Byte} = 8 \text{ Bit}$

**Rango** `TINYINT SIGNED`:
$$
\text{Min}: -2^{7} = -128
\hspace{3em}
\text{Max}: 2^{7}-1 = 127
$$

**Rango** `TINYINT UNSIGNED`:
$$
\text{Min}: 0
\hspace{3em}
\text{Max}: 2^{8}-1 = 255
$$
<br>


### `SMALLINT` `INT2`:

**Tamaño:** $2 \text{ Byte} = 16 \text{ Bit}$

**Rango** `SMALLINT SIGNED`:
$$
\text{Min}: -2^{15} = -32.768
\hspace{3em}
\text{Max}: 2^{15}-1 = 32.767
$$

**Rango** `SMALLINT UNSIGNED`:
$$
\text{Min}: 0
\hspace{3em}
\text{Max}: 2^{16}-1 = 65.535
$$
<br>


### `MEDIUMINT` `INT3`:

**Tamaño:** $3 \text{ Byte} = 24 \text{ Bit}$

**Rango** `MEDIUMINT SIGNED`:
$$
\text{Min}: -2^{23} = -8.388.608
\hspace{3em}
\text{Max}: 2^{23}-1 = 8.388.607
$$

**Rango** `MEDIUMINT UNSIGNED`:
$$
\text{Min}: 0
\hspace{3em}
\text{Max}: 2^{24}-1 = 16.777.215
$$
<br>


### `INT` `INTEGER` `INT4`:

**Tamaño:** $4 \text{ Byte} = 32 \text{ Bit}$

**Rango** `INT SIGNED`:
$$
\text{Min}: -2^{23} = -2.147.483.648
\hspace{2em}
\text{Max}: 2^{23}-1 = 2.147.483.647
$$

**Rango** `INT UNSIGNED`:
$$
\text{Min}: 0
\hspace{3em}
\text{Max}: 2^{32}-1 = 4.294.967.295
$$
<br>


### `BIGINT` `INT8`:

**Tamaño:** $8 \text{ Byte} = 64 \text{ Bit}$

**Rango** `BIGINT SIGNED`:
$$
\text{Min}: -2^{63} = -9.223.372.036.854.775.808
\hspace{2em}
\text{Max}: 2^{63}-1 = 9.223.372.036.854.775.807
$$

**Rango** `BIGINT UNSIGNED`:
$$
\text{Min}: 0
\hspace{3em}
\text{Max}: 2^{64}-1 = 18.446.744.073.709.551.615
$$
<br>



![alt](./tipos-numericos.svg)

<br><br>

#### Docs

- [Numeric data type](https://mariadb.com/kb/en/numeric-data-type-overview/)
- [TINYINT INT1](https://mariadb.com/kb/en/tinyint/)
- [SMALLINT INT2](https://mariadb.com/kb/en/smallint/)
- [MEDIUMINT INT3](https://mariadb.com/kb/en/mediumint/)
- [INT INTEGER INT4](https://mariadb.com/kb/en/int/)
- [BIGINT INT8](https://mariadb.com/kb/en/bigint/)
- [DECIMAL](https://mariadb.com/kb/en/decimal/)
- [FLOAT](https://mariadb.com/kb/en/float/)
- [DOUBLE](https://mariadb.com/kb/en/double/)
- [BIT](https://mariadb.com/kb/en/bit/)