
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

Accede a la aplicación en \`http://127.0.0.1:8000/\`.

## Despliegue con Docker

### 1. Construir y Ejecutar los Contenedores

\`\`\`bash
$ docker-compose up --build
\`\`\`

Esto lanzará la aplicación junto con los servicios configurados en el \`docker-compose.yml\`, incluyendo Nginx y Gunicorn.

### 2. Acceder a la Aplicación

La aplicación estará disponible en \`http://localhost\` si estás corriendo los contenedores en un entorno local.

## Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo [LICENSE.md](LICENSE.md) para más detalles.

---

Desarrollado por **Christopher Porras**.
