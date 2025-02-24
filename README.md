# CURSO-BASICO-GIT

# Curso Básico de Git para Novatos

## 1. Introducción
Git es un sistema de control de versiones distribuido esencial para los desarrolladores de software. A menudo confundido con GitHub, ambos conceptos son diferentes: **Git** gestiona las versiones del código, mientras que **GitHub** aloja estos proyectos en línea y facilita la colaboración.

**Sitio web oficial:** [git-scm.com](https://git-scm.com)

### Conceptos Iniciales
- **Git:** Herramienta distribuida para gestionar versiones de código.
- **GitHub:** Plataforma web para alojar proyectos gestionados con Git.

### Recursos Adicionales
- [Libro gratuito Pro Git en español](https://git-scm.com/book/es/v2)

---

## 1.2 Historia

El control de versiones permite coordinar equipos de desarrollo y mantener un historial claro del proyecto. Git, creado por Linus Torvalds en 2005 tras perder acceso a BitKeeper, fue diseñado inicialmente para el kernel Linux, extendiéndose rápidamente a otros proyectos.

### Ventajas de Git
- **Distribuido:** Copia completa del repositorio en cada equipo.
- **Gestión de ramas:** Facilita creación, comparación y fusión.
- **Flexibilidad:** Adaptable a distintos flujos de trabajo.
- **Código abierto:** Gratuito, con soporte de una gran comunidad.

---

## 1.3 Instalación

### Windows
- Descargar desde [git-scm.com/download/win](https://git-scm.com/download/win)
- Incluye Git Bash, terminal compatible con Git.

### macOS
Usando Homebrew:
```bash
brew install git
```

### Linux
- Ubuntu/Debian:
```bash
sudo apt-get install git
```
- Fedora:
```bash
sudo dnf install git
```

### Verificación
- Comprobar instalación:
```bash
git --version
```

### Clientes Gráficos y Alternativas
Opciones gráficas: GitHub Desktop, GitKraken, Sourcetree, Fork. Integración con editores como VS Code o IntelliJ IDEA.

---

## 1.4 Comandos Básicos en Terminal
- `ls`: Lista archivos.
- `cd`: Cambia de directorio.
- `pwd`: Muestra ruta actual.
- `mkdir`: Crea carpetas.
- `touch`: Crea archivos vacíos.
- `rm`: Elimina archivos/carpetas.
- `cp`: Copia archivos.
- `mv`: Mueve archivos.

---

## 1.5 Configuración
Configurar usuario y correo en Git:
```bash
git config --global user.name "Tu nombre"
git config --global user.email "tuemail@dominio.com"
```

### Editor predeterminado VS Code:
```bash
git config --global core.editor "code --wait"
```

---

## 1.6 Inicialización de un repositorio
Crear repositorio local:
```bash
git init
```

Esto crea una carpeta `.git` para el control de versiones.

---

## 1.7 Ramas
- Configurar rama principal por defecto como "main":
```bash
git config --global init.defaultBranch main
```
- Cambiar nombre de rama actual:
```bash
git branch -m main
```

Las ramas permiten desarrollar funcionalidades independientes que luego se fusionan a la rama principal.

---

## 1.8 Guardar Cambios
- Ver estado de archivos:
```bash
git status
```
- Añadir archivos a Stage:
```bash
git add <archivo>
```
o
```bash
git add .
```
- Realizar un commit:
```bash
git commit -m "Mensaje descriptivo"
```

Cada commit captura el estado actual del proyecto, generando un historial organizado.

---

## 1.9 Verificación y Estado
- Ver historial de commits:
```bash
git log
```
- Estado actual del repositorio:
```bash
git status
```

### Concepto de HEAD
Indica el commit actual, moviéndose con cada nuevo commit realizado.

---

## Conclusión
Dominar Git mejora significativamente la eficiencia en desarrollo y colaboración. Continuar explorando la documentación oficial ayudará a profundizar aún más en sus funcionalidades avanzadas.

