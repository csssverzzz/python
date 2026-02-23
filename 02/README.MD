# Capítulo 02: Usando el intérprete de Python — Guía Completa

> *"La mejor forma de aprender Python es usarlo. Juega con el intérprete mientras lees."*  
> — Tutorial oficial de Python

---

##  Tabla de contenidos
- [¿Qué es el intérprete?](#-qué-es-el-intérprete)
- [ Instalación por plataforma](#️-instalación-por-plataforma)
  - [Windows](#windows)
  - [macOS](#macos)
  - [Linux](#linux)
  - [Verificación de instalación](#verificación-de-instalación)
- [ Invocar el intérprete](#️-invocar-el-intérprete)
  - [Diferencias: `python` vs `python3` vs `py`](#diferencias-python-vs-python3-vs-py)
  - [Rutas típicas de instalación](#rutas-típicas-de-instalación)
  - [Opciones de línea de comandos esenciales](#opciones-de-línea-de-comandos-esenciales)
- [ Salir del intérprete](#-salir-del-intérprete)
- [ Edición interactiva avanzada](#️-edición-interactiva-avanzada)
  - [readline y rlcompleter](#readline-y-rlcompleter)
  - [Historial persistente](#historial-persistente)
  - [Personalización con PYTHONSTARTUP](#personalización-con-pythonstartup)
- Modos de ejecución](#-modos-de-ejecución)
  - [Modo interactivo (REPL)](#modo-interactivo-repl)
  - [Ejecutar scripts](#ejecutar-scripts)
  - [`-c`: comandos en línea](#-c-comandos-en-línea)
  - [`-m`: módulos como scripts](#-m-módulos-como-scripts)
  - [`-i`: modo interactivo post-script](#-i-modo-interactivo-post-script)
  - [`-q`: modo silencioso](#-q-modo-silencioso)
  - [`-v`: modo verbose](#-v-modo-verbose)
- [ Gestión de argumentos (`sys.argv`)](#-gestión-de-argumentos-sysargv)
- [ Codificación de archivos fuente](#-codificación-de-archivos-fuente)
  - [UTF-8 por defecto](#utf-8-por-defecto)
  - [Declaración explícita de codificación](#declaración-explícita-de-codificación)
  - [Problemas comunes en Windows](#problemas-comunes-en-windows)
- [ Entornos virtuales (`venv`)](#-entornos-virtuales-venv)
- [ Variables de entorno clave](#-variables-de-entorno-clave)
- [ Ayuda interactiva integrada](#-ayuda-interactiva-integrada)
- [ REPL mejorado: IPython y Jupyter](#-repl-mejorado-ipython-y-jupyter)
- [ Troubleshooting común](#️-troubleshooting-común)
- [ Checklist de buenas prácticas](#-checklist-de-buenas-prácticas)
- [ Recursos y referencias](#-recursos-y-referencias)

---

##  ¿Qué es el intérprete?

El **intérprete de Python** es el motor ejecutable (`python`, `python3`, `py.exe`) que:

| Característica          | Descripción                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| **Ejecución dinámica**  | Lee y ejecuta código línea por línea sin compilación previa                 |
| **REPL integrado**      | *Read-Eval-Print Loop*: entorno interactivo para experimentar en tiempo real |
| **Multiplataforma**     | Mismo comportamiento en Windows, macOS, Linux y otros sistemas Unix-like    |
| **Multiimplementación** | CPython (oficial), PyPy (JIT), Jython (JVM), IronPython (.NET)             |
| **Extensible**          | Puede incrustarse en aplicaciones C/C++ como motor de scripting             |

>  **Ventaja clave**: Itera en segundos en lugar de minutos. Ideal para prototipado rápido, automatización y aprendizaje interactivo.

---

##  Instalación por plataforma

### Windows
| Método                          | Comando/Proceso                                                                 | Ventajas                                  |
|---------------------------------|---------------------------------------------------------------------------------|-------------------------------------------|
| **Microsoft Store**             | Buscar "Python 3.14" → Instalar                                                 | Actualizaciones automáticas               |
| **Instalador oficial (.exe)**   | Descargar de [python.org](https://python.org/downloads/) → ✅ *"Add to PATH"*   | Control total de instalación              |
| **Chocolatey**                  | `choco install python --version=3.14`                                           | Gestión centralizada de paquetes          |
| **Scoop**                       | `scoop install python`                                                          | Instalación sin privilegios de admin      |

>  **¡Importante!** Durante la instalación marca la casilla **"Add Python to PATH"**. Sin esto, el comando `python` no funcionará en PowerShell/CMD.

### macOS
| Método                | Comando                                                                 | Notas                                     |
|-----------------------|-------------------------------------------------------------------------|-------------------------------------------|
| **Homebrew**          | `brew install python@3.14`                                              | Recomendado (no usa Python de Apple)   |
| **Instalador .pkg**   | Descargar de [python.org](https://python.org/downloads/)                | Ruta típica: `/Library/Frameworks/...`    |
| **pyenv**             | `pyenv install 3.14.0 && pyenv global 3.14.0`                           | Gestión de múltiples versiones            |

>  **Advertencia**: macOS incluye Python 2.7 en `/usr/bin/python` (obsoleto). **Nunca lo uses**. Siempre usa `python3`.

### Linux (Debian/Ubuntu)
```bash
# Instalación mínima
sudo apt update
sudo apt install python3 python3-venv python3-pip

# Para desarrollo completo
sudo apt install python3-dev build-essential libssl-dev zlib1g-dev

# Verificar versión
python3 --version
# Salida esperada: Python 3.14.0