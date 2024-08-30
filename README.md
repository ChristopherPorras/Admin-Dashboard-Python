
# Admin Dashboard Python

![Admin Dashboard](https://via.placeholder.com/1000x500.png?text=Admin+Dashboard)

Este proyecto es un **Admin Dashboard** desarrollado en Python utilizando Django, diseñado para proporcionar una interfaz intuitiva y eficiente para la gestión de datos y procesos administrativos.

## Características

- **Panel de Control**: Vista centralizada de métricas clave y estadísticas.
- **Gestión de Usuarios**: Administración de roles y permisos.
- **Seguridad**: Autenticación y autorización de usuarios.
- **Integración con Docker**: Facilita el despliegue y la escalabilidad.
- **Soporte para Nginx y Gunicorn**: Configurado para un entorno de producción robusto.

## Tecnologías Utilizadas

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Django](https://img.shields.io/badge/Django-3.x-green.svg)
![Docker](https://img.shields.io/badge/Docker-Enabled-blue.svg)
![Nginx](https://img.shields.io/badge/Nginx-Configured-green.svg)
![Gunicorn](https://img.shields.io/badge/Gunicorn-Configured-yellow.svg)

- **Python**: Lenguaje principal de desarrollo.
- **Django**: Framework web utilizado para construir la aplicación.
- **Docker**: Utilizado para contenedorización, facilitando la implementación y el escalado.
- **Nginx**: Servidor web utilizado para manejar las solicitudes HTTP.
- **Gunicorn**: Servidor de aplicaciones WSGI para servir aplicaciones Python.

## Estructura del Proyecto

\`\`\`bash
< PROJECT ROOT >
   ├── core/                            # Configuración principal y enrutamiento del proyecto
   ├── home/                            # Lógica de la aplicación, incluyendo vistas y modelos
   ├── static/                          # Archivos estáticos como CSS y JS
   ├── templates/                       # Plantillas HTML para renderizar las vistas
   ├── Dockerfile                       # Definición del contenedor Docker
   ├── docker-compose.yml               # Configuración de servicios Docker
   ├── nginx/                           # Configuración de Nginx
   ├── gunicorn-cfg.py                  # Configuración de Gunicorn
   ├── requirements.txt                 # Dependencias del proyecto
   ├── manage.py                        # Script para manejar tareas administrativas en Django
   └── README.md                        # Documentación del proyecto
\`\`\`

## Instalación y Configuración

### 1. Clonar el Repositorio

\`\`\`bash
$ git clone https://github.com/ChristopherPorras/Admin-Dashboard-Python.git
$ cd Admin-Dashboard-Python
\`\`\`

### 2. Configurar el Entorno Virtual

\`\`\`bash
$ virtualenv env
$ source env/bin/activate
$ pip install -r requirements.txt
\`\`\`

### 3. Configurar las Variables de Entorno

Copia el archivo \`env.sample\` y renómbralo a \`.env\`, luego ajusta las variables de entorno según sea necesario.

### 4. Migrar la Base de Datos

\`\`\`bash
$ python manage.py makemigrations
$ python manage.py migrate
\`\`\`

### 5. Crear un Superusuario

\`\`\`bash
$ python manage.py createsuperuser
\`\`\`

### 6. Iniciar la Aplicación

\`\`\`bash
$ python manage.py runserver
\`\`\`

At this point, the app runs at `http://127.0.0.1:8000/`. 

<br />

## Codebase structure

The project is coded using a simple and intuitive structure presented below:

```bash
< PROJECT ROOT >
   |
   |-- core/                            
   |    |-- settings.py                  # Project Configuration  
   |    |-- urls.py                      # Project Routing
   |
   |-- home/
   |    |-- views.py                     # APP Views 
   |    |-- urls.py                      # APP Routing
   |    |-- models.py                    # APP Models 
   |    |-- tests.py                     # Tests  
   |    |-- templates/                   # Theme Customisation 
   |         |-- includes                # 
   |              |-- custom-footer.py   # Custom Footer      
   |     
   |-- requirements.txt                  # Project Dependencies
   |
   |-- env.sample                        # ENV Configuration (default values)
   |-- manage.py                         # Start the app - Django default start script
   |
   |-- ************************************************************************
```

<br />

## How to Customize 

When a template file is loaded in the controller, `Django` scans all template directories starting from the ones defined by the user, and returns the first match or an error in case the template is not found. 
The  theme used to style this starter provides the following files: 

```bash
# This exists in ENV: LIB/admin_star
< UI_LIBRARY_ROOT >                      
   |
   |-- templates/                     # Root Templates Folder 
   |    |          
   |    |-- accounts/       
   |    |    |-- login.html           # Sign IN Page
   |    |    |-- register.html        # Sign UP Page
   |    |
   |    |-- includes/       
   |    |    |-- footer.html          # Footer component
   |    |    |-- sidebar.html         # Sidebar component
   |    |    |-- navigation.html      # Navigation Bar
   |    |    |-- scripts.html         # Scripts Component
   |    |
   |    |-- layouts/       
   |    |    |-- base.html            # Masterpage
   |    |    |-- base-auth.html       # Masterpage for Auth Pages
   |    |
   |    |-- pages/       
   |         |-- index.html           # Dashboard Page
   |         |-- *.html               # All other pages
   |    
   |-- ************************************************************************
```

When the project requires customization, we need to copy the original file that needs an update (from the virtual environment) and place it in the template folder using the same path. 

> For instance, if we want to **customize the footer.html** these are the steps:

- ✅ `Step 1`: create the `templates` DIRECTORY inside the `home` app
- ✅ `Step 2`: configure the project to use this new template directory
  - `core/settings.py` TEMPLATES section
- ✅ `Step 3`: copy the `footer.html` from the original location (inside your ENV) and save it to the `home/templates` DIR
  - Source PATH: `<YOUR_ENV>/LIB/admin_star/template/includes/footer.html`
  - Destination PATH: `<PROJECT_ROOT>home/templates/includes/footer.html`

> To speed up all these steps, the **codebase is already configured** (`Steps 1, and 2`) and a `custom footer` can be found at this location:

`home/templates/includes/custom_footer.html` 

By default, this file is unused because the `theme` expects `footer.html` (without the `custom-` prefix). 

In order to use it, simply rename it to `footer.html`. Like this, the default version shipped in the library is ignored by Django. 

In a similar way, all other files and components can be customized easily.

<br />

## Deploy on [Render](https://render.com/)

- Create a Blueprint instance
  - Go to https://dashboard.render.com/blueprints this link.
- Click `New Blueprint Instance` button.
- Connect your `repo` which you want to deploy.
- Fill the `Service Group Name` and click on `Update Existing Resources` button.
- After that your deployment will start automatically.

At this point, the product should be LIVE.

<br />


![Argon Dashboard 2 PRO - Automotive (Premium Bootstrap 5 Design).](https://user-images.githubusercontent.com/51070104/211158013-fea76b79-bb54-4066-a617-5ec3b4b6ec42.jpg)

<br />

---
[Django Star Admin](https://appseed.us/product/star-admin/django/) - **Django** Starter provided by **[AppSeed](https://appseed.us/)**
