## **Comandos CLI**

### Comandos tipicos

- Listado de imagenes descargadas en la maquina

    ```bash
    docker images
    ```

- Descargar imagen desde dockerhub (si no se pone versoin descargara la ultima disponible)

    ```bash
    docker pull <nombre_imagen>:<version_imagen>
    ```

- Eliminar imagenes descargadas en la maquina

    ```bash
    docker image rm <nombre_imagen>:<version_imagen>
    ```

- Crear contenedor desde imagen base 

    - Comando sirve para insertar nueva imagen a contenedor.
    - Sin no se le coloca nombre docker le asignara uno.
    - Se le asigna puerto para Port Mapping, Sin no se le coloca puerto de contenedor docker le asignara uno
    - p = publish.
    - -e sirve para asignar variables de entorno solicitadas por la respectiva imagen.
    - Retorna id.

    ```bash
    docker create -p<puerto_host>:<puerto_container> --name <nombre_contenedor> --network <nombre_red> <nombre_imagen> -e <nombre_variable>=<valor_variable>  
    ```

- Ejecutar contenedor
    ```bash
    docker start <id_contenedor>
    ```

- Detener contenedors
    ```bash
    docker stop <id_contenedor>
    ```

- Visualizar contenedoers corriendo
    ```bash
    docker ps
    ```

- Visualizar todos los contenedoers (corriendo o detenido)
    ```bash
    docker ps -a
    ```

- Visualizar ejecución de contenedor
    - --follow permite escuchar constantemente ejecución de contenedor
    ```bash
    docker logs --follow <nombre_contenedor>
    ```
- combinación de pull, create y start .
    - -d permit ejecutar comando sin considerar la visualización de logs
    - comando run crea en cada ejecución un nuevo contenedor
    ```bash
    docker run --name <nombre_contenedor> -p<puerto_host>:<puerto_container> -d <nombre_imagen>
    ```

### Comandos montar app en contenedos

- Crear acrhivo Dockerfile (instrucciones para crear contenedor de la app)

    ```bash
    Create file <ruta_root_app>/Dockerfile
    ```
- Escribir en Dockerfile

   - Imagen base para construir contenedor:

        ```docker
        From <nombre_imagen>:<version_imagen>
        ```

    - Carpeta (dentro del contenedor) donde se ubicara codigo fuente de la app

         ```docker
        RUN mkdir -p <ruta_app_SO_client>
        ```
    
    - Indicar de donde sacar código fuente

         ```docker
        COPY <ruta_app_SO_host> <ruta_app_SO_client>
        ```
    
    - Exponer puerto host para acceder a contenedor

         ```docker
        EXPOSE <puerto_host>
        ```
    
    - Comando a ejecutar para que app corra

         ```docker
         # ejemplo para node js
        CMD ["node", "<ruta_contenedor_index.js>"]
        ```
    
- Crear **imagenen** en base a archivo Dockerfile 

    - Para etiqueta, sule usarse la versión del contenedor.
    - Para *<ruta_Dockerfile>*, se utiliza '.' para representar ubicación actual (siempre que comando se ejecute en root de app)

    ```bash
    docker build -t <nombre_contenedo>:<etiqueta_contenedor> <ruta_Dockerfile>
    ```

### Redes internas contenedores

- Listado de redes configuradas en docker

    ```bash
    docker network ls
    ```

- Crear red en docker

    - Retorna id.

    ```bash
    docker network create <nombre_red>
    ```

- Eliminar red en docker

    - Retorna id.

    ```bash
    docker network rm <nombre_red>
    ```

### Definiciones

- Imagenes

- Contenedores:
    - Se crea en base a imagenes descargadas en la maquina.



### Repositorio publico a usar

- [hub.docker.com](https://hub.docker.com/)


### Notas generales:

- Docker utiliza el kernel (SO host) para ejecutarse.

- Existen 3 tipos de virtualización para VM:

    - Para-virtualización: SO anfitrion intenta entregar la mayor cantidad de acceso de su hardware al SO invitado.
    - Virtualización parcial: Algunos componentes del hardware se virtualizan para el SO invitado.
    - Viatualización completa: Todo el hardware utilizado por el SO cliente esta virtualizado, no se accede al hardware.

- *Port Mapping*: 
    - Mapear o conectar un puerto da la maquina host con un puerto de un contenedor.   
    
- Nombre que se le asigna a contenedor es el nombre de dominio interno paa redes docker.

- Contenedores dentro de una misma subred pueden comunicarse entre si con el nombre (dominio) de cada contenedor.

### Notas Docker Desktop

- Docker Desktop es una VM, optimizada y corre Linux (permite acceder a sistema de archivos y red)   . 

- Herramientas de Docker desktop:
    - Docker Compose
    - CLI
    - Corre nativo con WSL2 para Windows
