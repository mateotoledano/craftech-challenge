# Prueba 3 - CI/CD

Para resolver el challenge-3 hice lo siguiente:

### 1. Preparación del Entorno
- **Estructura de Carpetas**:
  - Primero, creé una carpeta llamada `github/workflows` en la raíz del proyecto para guardar el archivo de configuración del pipeline. Esto ayuda a organizar todo mejor y hacer que los procesos automáticos sean más fáciles de manejar.

### 2. Creación del Archivo de Pipeline
- **Archivo `ci-cd-pipeline.yml`**:
  - En la carpeta `github/workflows`, añadí un archivo llamado `ci-cd-pipeline.yml`. Este archivo dice qué pasos deben seguirse automáticamente cada vez que se haga un cambio en el `index.html`.

### 3. Creación del Dockerfile
- **Dockerfile en `challenge-3`**:
  - Dentro de la carpeta `challenge-3`, cree un archivo `Dockerfile`. Este archivo explica cómo crear una imagen de Docker para el servidor nginx usando el archivo `index.html` que viene por defecto. Incluye instrucciones para instalar nginx y colocar el `index.html` en el lugar correcto dentro del contenedor.

### 4. Configuración del Docker Compose
- **Archivo `docker-compose.yml` en `challenge-3`**:
  - También en `challenge-3`, creé un archivo llamado `docker-compose.yml`. Este archivo especifica cómo se deben configurar y ejecutar los servicios necesarios para el nginx en un contenedor. Definí el servicio nginx y configuré que se construya usando el Dockerfile.

### 5. Automatización del Pipeline CI/CD
- **Configuración del Pipeline**:
  - En `ci-cd-pipeline.yml`, configuré los pasos del pipeline usando una herramienta de CI (como GitHub Actions). Definí qué eventos deben activar el pipeline, como cada vez que se haga un cambio en la rama principal del repositorio.
  - Los pasos incluyen:
    - **Construir la imagen Docker**: Usando el Dockerfile, se crea una nueva imagen con el `index.html` actualizado.
    - **Subir la imagen a la plataforma de contenedores**: Configuré para que la nueva imagen se suba automáticamente a Docker Hub u otro servicio de contenedores.

## 6. Justificacion Docker-Compose
- **Simplicidad y Eficiencia**:
  - Elegí Docker-Compose porque es fácil de usar y ayuda a manejar aplicaciones con varios contenedores. Docker-Compose permite definir todo lo que se necesita para el despliegue en un solo archivo `docker-compose.yml`, lo que hace más fácil configurar y ejecutar los servicios.
- **Facilidad para Probar y Desplegar**:
  - Docker-Compose hace que la configuración sea fácil de copiar y usar en diferentes entornos, lo que es perfecto para pruebas y despliegues continuos. Puedes definir todos los servicios que necesita la aplicación, incluidos volúmenes y redes, en un solo lugar.

Con estos pasos, conseguí automatizar el despliegue de la nueva imagen de nginx con el `index.html` actualizado cada vez que hay un cambio, usando Docker y Docker-Compose para gestionar los contenedores y hacer más fácil el despliegue. La integración con CI asegura que el proceso sea rápido y sencillo.
