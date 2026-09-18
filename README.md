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

### Paso 6: Crear la Plantilla HTML con Tema de Naturaleza
Crea una carpeta llamada `templates` y dentro crea el archivo `index.html`:

```bash
mkdir templates
```

Crea `templates/index.html` con la interfaz centrada, tipografía y gráficos SVG integrados:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bienvenido a la Naturaleza | Flask App</title>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;600;700;800&family=Playfair+Display:ital,wght@0,600;0,800;1,400&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-gradient: linear-gradient(135deg, #0b2b1a 0%, #1b4332 40%, #2d6a4f 100%);
            --card-bg: rgba(255, 255, 255, 0.08);
            --card-border: rgba(255, 255, 255, 0.15);
            --primary-light: #d8f3dc;
            --accent-sage: #95d5b2;
            --accent-green: #52b788;
            --text-main: #f8f9fa;
            --text-sub: #b7e4c7;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
            background: var(--bg-gradient);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--text-main);
            padding: 20px;
        }

        .container {
            max-width: 900px;
            width: 100%;
            background: var(--card-bg);
            backdrop-filter: blur(16px);
            border: 1px solid var(--card-border);
            border-radius: 28px;
            padding: 60px 40px;
            text-align: center;
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.35);
        }

        h1 {
            font-family: 'Playfair Display', serif;
            font-size: 3.5rem;
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff 30%, var(--accent-sage) 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 16px;
        }

        .subtitle {
            font-size: 1.25rem;
            color: var(--text-sub);
            margin-bottom: 40px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
        }

        .feature-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.08);
            border-radius: 20px;
            padding: 28px 20px;
            transition: all 0.3s ease;
        }

        .feature-card:hover {
            transform: translateY(-6px);
            border-color: var(--accent-green);
        }

        .card-icon {
            width: 44px;
            height: 44px;
            margin-bottom: 16px;
            fill: var(--accent-green);
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- SVG Principal -->
        <svg style="width:64px; height:64px; fill:#95d5b2; margin-bottom:20px;" viewBox="0 0 24 24">
            <path d="M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M12,4A8,8 0 0,1 20,12C20,14.4 18.9,16.5 17.2,18C15.8,16.6 13.9,15.6 12,15.6C10.1,15.6 8.2,16.6 6.8,18C5.1,16.5 4,14.4 4,12A8,8 0 0,1 12,4Z"/>
        </svg>

        <h1>¡Bienvenido a la Experiencia Flask!</h1>
        <p class="subtitle">Tu aplicación en Python está lista y conectada en un entorno de naturaleza.</p>

        <div class="features-grid">
            <div class="feature-card">
                <svg class="card-icon" viewBox="0 0 24 24"><path d="M17,8C8,10 59,16.17 3.82,21.34L5.23,22.75C11.4,17.58 14,9 17,8M12.43,15.58C12.12,14.6 11.5,13.62 10.5,12.75C8.16,10.68 4.79,10.29 2,11C2.5,13.88 3.5,17 6.5,18.88C8.13,19.9 9.89,20 11.38,19.62L12.43,15.58M17,3C12,3 8.44,6.25 7.08,9.77C9.37,9.75 11.83,10.5 13.75,12.2C15.67,13.9 16.5,16.32 16.29,18.61C19.68,16.94 22,13.2 22,8.5C22,5.4 19.5,3 17,3Z"/></svg>
                <h3>Diseño Orgánico</h3>
                <p>Paletas inspiradas en la naturaleza.</p>
            </div>
            <div class="feature-card">
                <svg class="card-icon" viewBox="0 0 24 24"><path d="M14,6L10.25,11L13.1,14.8L11.5,16C9.81,13.75 7,10 7,10L1,18H23L14,6Z"/></svg>
                <h3>Estructura Firme</h3>
                <p>Potenciado por Python y Flask.</p>
            </div>
        </div>
        <p align="center" style="margin-top: 30px;">Creado por Juan Sebastian Martinez Galeano</p>
    </div>

</body>
</html>
```

---

### Paso 7: Ejecutar el Servidor Web Localmente
Corre tu servidor con Python:

```bash
python app.py
```

Abre tu navegador en:  
`http://127.0.0.1:5000/`

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

Estas evidencias viven **únicamente en este README** (y en la carpeta
`evidencias/` del repositorio); la página web ya no incluye una sección de
evidencias, para mantener la interfaz enfocada en el proyecto, su
arquitectura y el cuestionario de repaso.

---

### 👤 Autor
**Juan Sebastian Martinez Galeano**
