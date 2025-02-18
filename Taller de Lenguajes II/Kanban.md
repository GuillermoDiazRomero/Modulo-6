# Kanban MVC - Gestor de Tareas
---
## Descripción
---

Kanban MVC es una aplicación web desarrollada en ASP.NET que permite gestionar tareas de forma intuitiva utilizando un tablero Kanban. Su objetivo es optimizar el flujo de trabajo, facilitar la colaboración y organizar las tareas de manera eficiente mediante un sistema de tarjetas y columnas que representan las distintas etapas del proceso.

La aplicación está diseñada para ser flexible y segura, permitiendo el acceso únicamente a usuarios autenticados y ofreciendo funcionalidades específicas según el rol asignado.

---
## Características Principales
---

- **Autenticación Segura:** Acceso restringido a usuarios registrados.
- **Gestión de Tareas:** Crear, modificar y mover tareas entre las distintas etapas del tablero.
- **Roles Diferenciados:**
    - **Administrador:** Control total sobre usuarios, tableros y tareas.
    - **Operador:** Gestión de tareas propias y visualización de tableros relacionados.
- **Interfaz Intuitiva:** Diseño sencillo y accesible para facilitar su uso en cualquier entorno laboral.
- **Registro de Logs:** Registro automático de eventos y errores para facilitar el mantenimiento.

---
## Cómo Funciona
---

1. **Inicio de Sesión:** Los usuarios deben autenticarse para acceder al sistema.
2. **Gestión de Usuarios:** Los administradores pueden agregar, modificar o eliminar usuarios.
3. **Gestión de Tableros:** Crear nuevos tableros y organizar tareas en ellos.
4. **Gestión de Tareas:** Asignar tareas a usuarios, cambiar su estado y mantener un seguimiento del progreso.
5. **Seguridad y Control:** Validación de datos, control de excepciones y sistema de logs para garantizar el correcto funcionamiento.

## Instalación y Configuración

1. **Visual Studio Code:**
- Tener instalado Visual Studio Code con extensiones de C# para poder ejecutar el proyecto

2. **Clonar el Repositorio:**

 ```
git clone https://github.com/TallerDeLenguajes2/tl2-proyecto-2024-GuillermoDiazRomero
```

3. **Abrir el proyecto desde la terminal:**

```
cd tl2-proyecto-2024-GuillermoDiazRomero
```

1. **Correr el proyecto:**

```
dotnet run
```


## Tecnologías Utilizadas

- ASP.NET MVC 8.0
- C#
- SQLite
- HTML5, CSS3 y JavaScript

## Beneficios de Usar Kanban MVC

- **Organización Eficiente:** Controla y organiza tareas fácilmente.
- **Colaboración Optimizada:** Visualiza y gestiona tareas en equipo sin complicaciones.
- **Accesible para Todos:** Interfaz clara e intuitiva que permite su uso a personas con distintos niveles técnicos.
- **Seguridad y Control:** Sistema robusto con control de acceso y logs detallados.

## ¡Empieza a Organizar tu Trabajo Hoy!

Si buscas una herramienta sencilla, práctica y eficiente para gestionar tareas, ¡Kanban MVC es la solución perfecta! Prueba ahora y experimenta cómo un tablero Kanban bien gestionado puede impulsar la productividad de tu equipo.

## Usuarios de Prueba
**Rol Admin:**
- Usuario: Admin
- Clave: !adminPass123!
**Rol Operador:**
- Usuario: Pepe Argento
- Clave: PepeArgento123!