
### MariaDB

#### Conectar con la base de datos

Usamos el comando:

```sh
> mariadb --user=user_name --password 
```

Conectar a una **base de datos** en particular

```sh
> mariadb --user=user_name --password db_name
```

y introducimos la **contraseña**

<br>

### Otras configuraciones

- `--port` `-P`: Indicamos el puerto por el servidor `mariadbd` recibira las conexiones, por defecto es: `3306`

    ```sh
    > mariadb --port 3306 --user=user_name --password db_name
    ```


<br>

Ver las **variables de configuracion del servidor** `mariadbd`

```sql
> SHOW VARIABLES;
```