# Prueba técnica Craftech

Repositorio que contiene la resolución a los tres puntos de la prueba tecnica de Craftech. Cada una de las carpetas contiene un archivo README.md que explica como fue que se resolvió cada punto y tambien las instrucciones para poder ejecutarlos.

### Prueba 1 - Diagrama de Red

**Objetivo**: Produzca un diagrama de red (puede utilizar Lucidchart) de una aplicación web en GCP o AWS y escriba una descripción de texto de 1/2 a 1 página de sus elecciones y arquitectura.

**Requisitos**:
- El diseño debe soportar:
  - Cargas variables.
  - Contar con alta disponibilidad (HA).
  - Frontend en JavaScript.
  - Backend con una base de datos relacional y una no relacional.
  - La aplicación backend consume 2 microservicios externos.
- El diagrama debe hacer un mejor uso de las soluciones distribuidas.

### Prueba 2 - Despliegue de una aplicación Django y React.js

**Objetivo**: Elaborar el deployment dockerizado de una aplicación en Django (backend) con frontend en React.js contenida en el repositorio. Es necesario desplegar todos los servicios en un solo `docker-compose`.

**Requisitos**:
- Se deben entregar los Dockerfiles pertinentes para elaborar el despliegue y justificar la forma en la que elabora el deployment (supervisor, scripts, docker-compose, kubernetes, etc.).
- Subir todo lo elaborado a un repositorio (GitHub, GitLab, Bitbucket, etc.).
- En el repositorio se debe incluir el código de la aplicación y un archivo `README.md` con instrucciones detalladas para compilar y desplegar la aplicación, tanto en una PC local como en la nube (AWS o GCP).

### Prueba 3 - CI/CD Dockerizar un Nginx con el index.html Default

**Objetivo**: Elaborar un pipeline que, ante cada cambio realizado sobre el `index.html`, construya la nueva imagen y la actualice en la plataforma elegida (docker-compose, swarm, kubernetes, etc.). Para la creación del CI/CD se puede utilizar cualquier plataforma (CircleCI, GitLab, GitHub, Bitbucket).

**Requisitos y Deseables**:
- La solución al ejercicio debe mostrar que usted puede:
  - Automatizar la parte del proceso de despliegue.
  - Usar conceptos de CI para aprovisionar el software necesario para que los entregables se ejecuten.
  - Usar cualquier herramienta de CI de su elección para implementar el entregable.

