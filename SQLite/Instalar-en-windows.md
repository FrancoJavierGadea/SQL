## Instalar SQLite en Windows

1. Descargar los ejecutables `sqlite-tools-win` para `windows` en: 

    [www.sqlite.org/download](https://www.sqlite.org/download.html)

<br>

2. Crear una **carpeta** o **directorio** `sqlite` en el disco `C:` y colocar los ejecutables

    ```text
    sqlite
    |-- sqlite3.exe
    |-- sqldiff.exe
    |-- sqlite3_analyzer.exe
    ```

<br>

3. Editar las `variables de entorno`

    - Crear la variable `SQLITE_HOME` con la ruta a la carpeta con los ejecutables

    - Agregar a la variable `PATH`: `%SQLITE_HOME%`

<br>

4. comprobar la instalacion abriendo una terminal y probando:

    ```sh
    > sqlite3 --version
    ```
    ```sh
    > sqlite3 --help
    ```

<br><br>

### Cientes para SQLite

- [sqlite browser](https://sqlitebrowser.org/)

- `sqlite studio` 
  [sqlitestudio.pl](https://sqlitestudio.pl/)
  [github](https://github.com/pawelsalawa/sqlitestudio/)

- `HeidiSQL`
  [heidisql.com](https://www.heidisql.com/)
  [github](https://github.com/HeidiSQL/HeidiSQL)