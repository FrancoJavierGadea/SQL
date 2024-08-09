## SQLite

- [home](https://www.sqlite.org/)

- [download](https://www.sqlite.org/download.html)

<br>

### Crear una base de datos

Para **abrir** o **crear** una **base de datos** podemos:

usar el **comando**:

```sh
> sqlite3 database_name
```

o ya dentro de la terminal `sqlite3`: 

```sh
> .open database_name
```

<br>

#### Guardar en otro archivo

Si queremos **exportar** o **guardar** la **base de datos actual** en otro archivo usamos el comando:

```sh
> .save database_name
```

<br>

### SQL Syntax

```sql
CREATE TABLE Amigos (ID INTEGER PRIMARY KEY, Name TEXT, Age INTEGER, phone TEXT);
```

```sql
INSERT INTO Amigos (Name, Age, phone) VALUES ('Luciano javier Cordoba', 25, '+54 9 381 202-0962');
```

```sql
SELECT * FROM Amigos;
```

```sql
SELECT * FROM Amigos ORDER BY Age ASC;
```

```sql
SELECT * FROM Amigos WHERE Age = 24;
```

### Otros comandos

Ver la **direccion** del **directorial actual** en `windows`

```sh
> .shell echo %cd%
```