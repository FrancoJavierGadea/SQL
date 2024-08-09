# Exportar SQL a TXT

Exportar el resultado de una **consulta SQL** a un archivo `txt`, `csv`

Los ejecutables de `MariaDB server`: `mariadbd.exe` `mysqld.exe` tienen que tener permisos de **escritura**


<br><br>

## Configurar los permisos

### En windows

Buscamos los ejecutables del `MariaDB server` en la carpeta donde se instalo `MariaDB 11.x`:

- `MariaDB 11.x/bin/mariadbd.exe`
- `MariaDB 11.x/bin/mysqld.exe`

Y les damos permisos de **escritura** a los usuarios

> click derecho -> propiedades -> seguridad -> Editar


<br>

Ya con esto funcionara corriendo el `MariaDB server` desde una **terminal**

#### Servicio

Para que funcione tambien con el `servicio` `MariaDB` 

tenemos que abrir `services.msc`:

`Win + R` `services.msc`

Buscar el `servicio` `MariaDB` y en **propiedades -> iniciar sesion** asegurarse que 
este logeado con una **cuenta local** o una que tenga los permisos adecuados


<br><br>

## SELECT INTO OUTFILE

```sql
SELECT * FROM table_name INTO OUTFILE 'path/to/file.txt';
```

- `csv`

```sql
SELECT * FROM table_name INTO OUTFILE 'path/to/file.txt'
FIELDS TERMINATED BY ',' 
OPTIONALLY ENCLOSED BY '"'
LINES TERMINATED BY '\n';
```

- `JSON Array`

```sql
SELECT * FROM table_name INTO OUTFILE 'path/to/file.txt'
FIELDS TERMINATED BY ',' 
OPTIONALLY ENCLOSED BY '"'
LINES STARTING BY '[' TERMINATED BY '],\n';
```



<br><br>

#### Docs

- [select-into-outfile](https://mariadb.com/kb/en/select-into-outfile/)
- [secure_file_priv](https://mariadb.com/kb/en/server-system-variables/#secure_file_priv)
- 