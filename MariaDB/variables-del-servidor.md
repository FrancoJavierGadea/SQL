## Variables del Servidor

### Ver los valores de las variables del servidor

```sh
> mariadbd --verbose --help
```

o desde un `MariaDB client` y la `CLI Client`

```sh
> SHOW VARIABLES;
```

<br><br>


## Archivo de configuracion

El `archivo de configuracion` por defecto en `Windows` esta en:

El **directorio de instalacion** en la carpeta `data`

```text
| MariaDB 11.*
|-> data
|---> my.ini
```

<br><br>

#### Docs

- [server-system-variables](https://mariadb.com/kb/en/server-system-variables/#port)
- [server-system-variables: port](https://mariadb.com/kb/en/server-system-variables/#port)
- [configuring-mariadb-with-option-files](https://mariadb.com/kb/en/configuring-mariadb-with-option-files/)