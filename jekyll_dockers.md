# Sitio Local en Jekyll con Docker

### Antes de empezar a usar los comandos de este documento deberemos estar con el usuario: root

## Paso 1: Creamos un contenedor Docker con Jekyll

#### El comando necesario es:

```
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll
```

![Img](img/Captura1.png)

## Paso 2: Creamos la estructura de directorios y los archivos necesarios para un proyecto Jekyll nuevo

### Antes de usar este comando debemos estar en la siguiente ruta: /home/usuario

#### El comando necesario es:

```
docker run -it --rm -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll new blog
```

![Img](img/Captura2.png)

## Paso 3: Modificamos el archivo gemfile, el la parte de abajo añadimos gem "webrick"

![Img](img/Captura3.png)

## Paso 4: Con este comando nos permite servir de forma local un sitio HTML estatico generado a partir del proyecto

#### El comando necesario es:

```
docker run -it --rm -p 4000:4000 -v "$PWD:/srv/jekyll" jekyll/jekyll jekyll serve --force_polling
```

![Img](img/Captura4.png)

## Paso 5:Ahora para ver nuestro sitio web debemos abrir un navegador web de estas 2 formas

### Opcion 1 si lo hacemos en local

```
http://127.0.0.1:4000
```

### Opcion 2 si lo hacemos desde otra maquina

```
http://10.0.16.40:4000
```

![Img](img/Captura5.png)
