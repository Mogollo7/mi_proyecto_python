# 🌿 Proyecto Flask - Naturaleza & Experiencia Web

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0.0-000000?style=for-the-badge&logo=flask&logoColor=white)
![Render](https://img.shields.io/badge/Render-Deployed-46E3B7?style=for-the-badge&logo=render&logoColor=white)
![Licencia](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

Una aplicación web construida con **Python** y **Flask**, con una interfaz
propia (branding en tono índigo, tipografía clara, componentes planos) y
gráficos vectoriales **SVG**. Además de servir la interfaz real, la página
documenta de forma explicativa una arquitectura de software propuesta y su
stack tecnológico, e incluye un cuestionario de repaso sobre esa teoría.

---

## 🔗 Enlaces

- **Repositorio (GitHub):** <https://github.com/Mogollo7/mi_proyecto_python>
- **Fork base:** <https://github.com/g3in-unilasallista/mi_proyecto_python/forks>
- **Demo en vivo (Render):** <https://mi-proyecto-python-03d8.onrender.com>

---

## 🛠️ Tecnologías Utilizadas

- **Backend**: Python 3, Flask, Gunicorn
- **Frontend**: HTML5, Vanilla CSS3 (Variables CSS, Flexbox, CSS Grid, componentes planos, micro-animaciones)
- **Recursos**: SVG Vectorial puro, Google Fonts (*Space Grotesk*, *Inter* & *JetBrains Mono*)
- **Despliegue**: Render, Git & GitHub

---

## 📁 Estructura de carpetas

```text
mi_proyecto_python/
├── app.py                 # Servidor Flask real de esta página
├── requirements.txt       # Dependencias reales (Flask, Gunicorn)
├── Procfile                # Comando de arranque para Render
├── templates/
│   └── index.html         # Página real (incluye contenido explicativo)
├── evidencias/             # Evidencias reales del proyecto (capturas, comandos)
├── LICENSE
└── README.md               # Esta documentación
```

---

## 🚀 Aprende a Replicar este Proyecto

Guía paso a paso para construir la aplicación en tu propia máquina.

### Paso 1: Instalar Python y Git
Asegúrate de tener Python 3.10+ y Git instalados en tu sistema operativo.

```bash
# Verificar la versión de Python
python --version

# Verificar la versión de Git
git --version
```

---

### Paso 2: Crear la Estructura de Carpetas
Crea la carpeta de tu proyecto y entra en ella:

```bash
mkdir mi_proyecto_python
cd mi_proyecto_python
```

---

### Paso 3: Crear y Activar el Entorno Virtual (`.venv`)
El entorno virtual aísla las librerías de tu proyecto para no afectar tu computadora.

```bash
# Crear entorno virtual
python -m venv .venv

# Activar en Windows (PowerShell)
.\.venv\Scripts\Activate.ps1

# Activar en Mac/Linux
source .venv/bin/activate
```

---

### Paso 4: Crear `requirements.txt` e Instalar Dependencias
Guarda tus dependencias en `requirements.txt` (incluyendo `gunicorn` para el despliegue):

```bash
# Escribir las dependencias
echo Flask>=3.0.0 > requirements.txt
echo gunicorn>=21.2.0 >> requirements.txt

# Instalar dependencias
pip install -r requirements.txt
```

---

### Paso 5: Crear el Servidor Flask (`app.py`)
Crea el archivo `app.py` que controlará las rutas de tu servidor:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route('/')
def home():
    return render_template('index.html')

if __name__ == '__main__':
    app.run(debug=True)
```
---


## 🌐 Despliegue en la Nube (Render)

### ¿Qué es Gunicorn y el archivo `Procfile`?

1. **¿Qué es Gunicorn?**  
   El servidor integrado de Flask (`app.run()`) es solo para pruebas locales. **Gunicorn** es un servidor WSGI de grado de producción diseñado para procesar múltiples peticiones de forma rápida, segura y estable cuando tu aplicación está en producción en internet.

2. **¿Qué es el archivo `Procfile`?**  
   Es un archivo de texto simple sin extensión que indica a plataformas en la nube como Render o Heroku qué comando ejecutar para iniciar la aplicación web. Contiene:
   ```text
   web: gunicorn app:app
   ```
   *(El primer `app` es el archivo `app.py` y el segundo `app` es la variable de la aplicación `app = Flask(__name__)`).*

---

### Pasos para Desplegar en Render con GitHub

1. **Crear el archivo `Procfile` en la raíz del proyecto:**
   ```bash
   echo web: gunicorn app:app > Procfile
   ```

2. **Subir tu proyecto a GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Primer commit: Proyecto Flask Naturaleza"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/TU_REPOSITTORIO.git
   git push -u origin main
   ```

3. **Configurar en Render:**
   - Entra a [Render.com](https://render.com) e inicia sesión.
   - Haz clic en **`+ New`** -> **`Web Service`**.
   - Conecta tu cuenta de **GitHub** y selecciona tu repositorio.
   - Llena la configuración con estos valores:
     - **Name**: `mi-proyecto-flask`
     - **Runtime**: `Python 3`
     - **Build Command**: `pip install -r requirements.txt`
     - **Start Command**: `gunicorn app:app`
   - Haz clic en **Create Web Service**. ¡Listo! Render te dará un enlace público HTTPS para acceder a tu sitio web desde cualquier dispositivo.

---

## 🧭 Arquitectura y stack documentados en la página

La página (`templates/index.html`) incluye, a partir de esta versión, una sección
explicativa sobre una **arquitectura de software propuesta** para escalar el
proyecto, y sobre el **stack tecnológico documentado** para esa propuesta:

- **Python** — lenguaje descrito para los servicios backend de la arquitectura
  propuesta (y, además, lenguaje real del backend actual de esta página).
- **FastAPI** — framework de Python documentado para construir la API y los
  servicios backend propuestos.
- **Vite** — herramienta de desarrollo y construcción documentada para un
  futuro frontend desacoplado.
- **PostgreSQL** — sistema de gestión de base de datos relacional documentado
  para la persistencia de los servicios propuestos.
- **Arquitectura de microservicios** — organización conceptual en servicios
  independientes, desplegables y escalables por separado.
- **Render** — plataforma de despliegue, tanto de esta página real como,
  documentalmente, de la arquitectura propuesta.

> **Importante:** la arquitectura y el stack anteriores se presentan como
> **contenido explicativo** dentro de la página estática y **no forman parte
> de la implementación interna** de esta página, salvo las tecnologías que ya
> pertenecen al proyecto original (Python, Flask, Gunicorn, Render, HTML5,
> CSS3 y SVG). Esta página **no** ejecuta FastAPI, **no** tiene una base de
> datos PostgreSQL y **no** está dividida en microservicios: sigue siendo un
> sitio servido por Flask que renderiza una única plantilla Jinja2.

La página también incluye una sección **Cuestionario** con 10 preguntas de
repaso (formato pregunta/respuesta desplegable, sin JavaScript) sobre esta
misma teoría: Python, Flask vs. FastAPI, Vite, PostgreSQL, microservicios,
Render y Gunicorn.

## 📁 Evidencias

La carpeta [`evidencias/`](evidencias/) contiene evidencias reales del
proyecto:

- `image.png` — repositorio `mi_proyecto_python` en GitHub (fork sincronizado
  con `main`).
- `Captura de pantalla 2026-09-18 112401.png` — activación del entorno
  virtual e instalación de dependencias (`pip install -r requirements.txt`).
- `Captura de pantalla 2026-09-18 112419.png` — ejecución real del servidor
  con `python app.py`.
- `comandos-ejecutados.txt` — registro de los comandos ejecutados y sus
  resultados reales durante la validación de esta versión de la página
  (creación del entorno virtual, instalación de dependencias, arranque del
  servidor y verificación funcional/responsive).



---

### 👤 Autor
**Juan Sebastian Martinez Galeano**
