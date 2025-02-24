# CURSO-BASICO-GIT

# Curso de Git y GitHub desde CERO para PRINCIPIANTES

## Índice
1. [Introducción](#introducción)
2. [¿Qué es Git?](#qué-es-git)
3. [Instalación de Git](#instalación-de-git)
4. [Configuración inicial](#configuración-inicial)
5. [Comandos básicos de terminal](#comandos-básicos-de-terminal)
6. [Primeros pasos con Git](#primeros-pasos-con-git)
7. [Trabajando con repositorios locales](#trabajando-con-repositorios-locales)
8. [Trabajando con ramas](#trabajando-con-ramas)
9. [Gestión de cambios](#gestión-de-cambios)
10. [Trabajo con etiquetas](#trabajo-con-etiquetas)
11. [¿Qué es GitHub?](#qué-es-github)
12. [Creando una cuenta en GitHub](#creando-una-cuenta-en-github)
13. [Configurando la conexión segura SSH](#configurando-la-conexión-segura-ssh)
14. [Conectando Git con GitHub](#conectando-git-con-github)
15. [Clonando repositorios](#clonando-repositorios)
16. [Colaborando en GitHub](#colaborando-en-github)
17. [Flujos de trabajo profesionales](#flujos-de-trabajo-profesionales)
18. [Herramientas gráficas para Git](#herramientas-gráficas-para-git)
19. [Características adicionales de GitHub](#características-adicionales-de-github)
20. [Ejercicio práctico final](#ejercicio-práctico-final)
21. [Recursos adicionales](#recursos-adicionales)

## Introducción

¡Bienvenido/a al curso de Git y GitHub desde cero! Este curso está diseñado para que cualquier persona, incluso sin experiencia previa en control de versiones, pueda aprender a utilizar estas herramientas fundamentales en el desarrollo de software.

### ¿Por qué aprender Git y GitHub?

Trabajar con código de forma segura es tan importante como aprender a programar. Git y GitHub son herramientas esenciales por varias razones:

- **Control de versiones**: Permiten guardar el historial completo de cambios en tu código
- **Trabajo en equipo**: Facilitan la colaboración entre desarrolladores
- **Seguridad**: Funcionan como respaldo de tu código
- **Estándar de la industria**: Son utilizadas en prácticamente todas las empresas de desarrollo

Según la encuesta anual de Stack Overflow:
- Más del 93% de los desarrolladores utilizan Git
- GitHub es la plataforma de control de versiones más utilizada (87% a nivel personal y 55% a nivel profesional)

### Recursos disponibles

Para aprovechar al máximo este curso, tienes a tu disposición:
- Este documento de teoría
- Ejemplos prácticos con cada tema
- Ejercicios para aplicar lo aprendido

## ¿Qué es Git?

Git es un **sistema de control de versiones distribuido** creado por Linus Torvalds (el mismo creador del kernel de Linux) en 2005.

### Diferencia entre Git y otros sistemas de control de versiones

A diferencia de los sistemas de control de versiones centralizados anteriores, Git:

- Es distribuido, lo que significa que cada desarrollador tiene una copia completa del repositorio
- Es más rápido porque la mayoría de las operaciones son locales
- Permite trabajar sin conexión
- Es más seguro porque si el servidor central falla, cualquier copia local puede restaurarlo

### Historia de Git

Linus Torvalds creó Git mientras desarrollaba el kernel de Linux. Insatisfecho con los sistemas de control de versiones existentes, decidió crear uno propio que cumpliera con sus necesidades:

> "Estaba desarrollando el kernel de Linux y necesitaba un sistema de control de versiones que realmente funcionara para un proyecto tan grande. Ninguna de las opciones existentes me convencía, así que creé mi propio sistema."

Git fue diseñado con un enfoque en la velocidad, la integridad de los datos y el soporte para el desarrollo no lineal.

## Instalación de Git

Antes de empezar a usar Git, necesitamos instalarlo en nuestro sistema operativo.

### En Windows

1. Visita [git-scm.com/download/win](https://git-scm.com/download/win)
2. Descarga el instalador y ejecútalo
3. Puedes aceptar las opciones predeterminadas durante la instalación
4. Al finalizar, tendrás acceso a "Git Bash", una terminal para usar Git

### En macOS

**Opción 1: Usando Homebrew**
```bash
brew install git
```

**Opción 2: Desde el instalador**
1. Visita [git-scm.com/download/mac](https://git-scm.com/download/mac)
2. Descarga e instala el paquete

### En Linux (Ubuntu/Debian)

```bash
sudo apt-get update
sudo apt-get install git
```

### Verificar la instalación

Para comprobar que Git se ha instalado correctamente, abre una terminal (o Git Bash en Windows) y escribe:

```bash
git --version
```

Deberías ver algo como `git version 2.39.0` (el número puede variar).

## Configuración inicial

Antes de empezar a utilizar Git, es necesario configurar tu identidad. Esta información se utilizará para identificar tus contribuciones en los proyectos.

### Configurando nombre de usuario y email

Abre una terminal y ejecuta:

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"
```

Esta información se guarda en un archivo llamado `.gitconfig` en tu directorio de usuario.

### Verificar la configuración

Para ver tu configuración actual:

```bash
git config --list
```

### Ayuda en Git

Si necesitas ayuda con cualquier comando de Git:

```bash
git help <comando>
# Por ejemplo:
git help config
```

## Comandos básicos de terminal

Antes de profundizar en Git, es útil conocer algunos comandos básicos de terminal que usaremos frecuentemente.

### Navegación

```bash
# Ver el directorio actual
pwd

# Listar archivos y directorios
ls
# En Windows con Git Bash:
ls
# O también:
dir

# Cambiar de directorio
cd nombre_directorio

# Subir un nivel de directorio
cd ..
```

### Manipulación de archivos y directorios

```bash
# Crear un directorio
mkdir nombre_directorio

# Crear un archivo vacío
touch nombre_archivo.txt

# Eliminar un archivo
rm nombre_archivo.txt

# Eliminar un directorio
rm -r nombre_directorio
```

### Consejos para la terminal

- Usa la tecla Tab para autocompletar nombres de archivos y comandos
- Usa las flechas arriba/abajo para navegar por comandos anteriores
- Usa `clear` para limpiar la pantalla de la terminal

## Primeros pasos con Git

Ahora que tenemos Git instalado y configurado, vamos a empezar a usarlo.

### Conceptos fundamentales

Antes de comenzar, es importante entender tres conceptos clave:

1. **Repositorio**: Es el lugar donde Git almacena todo el historial de cambios de un proyecto
2. **Commit**: Es una "fotografía" o instantánea de los archivos en un momento determinado
3. **Rama (Branch)**: Es una línea independiente de desarrollo

### Inicializar un repositorio

Para convertir un directorio normal en un repositorio Git:

```bash
# Primero, crea un directorio para tu proyecto
mkdir mi_proyecto
cd mi_proyecto

# Inicializa el repositorio Git
git init
```

Este comando crea un subdirectorio oculto llamado `.git` que contiene toda la información necesaria para el control de versiones.

### Comprobando el estado

Para ver el estado actual de tu repositorio:

```bash
git status
```

Este comando te mostrará información sobre:
- La rama en la que te encuentras
- Archivos modificados que aún no han sido confirmados
- Archivos nuevos que no están siendo rastreados por Git

## Trabajando con repositorios locales

Vamos a crear nuestro primer proyecto con Git y aprender el flujo de trabajo básico.

### Ciclo básico de trabajo

El flujo básico de trabajo con Git consiste en:

1. Modificar archivos en tu directorio de trabajo
2. Preparar los archivos, añadiéndolos al área de preparación (staging)
3. Confirmar los cambios, creando una instantánea permanente en el repositorio

### Creando nuestro primer archivo

```bash
# Crear un archivo de ejemplo
echo "# Mi primer proyecto con Git" > README.md
```

### Revisando el estado

```bash
git status
```

Verás que Git detecta un archivo nuevo (README.md) pero indica que no está siendo rastreado.

### Añadiendo archivos al área de preparación

Para que Git comience a rastrear un archivo, debemos añadirlo al área de preparación:

```bash
git add README.md
```

Si queremos añadir todos los archivos modificados:

```bash
git add .
```

### Confirmando cambios (haciendo un commit)

Una vez que los archivos están en el área de preparación, podemos confirmar los cambios:

```bash
git commit -m "Mi primer commit: Añadido README.md"
```

El mensaje después de `-m` debe ser descriptivo, explicando qué cambios has realizado.

### Verificando el historial

Para ver el historial de commits:

```bash
git log
```

Para una visualización más compacta:

```bash
git log --oneline
```

### Creando un alias para mejorar la visualización

Para crear un comando personalizado que muestre el historial de forma más visual:

```bash
git config --global alias.tree "log --graph --decorate --all --oneline"
```

Ahora puedes usar `git tree` para ver una representación gráfica del historial.

## Trabajando con ramas

Las ramas son una de las características más poderosas de Git, permitiendo trabajar en diferentes versiones del proyecto simultáneamente.

### ¿Qué es una rama?

Una rama en Git es simplemente un puntero móvil a uno de los commits. La rama principal por defecto se llama "main" (anteriormente "master").

### Ver las ramas existentes

```bash
git branch
```

### Crear una nueva rama

```bash
git branch nueva-caracteristica
```

### Cambiar a otra rama

```bash
git switch nueva-caracteristica
# O con el comando más antiguo:
git checkout nueva-caracteristica
```

### Crear y cambiar a una rama en un solo paso

```bash
git checkout -b otra-caracteristica
```

### Fusionar ramas

Cuando has completado el trabajo en una rama y quieres incorporar los cambios a la rama principal:

```bash
# Primero, vuelve a la rama principal
git checkout main

# Luego, fusiona la otra rama
git merge nueva-caracteristica
```

### Ejemplo práctico de trabajo con ramas

Vamos a modificar nuestro proyecto para practicar:

```bash
# Crear y cambiar a una nueva rama
git checkout -b agregar-contenido

# Modificar el archivo README.md
echo "## Descripción" >> README.md
echo "Este es un proyecto de prueba para aprender Git" >> README.md

# Añadir y confirmar los cambios
git add README.md
git commit -m "Agregada descripción al README"

# Volver a la rama principal
git checkout main

# Fusionar los cambios
git merge agregar-contenido
```

### Resolver conflictos

A veces, Git no puede fusionar automáticamente los cambios debido a conflictos. Esto ocurre cuando las mismas líneas de un archivo han sido modificadas de diferentes maneras en las ramas que intentas fusionar.

Si hay un conflicto, Git lo indicará en el archivo afectado:

```
<<<<<<< HEAD
Contenido en la rama actual
=======
Contenido en la rama que estás fusionando
>>>>>>> nombre-de-rama
```

Para resolver el conflicto:
1. Edita el archivo para eliminar los marcadores y elegir qué contenido conservar
2. Añade el archivo resuelto: `git add archivo-con-conflicto`
3. Completa la fusión: `git commit -m "Resuelto conflicto en archivo-con-conflicto"`

## Gestión de cambios

Vamos a explorar cómo gestionar los cambios en nuestro repositorio de forma efectiva.

### Ver diferencias entre commits

Para ver qué ha cambiado pero aún no está en el área de preparación:

```bash
git diff
```

Para ver qué cambios están en el área de preparación:

```bash
git diff --staged
```

### Deshacer cambios

**Para deshacer cambios en archivos que aún no están en el área de preparación:**

```bash
git checkout -- archivo.txt
```

**Para quitar un archivo del área de preparación:**

```bash
git reset HEAD archivo.txt
```

**Para deshacer el último commit manteniendo los cambios:**

```bash
git reset --soft HEAD~1
```

**Para deshacer el último commit descartando los cambios (¡cuidado!):**

```bash
git reset --hard HEAD~1
```

### Guardar cambios temporalmente (stash)

El "stash" es útil cuando necesitas cambiar de rama pero tienes cambios sin confirmar:

```bash
# Guardar cambios en el stash
git stash

# Listar stashes guardados
git stash list

# Recuperar el último stash y eliminarlo de la lista
git stash pop

# Aplicar el stash sin eliminarlo
git stash apply

# Eliminar un stash
git stash drop
```

### Ejemplo práctico de stash

```bash
# Modificar README.md
echo "## Nuevo contenido temporal" >> README.md

# Guardar temporalmente los cambios
git stash

# Cambiar de rama
git checkout otra-rama

# Hacer algún trabajo en otra-rama
# ...

# Volver a la rama original
git checkout main

# Recuperar los cambios guardados
git stash pop
```

## Trabajo con etiquetas

Las etiquetas (tags) son referencias que señalan a puntos específicos en la historia de Git. Son útiles para marcar versiones de lanzamiento.

### Crear una etiqueta

```bash
# Etiqueta simple
git tag v1.0.0

# Etiqueta anotada (recomendada)
git tag -a v1.0.0 -m "Versión 1.0.0 - Primer lanzamiento estable"
```

### Listar etiquetas

```bash
git tag
```

### Ver información detallada de una etiqueta

```bash
git show v1.0.0
```

### Etiquetar un commit anterior

```bash
# Primero, encuentra el hash del commit
git log --oneline

# Luego, etiqueta ese commit específico
git tag -a v0.9.0 -m "Versión Beta" 9fceb02
```

### Compartir etiquetas

Por defecto, `git push` no transfiere etiquetas. Para hacerlo:

```bash
# Enviar una etiqueta específica
git push origin v1.0.0

# Enviar todas las etiquetas
git push origin --tags
```

## ¿Qué es GitHub?

Después de aprender Git, es momento de entender GitHub y cómo ambos trabajan juntos.

### Diferencia entre Git y GitHub

- **Git** es un sistema de control de versiones que funciona en tu máquina local
- **GitHub** es una plataforma en la nube que aloja repositorios Git

GitHub añade funcionalidades adicionales como:
- Interfaz web para visualizar repositorios
- Herramientas de colaboración (pull requests, issues)
- Gestión de proyectos
- Integración continua

### Alternativas a GitHub

Aunque GitHub es la plataforma más popular, existen alternativas:
- GitLab
- Bitbucket
- GitKraken
- Azure DevOps

## Creando una cuenta en GitHub

Vamos a crear una cuenta en GitHub para poder empezar a usar la plataforma.

### Pasos para crear una cuenta

1. Ve a [github.com](https://github.com)
2. Haz clic en "Sign up" (Registrarse)
3. Introduce tu correo electrónico, contraseña y nombre de usuario
4. Completa la verificación
5. Selecciona tus preferencias (puedes saltarte este paso)
6. Verifica tu dirección de correo electrónico

### Personalizando tu perfil

Una vez creada tu cuenta:
1. Haz clic en tu avatar en la esquina superior derecha
2. Selecciona "Settings" (Configuración)
3. Completa tu perfil con:
   - Foto de perfil
   - Nombre
   - Biografía
   - Ubicación (opcional)
   - Página web (opcional)

### Configuración del repositorio especial de perfil

Puedes crear un repositorio especial con el mismo nombre que tu usuario para personalizar tu página de perfil:

1. Crea un nuevo repositorio con exactamente el mismo nombre que tu nombre de usuario
2. Añade un archivo README.md
3. Este archivo se mostrará en tu perfil

## Configurando la conexión segura SSH

Para conectar tu Git local con GitHub de forma segura, es recomendable usar claves SSH.

### ¿Qué es SSH?

SSH (Secure Shell) es un protocolo que permite una conexión segura entre tu ordenador y GitHub, sin necesidad de introducir tu nombre de usuario y contraseña cada vez.

### Generar una clave SSH

```bash
# Generar una nueva clave SSH
ssh-keygen -t ed25519 -C "tu.email@ejemplo.com"

# Presiona Enter para aceptar la ubicación predeterminada
# Opcional: introduce una contraseña para mayor seguridad
```

### Iniciar el agente SSH

```bash
# En Mac/Linux
eval "$(ssh-agent -s)"

# En Windows (Git Bash)
eval $(ssh-agent -s)
```

### Añadir la clave SSH al agente

```bash
ssh-add ~/.ssh/id_ed25519
```

### Añadir la clave SSH a tu cuenta de GitHub

1. Copia el contenido de tu clave pública:
   ```bash
   # Mac/Linux
   cat ~/.ssh/id_ed25519.pub | pbcopy
   
   # Windows (Git Bash)
   cat ~/.ssh/id_ed25519.pub | clip
   ```

2. En GitHub:
   - Ve a Settings > SSH and GPG keys
   - Haz clic en "New SSH key"
   - Dale un título descriptivo (ej. "Mi laptop personal")
   - Pega la clave en el campo "Key"
   - Haz clic en "Add SSH key"

### Probar la conexión

```bash
ssh -T git@github.com
```

Deberías ver un mensaje como: "Hi username! You've successfully authenticated, but GitHub does not provide shell access."

## Conectando Git con GitHub

Ahora que tenemos configurada la conexión SSH, vamos a aprender a trabajar con GitHub.

### Crear un nuevo repositorio en GitHub

1. En GitHub, haz clic en el botón "+" en la esquina superior derecha
2. Selecciona "New repository"
3. Completa la información:
   - Nombre del repositorio
   - Descripción (opcional)
   - Visibilidad (público o privado)
   - Inicializar con README (opcional)
   - Añadir .gitignore (opcional)
   - Elegir licencia (opcional)
4. Haz clic en "Create repository"

### Conectar un repositorio local existente con GitHub

Si ya tienes un repositorio local y quieres subirlo a GitHub:

```bash
# Añadir el repositorio remoto
git remote add origin git@github.com:tu-usuario/nombre-repositorio.git

# Verificar que se ha añadido correctamente
git remote -v

# Subir tus cambios al repositorio remoto
git push -u origin main
```

El flag `-u` (o `--set-upstream`) establece una relación de seguimiento, lo que significa que en el futuro solo necesitarás usar `git push` sin más argumentos.

### Actualizar repositorio local con cambios remotos

```bash
# Obtener los cambios sin fusionarlos
git fetch origin

# Obtener y fusionar los cambios en una sola operación
git pull origin main
```

### Ejemplo práctico de sincronización

```bash
# Crear un nuevo archivo localmente
echo "# Nuevo archivo" > archivo.md

# Añadir y confirmar
git add archivo.md
git commit -m "Añadido nuevo archivo"

# Subir a GitHub
git push

# Simular un cambio en GitHub (aquí harías el cambio en la interfaz web)
# ...

# Actualizar tu repositorio local
git pull
```

## Clonando repositorios

Una de las ventajas de GitHub es poder trabajar con repositorios creados por otros.

### Clonar un repositorio

```bash
git clone git@github.com:usuario/repositorio.git
```

Esto creará una carpeta con el nombre del repositorio y descargará todo su contenido, incluyendo el historial completo.

### Clonar a un directorio específico

```bash
git clone git@github.com:usuario/repositorio.git mi-directorio
```

### Clonar una rama específica

```bash
git clone -b nombre-rama git@github.com:usuario/repositorio.git
```

### Después de clonar

Una vez clonado un repositorio:
1. Explora la estructura del proyecto
2. Lee el archivo README.md para entender cómo configurar y usar el proyecto
3. Revisa las ramas disponibles con `git branch -a`

## Colaborando en GitHub

GitHub facilita la colaboración entre desarrolladores mediante distintos mecanismos.

### Modelo Fork & Pull Request

Este es el modelo de colaboración más común en proyectos de código abierto:

1. **Fork**: Crear tu propia copia del repositorio en tu cuenta de GitHub
2. **Clone**: Clonar tu fork a tu máquina local
3. **Branch**: Crear una rama para tu contribución
4. **Commit**: Realizar y confirmar tus cambios
5. **Push**: Subir tu rama a tu fork
6. **Pull Request**: Solicitar que tus cambios se integren en el repositorio original

### Creando un Fork

1. Navega al repositorio que quieres bifurcar
2. Haz clic en el botón "Fork" en la esquina superior derecha
3. Selecciona tu cuenta como destino del fork

### Manteniendo un Fork actualizado

```bash
# Añadir el repositorio original como remoto
git remote add upstream git@github.com:usuario-original/repositorio.git

# Verificar los remotos
git remote -v

# Obtener los cambios del repositorio original
git fetch upstream

# Asegurarte de estar en la rama principal
git checkout main

# Fusionar los cambios del repositorio original
git merge upstream/main

# Actualizar tu fork en GitHub
git push
```

### Creando un Pull Request

1. En GitHub, navega a tu fork
2. Haz clic en "Compare & pull request" (si acabas de hacer push) o en "New pull request"
3. Selecciona las ramas que quieres comparar
4. Añade un título y descripción que explique tus cambios
5. Haz clic en "Create pull request"

### Buenas prácticas para Pull Requests

1. Haz cambios pequeños y enfocados
2. Escribe un título claro y descriptivo
3. En la descripción, explica:
   - Qué cambios has realizado
   - Por qué los has realizado
   - Cómo se pueden probar
4. Menciona cualquier issue relacionado con "#" seguido del número
5. Responde a los comentarios y realiza los cambios solicitados

## Flujos de trabajo profesionales

En entornos profesionales, los equipos suelen seguir flujos de trabajo estructurados. Veamos el más popular.

### GitFlow

GitFlow es un modelo de ramificación que define roles específicos para diferentes tipos de ramas:

#### Ramas principales
- **main**: Contiene código en producción
- **develop**: Rama de desarrollo principal

#### Ramas de soporte
- **feature/**: Para nuevas características
- **release/**: Para preparar versiones
- **hotfix/**: Para correcciones urgentes

#### Flujo básico en GitFlow

1. Se desarrollan nuevas características en ramas `feature/`
2. Las características completadas se fusionan en `develop`
3. Cuando `develop` tiene suficientes características para un lanzamiento, se crea una rama `release/`
4. La rama `release/` se prueba y corrige
5. Cuando está lista, se fusiona en `main` y en `develop`
6. Si hay un error en producción, se crea una rama `hotfix/` desde `main`
7. La corrección se fusiona en `main` y en `develop`

### Instalación y uso de Git Flow

Existen herramientas que facilitan trabajar con GitFlow:

```bash
# Instalación en macOS
brew install git-flow

# Inicializar GitFlow en un repositorio
git flow init

# Trabajar con características
git flow feature start nueva-funcion
# Trabajar en la función...
git flow feature finish nueva-funcion

# Crear una versión
git flow release start 1.0.0
# Preparar la versión...
git flow release finish 1.0.0

# Corregir un error urgente
git flow hotfix start error-critico
# Corregir el error...
git flow hotfix finish error-critico
```

## Herramientas gráficas para Git

Aunque la línea de comandos te da control total, las herramientas gráficas pueden facilitar ciertas tareas.

### GitHub Desktop

- Desarrollada por GitHub
- Simple y fácil de usar
- Perfecta para principiantes
- Disponible para Mac y Windows
- [Descargar GitHub Desktop](https://desktop.github.com/)

### GitKraken

- Interfaz visual potente
- Funciona en Windows, Mac y Linux
- Muestra claramente el historial de ramas
- Integración con GitHub, GitLab, Bitbucket
- [Descargar GitKraken](https://www.gitkraken.com/)

### SourceTree

- Desarrollado por Atlassian
- Gratuito para uso personal
- Interfaz detallada
- Potentes funciones de visualización
- [Descargar SourceTree](https://www.sourcetreeapp.com/)

### Visual Studio Code

- Editor de código con extensiones para Git
- Te permite usar Git sin salir del editor
- Combina edición de código y control de versiones
- [Descargar VS Code](https://code.visualstudio.com/)

### ¿Cuál usar?

No hay una respuesta única:
- Si estás empezando, GitHub Desktop es simple y potente
- Si quieres visualizar bien el historial, GitKraken es excelente
- Si necesitas una herramienta completa, SourceTree es muy potente
- Si ya usas VS Code, sus extensiones de Git pueden ser suficientes

Lo importante es entender los conceptos de Git, independientemente de la herramienta que uses.

## Características adicionales de GitHub

GitHub ofrece muchas funcionalidades más allá del control de versiones.

### GitHub Pages

GitHub Pages te permite alojar sitios web directamente desde tus repositorios:

1. Crea un repositorio llamado `username.github.io`
2. Añade tu código HTML, CSS y JavaScript
3. Activa GitHub Pages en la configuración del repositorio
4. Tu sitio estará disponible en `https://username.github.io`

También puedes activar GitHub Pages para cualquier repositorio en Settings > Pages.

### GitHub Actions

GitHub Actions te permite automatizar flujos de trabajo directamente en GitHub:

- Compilación y pruebas automáticas
- Despliegue automático
- Verificación de código
- Publicación de paquetes

Para usar GitHub Actions, crea un archivo en `.github/workflows/nombre.yml`:

```yaml
name: CI

on:
  push:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Instalar dependencias
      run: npm install
    - name: Ejecutar pruebas
      run: npm test
```

### Issues y Projects

- **Issues**: Sistema de seguimiento de tareas y errores
- **Projects**: Tableros Kanban para organizar el trabajo

### Wikis

Cada repositorio puede tener una wiki para documentación detallada.

### Discusiones

Espacio para conversaciones generales, preguntas y respuestas.

## Ejercicio práctico final

Para consolidar todo lo aprendido, vamos a realizar un ejercicio completo.

### Objetivo

Crear un pequeño proyecto personal y publicarlo en GitHub, siguiendo todo el flujo de trabajo profesional.

### Pasos detallados

1. **Crea un repositorio local**:
   ```bash
   mkdir mi-proyecto-final
   cd mi-proyecto-final
   git init
   ```

2. **Crea un archivo README.md**:
   ```bash
   echo "# Mi Proyecto Final" > README.md
   echo "Este es un proyecto para practicar Git y GitHub" >> README.md
   ```

3. **Crea un .gitignore** (útil para cualquier proyecto):
   ```bash
   # Para proyectos Node.js
   echo "node_modules/" > .gitignore
   echo ".env" >> .gitignore
   ```

4. **Haz tu primer commit**:
   ```bash
   git add .
   git commit -m "Configuración inicial del proyecto"
   ```

5. **Crea una rama para una nueva característica**:
   ```bash
   git checkout -b feature/estructura-base
   ```

6. **Añade algunos archivos de ejemplo**:
   ```bash
   mkdir src
   echo "console.log('Hola mundo');" > src/index.js
   echo ".container { padding: 20px; }" > src/styles.css
   ```

7. **Commit de los cambios**:
   ```bash
   git add .
   git commit -m "Añadida estructura base del proyecto"
   ```

8. **Vuelve a la rama principal y fusiona la característica**:
   ```bash
   git checkout main
   git merge feature/estructura-base
   ```

9. **Crea un repositorio en GitHub**:
   - Ve a GitHub y crea un nuevo repositorio
   - No inicialices el repositorio con ningún archivo

10. **Conecta tu repositorio local con GitHub**:
    ```bash
    git remote add origin git@github.com
