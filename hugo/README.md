
## Documentación sobre Hugo
### [sitio oficial](https://gohugo.io/getting-started/quick-start/)

Hugo es un framework rápido para construir sitios web, creado en [Go](https://go.dev/).

## Prerrequisitos
Hay unos prerrequisitos iniciales, antes de iniciar:

1. Instalar Hugo, siguiendo la [documentación](https://gohugo.io/installation/) oficial.
2. Instalar Git, siguiendo la [documentación](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) oficial.


## Instalar Hugo

Vamos a realizar la instalación en `macOS`.

![alt text](/hugo/assets/image.png)

En este caso lo haremos mediante el manejador de paquetes [Homebrew](https://brew.sh/).
Basta con ejecutar el siguiente comando desde la terminal:
```bash
brew install hugo
```
![alt text](/hugo/assets/image-1.png)

Podemos utilizar el comando para revisar la versión instalada:
```bash
hugo version
```

## Construir sitio web

Para iniciar con Hugo, podemos seguir estos pasos:

1. Crear un sitio web
2. Agregar contenido
3. Configurar el sitio
4. Publicar el stio

## Crear sitio web

- Para crear un sitio web con Hugo, es importante tener los prerrequisitos instalados, y luego podemos ejecutar el comando:

```bash
hugo new site first-site
```

![alt text](/hugo/assets/image-2.png)

````
Congratulations! Your new Hugo site was created in /Users/jaitellez/development/github/personal/web-sites-templates/hugo/first-site.

Just a few more steps...

1. Change the current directory to /Users/jaitellez/development/github/personal/web-sites-templates/hugo/first-site.
2. Create or install a theme:
   - Create a new theme with the command "hugo new theme <THEMENAME>"
   - Or, install a theme from https://themes.gohugo.io/
3. Edit hugo.toml, setting the "theme" property to the theme name.
4. Create new content with the command "hugo new content <SECTIONNAME>/<FILENAME>.<FORMAT>".
5. Start the embedded web server with the command "hugo server --buildDrafts".

See documentation at https://gohugo.io/.
````

- El directorio queda con la siguiente estructura

![alt text](/hugo/assets/image-3.png)

- Ingresar al directorio con el comando:
```bash
cd first-site
```

- Clonar el tema de Anake en el directorio `themes`, lo añade como submódulo.

![alt text](/hugo/assets/image-4.png)
![alt text](/hugo/assets/image-5.png)

- Indicar el tema actual en la configuración del sitio.
```bash
echo "theme = 'ananke'" >> hugo.toml
```

- Iniciar el servidor de desarrollo de Hugo para ver el sitio.
```bash
hugo server
```

- Acceder al sitio web desde el navegador.
http://localhost:1313/


## Agregar contenido

- Para añadir una nueva página al sitio web, se puede hacer por medio del siguiente comando:

```bash
hugo new content content/posts/my-first-post.md
```

con este comando se crea el archivo `content/posts/my-first-post.md`.

Por defecto Hugo, no publica contenido de borrador, se identifica cuando tiene la etiqueta `draft = true` .

Modificar un poco el archivo con [Markdown](https://commonmark.org/help/)

Para incluir contenido borrador en la publicación, se puede bajar el servidor con `Ctrl + C` y luego ejecutar uno de los siguientes comandos:

```bash
hugo server --buildDrafts
hugo server -D
```

cuando ya termine los cambios puede cambiar la etiqueta `draft` a `false`.


## Configurar el sitio

Abrir el archivo de configuración de Hugo `hugo.toml` que está ubicado en la raíz del proyecto. Allí encontrará este contenido:

```toml
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
theme = 'ananke'
```

- `baseURL` propiedad donde debe colocarse la url del sitio web productiva.
- `languageCode` propiedad para indicar el lenguaje según la región.
- `title` propiedad para cambiar el título de su sitio web productivo.
- `theme` propiedad para cambiar el tema de su sitio web.

Bajar el servidor con `Ctrl + C` y volverlo a subir con `hugo server -D`


## Publicar sitio

POr último, debemos publicar el sitio web, aunque no se desplegará en producción directamente. Hugo se encarga de crear el sitio estático en el directorio `public` en la raíz del proyecto.

Tener en cuenta que hay que cambiar los `draft` a `false`, en caso de querer publicarlos.

Una vez está todo listo para la publicación, procedemos a ejecutar el comando:

```bash
hugo 
```

este crea la estructura del sitio estático en `public` y `resources`.

- Luego de esto, para tener el sitio web ya desplegado en producción, tenemos algunas alternativas que podemos ver en esta publicación.


## Publicar sitio en producción

- Tenemos una forma manual, por decirlo de alguna forma, donde tomamos todo el contenido de `public` y lo subimos al hosting productivo y debería ser suficiente.
- Hugo nos brinda [documentación](https://gohugo.io/hosting-and-deployment/) para poder hacer estos despliegues productivos.
