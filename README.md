
# Clon de Colab
Este proyecto tiene como objetivo desarrollar una aplicación web que emule las funcionalidades básicas de Colab.

## Gestión de Proyectos:
- Crear, listar, actualizar, obtener detalles (incluidas las tareas relacionadas, resumen de estados de las tareas, etc.), y eliminar (soft) proyectos. 
- Un proyecto tiene:
  - **Id**: Identificador único.
  - **Name**: Nombre del proyecto.
  - **Description**: Descripción.
  - **CreatedById**: Usuario que lo creó.
  - **ResponsibleId**: Usuario Responsable.

## Gestión de Tareas:
- Crear, listar (añadir filtros según su criterio), actualizar y eliminar (soft) tareas dentro de un proyecto.
- Una tarea tiene:
  - **Id**: Identificador único.
  - **ProjectId** Proyecto al que está relacionado la tarea.
  - **Title**: Título.
  - **Description**: Descripción.
  - **DueDate**: Fecha límite.
  - **Status**: Estado (Pendiente, En Proceso, Completada).
  - **CreatedById**: Usuario que lo creó.

## Gestión de Usuarios:
- **Registro de usuarios** con validación de datos (correo único, contraseñas seguras).
- **Inicio de sesión** con autenticación basada en JWT.
- **Roles**:
  - **Admin**: Puede gestionar proyectos y usuarios.
  - **User**: Puede gestionar solo sus tareas.

## Requisitos Técnicos

### Tecnologías:
- **ASP.NET**.
- **Entity Framework Core o Dapper** (con una base de datos SQL).
- **Autenticación JWT**.
- Opcional:
  - Uso de un contenedor Docker (archivo Dockerfile).
  - SignalR para notificaciones.

### Estructura del Proyecto:
- La arquitectura de capas (WebApi, Infrastructure, Core).
- Implementa patrones de diseño como **Repository Pattern**.

### Validaciones:
- Valida modelos de entrada (e.g., contraseñas con al menos 8 caracteres, correos válidos).
- Maneja errores mediante middleware global para devolver respuestas HTTP claras.
- Opcional: Sólo los responsables pueden actualizar/eliminar el proyecto.
- Opcional: Sólo los creadores de la tarea pueden actualizar la misma.

## Entregables

### Código Fuente:
- Repositorio organizado con instrucciones claras en un archivo **README.md**.
- Opcional:
  - Dockerfile y docker-compose.yml para levantar la aplicación localmente.
