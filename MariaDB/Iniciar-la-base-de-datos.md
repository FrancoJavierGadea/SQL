# MariaDB server

El servidor de `MariaDB` se llama `mariadbd.exe`

Ver la version del servidor

```sh
> mariadbd --version
```

<br>

Muestra todos las **opciones** que soporta junto con los valores de las **variables de configuracion del servidor**

```sh
> mariadbd --verbose --help
```

<br><br>


## Iniciar MariaDB server

Para iniciar `mariadb server` usamos el comando:

```sh
> mariadbd --console
```

La opcion `--console` es exclusiva de `Windows` y mantiene abierta la consola mostrando los mensajes de **LOG**


### Detener

Para detener el proceso y apagar la **base de datos usamos**: `Ctrl + C`


### Iniciar como servicio

Al instalar `MariaDB` podemos eleguir que se instale ademas como un **servicio de windows**

Podemos administrarlo desde `services.msc` o desde una terminal en modo administrador

#### Usando el comando `net`

```sh
//Iniciar
> net start MariaDB

//Detener
> net stop MariaDB
```

```sh
//Status
> Get-Service MariaDB
```

```sh
//Iniciar
> Start-Service -name MariaDB

//Detener
> Stop-Service -name MariaDB
```



<br><br>

### Configuracion basica

- `--port` `-P`: Indicamos el puerto por el cual recibira las conexiones, por defecto es: `3306`

    ```sh
    > mariadbd --port 3306 --console
    ```

<br>



<br><br>

#### Docs

- [mariadbd options](https://mariadb.com/kb/en/mariadbd-options/)
- [mariadbd options port](https://mariadb.com/kb/en/server-system-variables/#port)


- [](https://ss64.com/ps/get-service.html)
- [](https://ss64.com/nt/net-service.html)