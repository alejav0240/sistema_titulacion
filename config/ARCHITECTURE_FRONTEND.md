# Arquitectura del Frontend - Sistema de Titulación

Esta arquitectura define la estructura de la interfaz de usuario desarrollada con **React** y **TypeScript**, optimizada para consumir la API del backend.

## 🏗️ Flujo de Datos y Componentes

<div align="center">
  <table style="width:100%; border-collapse: collapse; text-align: left; font-family: sans-serif;">
    <tr style="background-color: #005a8d; color: white;">
      <th style="padding: 10px; border: 1px solid #ddd;">Nivel</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Tecnología / Herramienta</th>
      <th style="padding: 10px; border: 1px solid #ddd;">Propósito en el Sistema</th>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">Presentación</td>
      <td style="padding: 10px; border: 1px solid #ddd;">React + Shadcn UI</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Componentes visuales (Cards de proyectos, formularios de anotaciones).</td>
    </tr>
    <tr style="background-color: #f0f7ff;">
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">Navegación</td>
      <td style="padding: 10px; border: 1px solid #ddd;">TanStack Router</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Gestión de rutas (Dashboards de estudiantes vs docentes).</td>
    </tr>
    <tr>
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">Estado Global</td>
      <td style="padding: 10px; border: 1px solid #ddd;">TanStack Query (React Query)</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Sincronización con el servidor (Proyectos, Notificaciones).</td>
    </tr>
    <tr style="background-color: #f0f7ff;">
      <td style="padding: 10px; border: 1px solid #ddd; font-weight: bold;">Feedback Visual</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Canvas / PDF Layers</td>
      <td style="padding: 10px; border: 1px solid #ddd;">Manejo de las coordenadas X, Y para las notas en los documentos.</td>
    </tr>
  </table>
</div>

## 🧩 Módulos de Usuario (Basado en DBML)

El frontend se organiza por capacidades según el perfil del usuario:

*   **Módulo de Revisión (Docente/Tribunal)**:
    *   Visualizador de PDF con capacidad de click para crear `Anotacion`.
    *   Formulario para estados de revisión (`estado_pendiente_revisando_...`).
*   **Módulo de Estudiante**:
    *   Subida de `Versiones` de proyectos.
    *   Panel de `Notificaciones` para ver feedback recibido.
*   **Módulo de Administración**:
    *   Gestión de `Usuarios`, `Materias` y asignación de `TutorTribunales`.

## 🛠️ Stack Tecnológico

*   **Vite**: Herramienta de construcción rápida.
*   **Tailwind CSS**: Estilizado basado en utilidades.
*   **Zustand (Opcional)**: Para estado local simple (como el tema oscuro/claro).
*   **Axios**: Cliente HTTP para conectar con el backend de Django.
