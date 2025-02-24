# Guía paso a paso para instalar, configurar y conectar Git con GitHub

## Paso 1: Instalación de Git

### Windows:

1. Descarga el instalador desde [git-scm.com](https://git-scm.com/download/win).
2. Ejecuta el instalador y sigue las instrucciones (recomendado usar Git Bash).

### macOS:

1. Abre la terminal.
2. Escribe el siguiente comando para instalar con Homebrew:

```bash
brew install git
```

### Linux (Ubuntu/Debian):

1. Abre la terminal.
2. Ejecuta:

```bash
sudo apt-get install git
```

### Verificar Instalación:

```bash
git --version
```

---

## Paso 2: Configuración Inicial

### Configurar tu nombre y correo electrónico:

```bash
git config --global user.name "Tu nombre"
git config --global user.email "tuemail@dominio.com"
```

### Configurar Visual Studio Code como editor por defecto:

```bash
git config --global core.editor "code --wait"
```

### Verificar configuración:

```bash
git config --list
```

---

## Paso 3: Primeros pasos con Git

### Crear un repositorio local:

1. Crea una carpeta para tu proyecto:

```bash
mkdir mi_proyecto
cd mi_proyecto
```

2. Inicializa un repositorio Git:

```bash
git init
```

### Agregar y guardar cambios:

1. Crea un archivo nuevo, por ejemplo:

```bash
touch README.md
```

2. Añade el archivo al área de preparación (Stage):

```bash
git add README.md
```

3. Realiza tu primer commit:

```bash
git commit -m "Primer commit - añade README"
```

### Verifica tu commit:

```bash
git log
```

---

## Paso 4: Conectar Git con GitHub

### Crear un repositorio remoto en GitHub:

1. Ingresa en [github.com](https://github.com) y crea una cuenta (si no tienes una).
2. Haz clic en "New Repository".
3. Asigna un nombre al repositorio (preferiblemente igual al de tu repositorio local).
4. Elige la configuración deseada (privado o público) y presiona "Create Repository".

### Vincular repositorio local con remoto:

1. Copia la URL del repositorio en GitHub (generalmente en formato HTTPS).

2. En tu terminal local, ejecuta:

```bash
git remote add origin <URL_del_repositorio>
```

### Autenticar Git con GitHub:

Desde agosto de 2021, GitHub ya no acepta autenticación por contraseña desde la terminal. Se debe usar autenticación basada en tokens (Personal Access Tokens - PAT).

1. En GitHub, ve a "Settings" > "Developer settings" > "Personal access tokens".
2. Haz clic en "Generate new token" y sigue las instrucciones, seleccionando permisos adecuados.
3. Copia y guarda el token generado (solo se muestra una vez).

### Subir cambios a GitHub:

1. Primero asegúrate de configurar tu rama principal como "main":

```bash
git branch -M main
```

2. Al realizar el primer push, introduce tu nombre de usuario de GitHub y, como contraseña, utiliza el token generado:

```bash
git push -u origin main
```

---

## Paso 5: Confirmar la conexión

- Revisa tu cuenta en GitHub, verifica que los archivos locales ahora aparecen en el repositorio remoto.

¡Listo! Ahora tienes Git configurado y conectado correctamente con GitHub.

