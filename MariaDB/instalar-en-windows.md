## Instalar MariaDB

1. Descargar el instalador de `MariaDB server` de la pagina:

    [mariadb.org/download](https://mariadb.org/download/)

3. Editar las `variables de entorno`

    - Crear la variable `MARIADB_HOME` con la ruta a la carpeta con los ejecutables: `C:\Program files\MariaDB 11.*\bin`

    - Agregar a la variable `PATH`: `%MARIADB_HOME%`

<br>

4. comprobar la instalacion abriendo una terminal y probando:

     ```sh
    > mariadb --version
    ```
    ```sh
    > mariadb --help
    ```

    Tambien podemos usar:

    ```sh
    > mysql --version
    ```
    ```sh
    > mysql --help
    ```

<br><br>


### Cientes para MySQL

- `PHPMyAdmin`
  [phpmyadmin.net](https://www.phpmyadmin.net/)
  [github](https://github.com/phpmyadmin/phpmyadmin)

- `HeidiSQL`
  [heidisql.com](https://www.heidisql.com/)
  [github](https://github.com/HeidiSQL/HeidiSQL)