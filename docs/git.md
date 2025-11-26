---
title: "Tarea pps"
---

## **1\. Creación del repositorio**

En primer lugar voy a crear el directorio local en kali linux, para la unidad 0, y voy a definir mis variables de acceso a la cuenta de github que crearé a continuación:

![](img/imagen-9-1024x450.png)

Copio y pego mis variables en el terminal:

![](img/imagen-82-1024x583.png)

Creo otro directorio, llamado _tarea\_ud0_, dentro

![](img/imagen-11.png)

Consulto actualizaciones con → _apt update_ y las ejetucto con _apt upgrade_:

![](img/imagen-83.png)

A continuación instalo git:

```
sudo apt install git
```

```
sudo apt install git
```

![](img/imagen-3.png)

Procedo a crearme la cuenta en github, en este enlace --> [https://github.com/signup?source=login](https://github.com/signup?source=login)

![](img/imagen-5.png)

relleno los datos correspondientes,

![](img/imagen-7-1024x538.png)

Recibiré un código al email, aportado, y ya rellenándolo tendré la cuenta creada.

Hago login en github,

![](img/imagen-8-1024x666.png)

A continuación voy a fijar las variables globales de acceso a github, en nuestro terminal de kali linux, para mayor comodidad, y asi las toma tal y como las definí al principio de esta tarea (la puedes ver el .txt de la izquierda que cree):

```
git config --global user.name $Tu_usuario_github
git config --global user.email $Tu_mail_github
git config --global init.defaultBranch main
git config --global core.editor nano
```

```
git config --global user.name $Tu_usuario_github
git config --global user.email $Tu_mail_github
git config --global init.defaultBranch main
git config --global core.editor nano
```

![](img/imagen-12-1024x484.png)

Para comprobar que toma bien las variables, hago la comprobación con el nombre de usuario de github, mediante el comando --> _git config user.name_

Y efectivamente, me lo devuelve correctamente en el terminal.

![](img/imagen-14.png)

A continuación configuramos _git config --global core.pager ""_ --> con eso conseguimos que ante comandos como _git diff_ o _git log_ , los resultados se muestren por completo y sin paginar en el terminal.

![](img/imagen-13.png)

A continuación voy a crear la llave ssh para nuestro equipo para añadirla en github, y así darle un plus de seguridad en las conexiones:

```
ssh-keygen -t ed25519 -C $Tu_mail_github
```

```
ssh-keygen -t ed25519 -C $Tu_mail_github
```

![](img/imagen-84.png)

![](img/imagen-18.png)

A continuación, procedo a copiar la clave ssh pública que he creado en github, y la borro en mi equipo,

![](img/imagen-19.png)

y para copiarla en github, entro con la cuenta de github, y en mi perfil --> _settings_

![](img/imagen-20.png)

y en _SSH and GPG keys_

![](img/imagen-22.png)

Añado la clave a través del botón verde New SSS key,

![](img/imagen-23-1024x391.png)

le escribo un título, y añado:

![](img/imagen-85-1024x601.png)

![](img/imagen-27-1024x303.png)

A continuación procedo a crear un repositorio en github,

haciendo clic en el avatar del perfil (arriba a la derecha con la flecha amarilla) y _Repositories_,

![](img/imagen-29.png)

_New_,

![](img/imagen-30-1024x197.png)

Le doy nombre al repositorio, una descripción, y la opción de _Add README_ activada:

![](img/imagen-31.png)

y a continuación copio el código de acceso en ssh,

![](img/imagen-32-1024x499.png)

y hago un _git clone_ con ese código ssh del repositorio, tal que asi:

```
git clone git@github.com:cibermbl/PPS-Unidad0-Tarea-Manuel-Benitez.git
```

```
git clone git@github.com:cibermbl/PPS-Unidad0-Tarea-Manuel-Benitez.git
```

Observamos, que nos da una primera advertencia sobre la conexión al repositorio por ssh, y a la pregunta de si estoy seguro de que quiero conectarme escribo Yes,

![](img/imagen-86.png)

y observamos como ha creado el nuevo directorio --> _PPS-Unidad0-Tarea-Manuel-Benitez,_

navego dentro de él, y listo lo que contiene con -> _ls -la_

Observamos, como contiene el _README.md_, el directorio _.git,_ etc.

![](img/imagen-35-1024x446.png)

A continuación, procedo a crear la estructura del repositorio. Que debe ser como éste:

![](img/imagen-36.png)

Para ello, en primer lugar procedo a instalar la herramienta GitHub CLI, la cual nos permite interactuar directamente desde la linea de comandos con GitHub, y nos permite crear, modificar, repositorios directamente desde la terminal.

Nota.-. En primer lugar, me cercioro de que ya tengo las variables inicializadas, tal y como lo hice en renglones anteriores, mediante el código:

```
git config user.name
```

```
git config user.name
```

![](img/imagen-37.png)

Y efectivamente, tengo las variables declaradas, correctamente.

Instalación de GitHub CLI:

```
sudo apt update
sudo apt install gh
```

```
sudo apt update
sudo apt install gh
```

![](img/imagen-38.png)

![](img/imagen-39.png)

Una vez instalado, procedo a autenticarme en github.com:

```
gh auth login
```

```
gh auth login
```

Nos das dos opciones de autenticación, y escojo _GitHub.com_ (con el cursos y enter),

![](img/imagen-40.png)

A continuación nos da dos opciones de protocolo de conexión, y dado que ya tengo configurado por ssh, para seguir la política de buenas prácticas en ciberseguridad, la escojo,

![](img/imagen-41.png)

Observamos, como reconoce la clave pública, que anteriormente añadí en github, y le damos a enter,

![](img/imagen-42.png)

A continuación procedo a logearme mediante la opción --> _Login with a web browser,_

Nos genera una clave de un solo uso, la cual deberemos de copiar en github.com,

![](img/imagen-43.png)

Presiono Enter, y se abre el navegador, y procedemos a entrar con el usuario y contraseña de github, elegimos signed in as (con nuestro usuario de github), y clic en tecla _Continue,_

![](img/imagen-44-1024x694.png)

Y ya podemos pegar el código anterior:

![](img/imagen-45-1024x687.png)

Clic en _Authorize github_,

![](img/imagen-46.png)

y ya comprobamos como ya está sincronizado con mi ordenador,

![](img/imagen-47-1024x831.png)

A continuación, paso a crear la estructura del repositorio:

![](img/imagen-36.png)

Comandos:

```
#Para crear los directorios
<div></div>
mkdir calculator docs
<div></div>
#Para crear los archivos
<div></div>
touch directorio/archivo
<div></div>
#En el ejemplo:
<div></div>
touch calculator/__init__.py calculator/gui.py docs/index.md mkdocs.yml requiriments.txt
<div></div>
touch docs/git.m docs/gitActions.md docs/gitPages.md docs/docker.md docs/conclusiones.md
```

```
#Para crear los directorios

mkdir calculator docs

#Para crear los archivos

touch directorio/archivo

#En el ejemplo:

touch calculator/__init__.py calculator/gui.py docs/index.md mkdocs.yml requiriments.txt

touch docs/git.m docs/gitActions.md docs/gitPages.md docs/docker.md docs/conclusiones.md
```

![](img/imagen-48-1024x706.png)

Compruebo como está el estado del proyecto en Github:

```
git status
```

```
git status
```

y se puede comprobar como los archivos están los archivos sin seguimiento,

![](img/imagen-49.png)

Añado todos los directorios y archivos al directorio github,

```
git add .
```

```
git add .
```

Compruebo el estado, y observamos como aparecen en el area _staged_ (en verde),

![](img/imagen-50.png)

Muestro el contenido del directorio en forma de árbol,

```
tree -a
```

```
tree -a
```

![](img/imagen-51.png)

Procedo a borrar el directgorio .git,

```
rm -rf .git*
```

```
rm -rf .git*
```

![](img/imagen-55.png)

Voy a actualizar el repositorio en remoto, para que no incluya el directorio .git

```
git init
git add.
git commit -m "Actualización de los archivos después de borrar .git"
git remote add origin git@github.com:cibermbl/PPS-Unidad0-Tarea-Manuel-Benitez.git
```

```
git init
git add.
git commit -m "Actualización de los archivos después de borrar .git"
git remote add origin git@github.com:cibermbl/PPS-Unidad0-Tarea-Manuel-Benitez.git
```

![](img/imagen-56.png)

Voy a confirmar todos los cambios para la creación del repositorio, mediante los comandos,

y para subir los cambios,

![](img/imagen-53.png)

Debido a la eliminación del escritorio .git, me da error por que hay commits que ya no están en el nuevo repositorio modificado,

![](img/imagen-57.png)

Para subsanar esto,

```
# forzamos el git push (eliminando los antiguos commits)
<div></div>
git push origin main -f
```

```
# forzamos el git push (eliminando los antiguos commits)

git push origin main -f
```

![](img/imagen-58.png)

ya está todo subido en remoto a github,

![](img/imagen-59-1024x668.png)

![](img/imagen-60-1024x576.png)

Por último, voy a crear dar contenido al archivo _mkdocs.yml,_ que es un archivo en lenguaje de marcas .yml, el cual sirve para crear toda la estructura de una página web estática html, a partir de los archivos .md que creamos en la estructura situados en la carpeta _docs/_,

├── docs/  
│ └── index.md  
│ └── git.md  
│ └── gitActions.md  
│ └── gitPages.md  
│ └── docker.md  
│ └── conclusiones.md  

Pues con:

```
nano mkdocs.yml
```

```
nano mkdocs.yml
```

Escribo lo siguiente:

```
# -------------------------------------------------------------
# CONFIGURACIÓN GENERAL DEL SITIO
# -------------------------------------------------------------
site_name: Documentación Unidad 0 - Tarea 
# Define el título que aparecerá en la barra de navegación y en la etiqueta <title> del navegador.
<div></div>
# -------------------------------------------------------------
# ESTRUCTURA DE NAVEGACIÓN (MENÚ)
# -------------------------------------------------------------
# Define la lista de enlaces y el orden de aparición en el menú de navegación principal.
nav:
  # El nombre de la sección en el menú: nombre_archivo.md
  - Home: index.md                 # Enlace a la página principal.
  - Git: git.md                    # Documentación del proceso de creación del repositorio Git.
  - GitHub Actions: gitActions.md  # Documentación del flujo de trabajo automatizado.
  - GitHub Pages: gitPages.md      # Documentación del despliegue en GitHub Pages.
  - Docker: docker.md              # Documentación de la configuración y despliegue con Docker y Nginx.
  - Conclusiones: conclusiones.md  # Reflexiones y conclusiones finales.
<div></div>
# -------------------------------------------------------------
# DIRECTORIOS
# -------------------------------------------------------------
# Ruta de la carpeta que contiene todos los archivos .md (Markdown) de la documentación.
# MkDocs buscará aquí los archivos listados en 'nav'.
doc_dir: docs
<div></div>
# -------------------------------------------------------------
# TEMA (Opcional, pero común)
# -------------------------------------------------------------
# theme:
#   name: 'material'   # Si se utiliza el tema Material for MkDocs.
#   # highlightjs: true
#   # code_fences: true

```

```
# -------------------------------------------------------------
# CONFIGURACIÓN GENERAL DEL SITIO
# -------------------------------------------------------------
site_name: Documentación Unidad 0 - Tarea 
# Define el título que aparecerá en la barra de navegación y en la etiqueta <title> del navegador.

# -------------------------------------------------------------
# ESTRUCTURA DE NAVEGACIÓN (MENÚ)
# -------------------------------------------------------------
# Define la lista de enlaces y el orden de aparición en el menú de navegación principal.
nav:
  # El nombre de la sección en el menú: nombre_archivo.md
  - Home: index.md                 # Enlace a la página principal.
  - Git: git.md                    # Documentación del proceso de creación del repositorio Git.
  - GitHub Actions: gitActions.md  # Documentación del flujo de trabajo automatizado.
  - GitHub Pages: gitPages.md      # Documentación del despliegue en GitHub Pages.
  - Docker: docker.md              # Documentación de la configuración y despliegue con Docker y Nginx.
  - Conclusiones: conclusiones.md  # Reflexiones y conclusiones finales.

# -------------------------------------------------------------
# DIRECTORIOS
# -------------------------------------------------------------
# Ruta de la carpeta que contiene todos los archivos .md (Markdown) de la documentación.
# MkDocs buscará aquí los archivos listados en 'nav'.
doc_dir: docs

# -------------------------------------------------------------
# TEMA (Opcional, pero común)
# -------------------------------------------------------------
# theme:
#   name: 'material'   # Si se utiliza el tema Material for MkDocs.
#   # highlightjs: true
#   # code_fences: true
```

Como se observa en el el mkdocs.yml, en nav, partir de las .md que están en /docs, crea un menú de navegación. En doc\_dir: se define la ruta donde están los .md

![](img/imagen-63-1024x576.png)

```
# Guardo el archivo
Ctrl + o
```

```
# Guardo el archivo
Ctrl + o
```

## 2\. Creación de WorkFlow de GitHub Actions

En primer lugar mkdocs es una extensión de python, la cual ejecutaremos en el terminal mediante el workflow que vamos a crear, ejecutará mediante _git push_, instrucciones determinadas.

Dicho workflow debe ir dentro de un directorio llamado _.github_, vamos a comprobar mediante:

```
ls -la
```

```
ls -la
```

y vemos que dicho directorio no está en la estructura,

![](img/imagen-64-1024x576.png)

y vemos que no existe, por lo tanto, procedo a crearlo:

```
mkdir -p .github/workflows
```

```
mkdir -p .github/workflows
```

![](img/imagen-65-1024x576.png)

![](img/imagen-66-1024x573.png)

Y para definir el flujo de trabajo, creo el siguiente archivo,

```
.github/workflows/deploy_docs.yml
```

```
.github/workflows/deploy_docs.yml
```

y con el siguiente código:

```
# -----------------------------------------------------------
# CONFIGURACIÓN DEL WORKFLOW
# -----------------------------------------------------------
name: Deploy MkDocs # Define el nombre de este flujo de trabajo (aparece en la pestaña 'Actions' de GitHub).
<div></div>
on:
  # Define el evento que dispara este flujo de trabajo.
  push:
    # Este workflow se ejecutará automáticamente cada vez que se haga un 'push' (subida)
    # de código al repositorio.
    branches:
      - main # Específicamente, solo se ejecuta si el push se realiza sobre la rama 'main'.
<div></div>
# -----------------------------------------------------------
# PERMISOS
# -----------------------------------------------------------
# Otorga permisos específicos al GITHUB_TOKEN que se usará en este workflow.
permissions:
  contents: write # Permite que el token pueda leer y escribir contenido (necesario para la rama gh-pages).
  pages: write    # Permite gestionar y escribir en la configuración de GitHub Pages.
  id-token: write # Permite solicitar tokens de OpenID Connect (necesario para algunas integraciones de seguridad).
<div></div>
# -----------------------------------------------------------
# DEFINICIÓN DEL TRABAJO (JOB)
# -----------------------------------------------------------
jobs:
  deploy: # Define un único trabajo llamado 'deploy'.
    runs-on: ubuntu-latest # Especifica que este trabajo se ejecutará en un servidor virtual con la última versión de Ubuntu.
<div></div>
    steps: # La secuencia de comandos o acciones a ejecutar en el servidor de Ubuntu.
    
    # -------------------------------------------------------
    # PASO 1: OBTENER EL CÓDIGO FUENTE
    # -------------------------------------------------------
    - name: Checkout Repo # Nombre descriptivo del paso.
      # Utiliza una acción oficial de GitHub para clonar el repositorio
      # completo en el entorno de trabajo del Runner.
      uses: actions/checkout@v3
<div></div>
    # -------------------------------------------------------
    # PASO 2: CONFIGURAR PYTHON
    # -------------------------------------------------------
    - name: Set up Python # Nombre descriptivo del paso.
      # Utiliza una acción oficial para configurar el entorno de Python.
      uses: actions/setup-python@v4
      with:
        python-version: '3.x' # Especifica que se debe usar la última versión de Python 3.
<div></div>
    # -------------------------------------------------------
    # PASO 3: INSTALAR DEPENDENCIAS
    # -------------------------------------------------------
    - name: Install dependencies # Nombre descriptivo del paso.
      # Comando que se ejecuta en la terminal de Ubuntu.
      # Instala el generador de documentación MkDocs (necesario para el siguiente paso).
      run: pip install mkdocs
<div></div>
    # -------------------------------------------------------
    # PASO 4: CONSTRUIR Y DESPLEGAR LA DOCUMENTACIÓN
    # -------------------------------------------------------
    - name: Deploy docs # Nombre descriptivo del paso.
      # Comando que se ejecuta en la terminal.
      # 1. 'mkdocs gh-deploy': Construye la documentación (generando los archivos HTML/CSS/JS).
      # 2. '--force': Sube esos archivos generados y fuerza su publicación en la rama 'gh-pages'.
      run: mkdocs gh-deploy --force
      # Configuración de variables de entorno específicas para este paso.
      env:
        # Pasa el Token de GitHub. MkDocs lo necesita para autenticarse y subir
        # los archivos a la rama 'gh-pages' del repositorio.
        GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

```
# -----------------------------------------------------------
# CONFIGURACIÓN DEL WORKFLOW
# -----------------------------------------------------------
name: Deploy MkDocs # Define el nombre de este flujo de trabajo (aparece en la pestaña 'Actions' de GitHub).

on:
  # Define el evento que dispara este flujo de trabajo.
  push:
    # Este workflow se ejecutará automáticamente cada vez que se haga un 'push' (subida)
    # de código al repositorio.
    branches:
      - main # Específicamente, solo se ejecuta si el push se realiza sobre la rama 'main'.

# -----------------------------------------------------------
# PERMISOS
# -----------------------------------------------------------
# Otorga permisos específicos al GITHUB_TOKEN que se usará en este workflow.
permissions:
  contents: write # Permite que el token pueda leer y escribir contenido (necesario para la rama gh-pages).
  pages: write    # Permite gestionar y escribir en la configuración de GitHub Pages.
  id-token: write # Permite solicitar tokens de OpenID Connect (necesario para algunas integraciones de seguridad).

# -----------------------------------------------------------
# DEFINICIÓN DEL TRABAJO (JOB)
# -----------------------------------------------------------
jobs:
  deploy: # Define un único trabajo llamado 'deploy'.
    runs-on: ubuntu-latest # Especifica que este trabajo se ejecutará en un servidor virtual con la última versión de Ubuntu.

    steps: # La secuencia de comandos o acciones a ejecutar en el servidor de Ubuntu.
    
    # -------------------------------------------------------
    # PASO 1: OBTENER EL CÓDIGO FUENTE
    # -------------------------------------------------------
    - name: Checkout Repo # Nombre descriptivo del paso.
      # Utiliza una acción oficial de GitHub para clonar el repositorio
      # completo en el entorno de trabajo del Runner.
      uses: actions/checkout@v3

    # -------------------------------------------------------
    # PASO 2: CONFIGURAR PYTHON
    # -------------------------------------------------------
    - name: Set up Python # Nombre descriptivo del paso.
      # Utiliza una acción oficial para configurar el entorno de Python.
      uses: actions/setup-python@v4
      with:
        python-version: '3.x' # Especifica que se debe usar la última versión de Python 3.

    # -------------------------------------------------------
    # PASO 3: INSTALAR DEPENDENCIAS
    # -------------------------------------------------------
    - name: Install dependencies # Nombre descriptivo del paso.
      # Comando que se ejecuta en la terminal de Ubuntu.
      # Instala el generador de documentación MkDocs (necesario para el siguiente paso).
      run: pip install mkdocs

    # -------------------------------------------------------
    # PASO 4: CONSTRUIR Y DESPLEGAR LA DOCUMENTACIÓN
    # -------------------------------------------------------
    - name: Deploy docs # Nombre descriptivo del paso.
      # Comando que se ejecuta en la terminal.
      # 1. 'mkdocs gh-deploy': Construye la documentación (generando los archivos HTML/CSS/JS).
      # 2. '--force': Sube esos archivos generados y fuerza su publicación en la rama 'gh-pages'.
      run: mkdocs gh-deploy --force
      # Configuración de variables de entorno específicas para este paso.
      env:
        # Pasa el Token de GitHub. MkDocs lo necesita para autenticarse y subir
        # los archivos a la rama 'gh-pages' del repositorio.
        GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

![](img/imagen-67-1024x576.png)

Para entender el _deploy\_doc_s.yml:

Este archivo hace funcionar un workflow de Github Actions, y se consigue crear una serie de tareas automáticas que Github las ejecutará automáticamente.

En este caso concreto genera y además publica la documentación creadas por MkDocs, cada vez que subimos un cambio al repositorio.

```
on:
  push:
    branches:
      - main

```

```
on:
  push:
    branches:
      - main
```

Cada vez que ejecutamos un push en git, el workflow lo ejecuta automáticamente, y en concreto en la rama main.

```
permissions:
  contents: write
  pages: write
  id-token: write

```

```
permissions:
  contents: write
  pages: write
  id-token: write
```

Solo permisos de escritura, para escribir en el repositorio remoto, en Github pages donde se publicará la documentación.

En _jobs:_ se definen cuatro pasos,

```
uses: actions/checkout@v3
```

```
uses: actions/checkout@v3
```

Descarga todo el código del repositorio para poder trabajar con él.

```
uses: actions/setup-python@v4
with:
  python-version: '3.x'

```

```
uses: actions/setup-python@v4
with:
  python-version: '3.x'
```

MKDocs está hecho en Python, y para ello se define la versión que permite ejecutarlo, en este caso la 3.

```
run: pip install mkdocs
```

```
run: pip install mkdocs
```

Se instala el programa que generará la documentación en formato web (HTML).

```
run: mkdocs gh-deploy --force
env:
  GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

```
run: mkdocs gh-deploy --force
env:
  GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

MkDocs genera la web a partir de los archivos .md de la carpeta /docs, los publica automáticamente en la rama gh-pages, y Github Pages lo utiliza para mostrar la documentación online. El token, permite que MkDocs, tenga los permisos necesarios para subir esos cambios al repositorio.

A continuación voy a subir todos los cambios a remoto, mediante _commit_ y _push_,

  ```
  git add .
  git commit -m "Configuración de MkDocs y pipeline de documentación"
  git push origin main
```

```
  git add .
  git commit -m "Configuración de MkDocs y pipeline de documentación"
  git push origin main
```

![](img/imagen-68-1024x576.png)

A continuación, procedo a comprobar en Github, que se han generado los cambios, y en la pestaña Actions, compruebo como se puede ver el workflow recien creado:

En primer lugar, se puede observar como se ha creado correctamente, el directorio _.github/workflows_ con el archivo [_deploy\_docs.yml_](https://github.com/cibermbl/PPS-Unidad0-Tarea-Manuel-Benitez/blob/main/.github/workflows/deploy_docs.yml) en su interior,

![](img/imagen-70-1024x577.png)

y en la pestaña Actions, podemos ver como el workflow está ejecutandose:

![](img/imagen-71-1024x576.png)

Reviso el log,

![](img/imagen-72-1024x577.png)

![](img/imagen-73-1024x576.png)

## 3\. Vinculación con GitHub Pages

Una vez comprobado que nuestro workflow está en marcha, y ha completado una pipeline, hacemos estos pasos para activar Github Pages:

Settings / Pages,

![](img/imagen-76-1024x576.png)

Pages,

![](img/imagen-77-1024x574.png)

Y seleccionamos el branch --> gh-pages

![](img/imagen-78-1024x575.png)

Dejamos el directorio /(root) que viene por defecto y clic en save, para guardar los cambios,

![](img/imagen-79-1024x576.png)

Con esto ya hemos configurado la fuente del despliegue, a la rama gh-pages.

Observamos, como ya se ha generado el dominio de gh-pages --> `cibermbl.github.io`

![](img/imagen-80-1024x577.png)

Para ver si carga la pagina hemos de añadirle al dominio el repositorio de Github, que en este caso es ->

_**[cibermbl.github.io/PPS-Unidad0-Tarea-Manuel-Benitez](http://cibermbl.github.io/PPS-Unidad0-Tarea-Manuel-Benitez)**_

Y efectivamente vemos como la carga, correctamente:

![](img/imagen-81-1024x576.png)

Ahora está todas las páginas vacias. Ya podemos empezar a darle contenido a cada una de las páginas, que están en el directorio /docs, en leguaje markdown.

\]\]>
