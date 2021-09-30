# Instalar Odoo con Docker 🐳

## Descarga e Instalación


1. Ir a [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop) 
    1. Descargar docker
    2. Instalar
    3. Verificar que esta instalado:
        1. Abrir terminal / cmd
        2. Poner comando: 

        ```bash
        $ docker --version
        ```

        Si es correcto, nos saldrá este mensaje según la versión instalada:

        ![Untitled](Instalar%20Odoo%20con%20Docker%20080c681afbe147a6accffa2f37b226ab/Untitled.png)

        En estos momentos podremos lazar comandos en la terminal (Linux/MacOS) o el cmd (si fuera Windows)

2. Instalación de Oddo y sus requerimientos

    a. Descargar la imagen de odoo, descargará todo lo que necesitamos

    ```bash
    $ docker pull odoo
    ```

    b. Iniciamos un PostgreSQL server

    ```bash
    $ docker run -d -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name db postgres:13
    ```

    c. Iniciamos una instancia de Odoo

    ```bash
    $ docker run -p 8069:8069 --name odoo --link db:db -t odoo
    ```

## Información de interés

- URL de acceso a odoo: [http://localhost:8069](http://localhost:8069)
- Iniciar contenedores:

```bash
$ docker start db
$ docker start odoo
```

- Detener contenedores:

```bash
$ docker stop odoo
$ docker stop db

```
