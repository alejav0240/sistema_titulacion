# Arquitectura del Backend - Sistema de Titulación

Esta arquitectura define la estructura del backend desarrollado en **Django**, basada en el esquema de datos definido en `Base.dbml`.

## 🏗️ Estructura de Capas

<div align="center">
  <table style="width:100%; border-collapse: collapse; text-align: center; font-family: sans-serif;">
    <tr style="background-color: #2d5900; color: white;">
      <th style="padding: 10px; border: 1px solid #ddd;">Capa</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Componentes Django</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Responsabilidad</th>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">API / Entry Point</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Views (DRF), URLs</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Manejo de peticiones HTTP y enrutamiento.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">Lógica de Negocio</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Serializers, Services</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Validación de datos y reglas de negocio del sistema de titulación.</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">Persistencia</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Models (ORM)</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Definición de tablas (Usuarios, Proyectos, Versiones) y relaciones.</td>
    </tr>
  </table>
</div>

## 🗄️ Modelos Principales (Mapeo DBML)

A partir del archivo `Base.dbml`, el backend implementa los siguientes módulos:

1.  **Gestión de Usuarios**:
    *   `Usuario`: Manejo de autenticación, roles y estado activo.
    *   `Notificaciones`: Sistema de alertas para usuarios según prioridad.
2.  **Gestión Académica**:
    *   `Materia`, `EstudianteMateria`: Organización de grupos y asignación de docentes.
    *   `TutorTribunal`: Relación entre estudiantes y docentes para la guía del proyecto.
3.  **Proyectos de Grado**:
    *   `ProyectoDeGrado`: Cabecera del proyecto y estado general.
    *   `Versiones`: Seguimiento de archivos PDF y estados de revisión.
    *   `Anotacion`, `NotaComentario`: Sistema de feedback detallado (coordenadas X, Y) sobre los documentos.

## 🛠️ Tecnologías Recomendadas

*   **Django REST Framework (DRF)**: Para la creación de la API.
*   **SimpleJWT**: Autenticación basada en tokens.
*   **PostgreSQL**: Base de datos relacional (según `docker-compose.yml`).
*   **Django-CORS-Headers**: Para permitir la comunicación con el frontend.
