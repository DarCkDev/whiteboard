# **Pizarra (React JS, NodeJS, MongoDB & Docker)**

## **Funcionalidades**

- Dibujo libre
- Color de la línea y relleno
- Ancho del trazo
- Borrar todo el contenido
- Borrador
- Relleno opcional (al marcar el checkbox de relleno se habilita el selector de color para el relleno)
- ~~Cargar imagen desde los archivos.~~
- ~~Poder dibujar sobre la imagen sin afectar a la imagen.~~
- ~~Eliminar la imagen de fondo sin afectar los trazos.~~
- Insertar texto
- Guardar como imagen (PNG)
- Modo Colaborativo

### Persistencia IndexedDB & MongoDB

## IndexedDB (Local)
- Guardar
- Eliminar
- Listar

## MongoDB (Servidor)
- El lienzo se guarda automáticamente cada 30 segundos en la sala en la que se encuentre y se carga automáticamente al ingresar a una sala (modo colaborador).

**Importante** 
**Navegadores probados:**

- Google Chrome
- Microsoft Edge
- ~~Mozilla Firefox~~ (IndexedDB presenta problemas en Firefox (Windows))
- ~~Mozilla Firefox~~ (Socket.io presenta problemas en Firefox (Linux))

**No implementados**
- Turnos por colaboradores (Es decir, cada colaborador puede dibujar en cualquier momento).
- Lista de colaboradores presentes en la sala.

## **Funcionalidades con bugs**

- Rotar la figura
- Parpadeo cuando dibuja otro colaborador


## **Uso**

Por defecto está seleccionado el dibujo libre.
Para usar el borrador se debe seleccionar el botón de borrador.
Si se carga alguna imagen, aparecerá el botón de eliminar la imagen, de otro modo no.

Para insertar un círculo se debe hacer clic en el botón de círculo, posteriormente presionar el boton izquierdo del mouse sobre el canvas y arrastrar hasta el tamaño que se quiera.
Si se tiene la opción de relleno seleccionado, la figura tendrá el color de relleno que se haya seleccionado.

### _**Insertar texto**_

El texto usará el color seleccionado, hacer clic en el botón T y escribir el texto en el prompt, al aceptar hacer clic sobre el canvas para insertar el texto, el lugar donde se haga clic será la parte inferior izquierda del texto. Por defecto el tamaño de fuente es 16px, pero puede ser cambiado en la sección de _Tamaño_.

### _**Persistencia en Indexed DB (Local)**_

Presionar en el botón Guardar guarda el lienzo actual y se lista en el menú izquierdo.

Hacer **clic sobre el nombre (id)** carga el linezo guardado.

Hacer **clic sobre la x** elimina el lienzo de la base de datos.

## - **Instalación (Sin Docker)** -

### Requisitos:

- Tener instalado Node JS y NPM

Para instalar NodeJS en Windows y MacOS, seguir el [enlace](https://nodejs.org/en/) y descargar el instalador.

Para instalar NodeJS en Linux, seguir las instrucciones en el siguiente [enlace](https://github.com/nodesource/distributions/blob/master/README.md)


## Servidor (Dentro de la carpeta "Whiteboard-srv")

### Comandos para instalación del proyecto:

### `npm install`

Para poder instalar las dependencias del proyecto

### `npm run dev`

Mostrará en consola un mensaje "Server running on port 3003".

## Cliente (Dentro de la carpeta "Whiteboard-react"

### Comandos para instalación del proyecto:

### `npm install`

Para poder instalar las dependencias del proyecto

### `npm run start`

Inicia la aplicación en modo desarrollo.
Abrir [http://localhost:3000](http://localhost:3000) para ver en el navegador.

### `npm run build`

Construye la aplicación para producción, por defecto se encuentra en la carpeta _build_.


## - **Instalación (Con Docker)** -

### Requisitos:

- Tener instalado Node JS y NPM

Para instalar NodeJS en Windows y MacOS, seguir el [enlace](https://nodejs.org/en/) y descargar el instalador.

Para instalar NodeJS en Linux, seguir las instrucciones en el siguiente [enlace](https://github.com/nodesource/distributions/blob/master/README.md)

- Tener instaldo Docker Engine y Docker-Compose

Para instalar Docker Engine en Linux, seguir las instrucciones en el siguiente [enlace](https://docs.docker.com/engine/install/)

Para instalar Docker-Compose en Linux (ubuntu), seguir las instrucciones en el siguiente [enlace](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-es)


## General (Dentro de la carpeta principal "Whiteboard" donde se encuentran las carpetas "Whiteboard-srv", "Whiteboard-react" y los archivos "docker-compose.yml" y "README.md")

### Comandos para instalación del proyecto:

### `docker-compose build`

Generará las imágenes necesarias y copiará los archivos necesarios dentro de cada contenedor.

### `docker-compose up`

Iniciará los contenedores.

Una vez iniciado todo, abrir [http://localhost:3000](http://localhost:3000) para ver en el navegador.

### `docker-compose down`
Para detener los contenedores.

## - Modo colaborativo (Con o Sin Docker) -
**Parámetros**
room=NombreDeLaSala
username=NombreDeUsuario

NombreDeLaSala => Nombre de la sala donde desea ingresar. Si la sala no existe se creará una nueva. Si la sala existe se cargará el lienzo que se tiene guardado en la base de datos (MongoDB)

NombreDeUsuario => Nombre de usuario

Una vez iniciado el programa:

Abrir [http://localhost:3000?room=NombreDeLaSala&username=NombreDeUsuario](http://localhost:3000?room=NombreDeLaSala&username=NombreDeUsuario) con los parámetros room y username para ver en el navegador.
