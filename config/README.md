# Sistema de Titulación - Configuración Docker

Este repositorio contiene la orquestación necesaria para levantar el entorno de desarrollo del Sistema de Titulación utilizando Docker Compose.

## Requisitos Previos

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Estructura del Proyecto

Se asume la siguiente estructura de directorios:
```text
sistema_titulacion/
├── backend/    # Código fuente de Django (debe contener un Dockerfile)
├── frontend/   # Código fuente de React (debe contener un Dockerfile)
└── config/     # Archivo docker-compose.yml y este README
```

## Servicios

El archivo `docker-compose.yml` levanta los siguientes servicios:

| Servicio | Tecnología | Puerto | Descripción |
|----------|------------|--------|-------------|
| `db` | PostgreSQL | 5432 | Base de datos principal. |
| `pgadmin` | pgAdmin 4 | 5050 | Interfaz web para administrar PostgreSQL. |
| `backend` | Django | 8000 | API del sistema. |
| `frontend` | React | 3000 | Interfaz de usuario. |

## Instrucciones de Uso

### 1. Levantar los servicios

Desde la carpeta `config/`, ejecuta:

```bash
docker-compose up --build
```

### 2. Acceso a las aplicaciones

- **Frontend:** [http://localhost:3000](http://localhost:3000)
- **Backend (API):** [http://localhost:8000](http://localhost:8000)
- **pgAdmin:** [http://localhost:5050](http://localhost:5050)
  - **Usuario:** `admin@admin.com`
  - **Contraseña:** `admin`

### 3. Configuración de la Base de Datos en pgAdmin

Al entrar a pgAdmin, para conectarte a la base de datos utiliza:
- **Host name/address:** `db`
- **Port:** `5432`
- **Maintenance database:** `sistema_titulacion`
- **Username:** `postgres`
- **Password:** `postgres`

## Notas Adicionales

- Los datos de la base de datos persistirán en un volumen de Docker llamado `postgres_data`.
- Asegúrate de configurar correctamente las variables de entorno en Django para usar los parámetros de conexión definidos en el `docker-compose.yml`.
