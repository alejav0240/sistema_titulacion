# Sistema de Titulación

Este es el repositorio principal del **Sistema de Titulación**, un proyecto estructurado mediante microservicios/componentes utilizando submódulos de Git para gestionar el frontend y el backend de forma independiente.

## 🏗️ Estructura del Proyecto

El proyecto está dividido en los siguientes módulos:

*   **[sistema_titulacion_backend](./sistema_titulacion_backend)**: API robusta desarrollada con Django (Python).
*   **[sistema_titulacion_frontend](./sistema_titulacion_frontend)**: Interfaz de usuario moderna construida con React (TypeScript) y Vite.
*   **[config](./config)**: Configuraciones compartidas, esquemas de base de datos (DBML) y despliegue local.

## 🚀 Inicio Rápido

### 1. Clonar el repositorio
Para clonar este proyecto junto con todos sus componentes (submódulos), utiliza:

```bash
git clone --recursive git@github.com:alejav0240/sistema_titulacion.git
cd sistema_titulacion
```

Si ya clonaste el repo sin los submódulos, inicialízalos con:
```bash
git submodule update --init --recursive
```

### 2. Actualizar componentes
Los submódulos están configurados para seguir la rama `main`. Para traer las últimas actualizaciones de todos los componentes:

```bash
git submodule update --remote --merge
```

### 3. Ejecución con Docker
El proyecto está preparado para correr con Docker Compose. Asegúrate de tener Docker y Docker Compose instalados.

```bash
docker-compose up --build
```

## 🛠️ Desarrollo

### Backend
Consulta el [README del Backend](./sistema_titulacion_backend/README.md) para detalles sobre migraciones y configuración de Django.

### Frontend
Consulta el [README del Frontend](./sistema_titulacion_frontend/README.md) para detalles sobre comandos de desarrollo y construcción.

## 📝 Notas de Git
Este repositorio utiliza submódulos. Al realizar cambios dentro de las carpetas `sistema_titulacion_backend` o `sistema_titulacion_frontend`, recuerda hacer commit dentro de ellas y luego actualizar la referencia en este repositorio raíz.
