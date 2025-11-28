# 🏢 Ferreteria Yerias - Backend API

![.NET](https://img.shields.io/badge/.NET-5.0-512BD4?style=flat-square&logo=dotnet)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white)
![EF Core](https://img.shields.io/badge/Entity%20Framework-Core-512BD4?style=flat-square)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat-square&logo=microsoft-sql-server&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

> Una API RESTful integral construida con .NET Core para potenciar el ecosistema de Ferretería Yerias, gestionando la lógica de negocio, persistencia de datos y autenticación.

---

### 🇺🇸 English Version: [Read here](./README.md)

---

## 🔗 Ecosistema y Repositorios Relacionados

Este repositorio provee los servicios backend para el **Ecosistema Ferreteria Yerias**.

*   **Cliente Web (React):** [React-System-Sales-Yerias-Web](https://github.com/dariverap/React-System-Sales-Yerias-Web)

---

## 👨‍💻 Autor

**Creado por Diego Rivera**

---

## 💻 Tech Stack

Esta solución backend utiliza tecnologías empresariales para fiabilidad y estructura:

*   **Framework:** .NET 5.0 Web API
*   **Lenguaje:** C#
*   **ORM:** Entity Framework Core (Enfoque Code-First).
*   **Base de Datos:** Microsoft SQL Server.
*   **Documentación:** Swagger / OpenAPI.
*   **Seguridad:** JWT (JSON Web Tokens) y Hashing de contraseñas (PBKDF2).

## 🏗️ Arquitectura

La API sigue un patrón Controlador-Servicio (simplificado a través de Controladores usando DbContext directamente):

1.  **Controladores:** Exponen endpoints RESTful (GET, POST, PUT, DELETE) en `api-ferreteria/[recurso]`.
2.  **Modelos de Entidad:** Definen el esquema de la base de datos (Productos, Clientes, Ventas, Usuarios, Roles).
3.  **Migraciones:** Gestiona los cambios de esquema de base de datos vía EF Core.
4.  **CORS:** Configurado para permitir peticiones desde el Cliente Web (`http://localhost:3000`).

### Entidades Clave
*   **Inventario:** `Producto`, `Categoria`, `Marca`, `Proveedor`.
*   **Operaciones:** `Compra` (Órdenes de compra), `Comprobante` (Recibos de venta), `Detalle` (Items de línea).
*   **Acceso:** `Usuario`, `Rol`, `Empleado`.

## 🚀 Instalación y Configuración

### Prerrequisitos
*   SDK de .NET 5.0
*   Microsoft SQL Server (LocalDB o Standard)
*   Visual Studio 2019/2022 o VS Code

### Pasos

1.  **Clonar el repositorio**
    ```bash
    git clone https://github.com/dariverap/Net5-System-Sales-Yerias-RestAPI
    cd Net5-System-Sales-Yerias-RestAPI
    ```

2.  **Configurar Conexión a Base de Datos**
    Actualiza el archivo `appsettings.json` con tu cadena de conexión local a SQL Server:
    ```json
    "ConnectionStrings": {
      "defaultConnection": "Data Source=.; Initial Catalog=dbferreteria; Integrated Security=true;"
    }
    ```

3.  **Aplicar Migraciones**
    Crea el esquema de base de datos usando las herramientas de Entity Framework Core:
    ```bash
    dotnet tool install --global dotnet-ef
    dotnet ef database update
    ```

4.  **Ejecutar la API**
    ```bash
    dotnet run
    ```
    La API se iniciará en `https://localhost:44318` (o el puerto configurado).
    Accede a la documentación Swagger en: `https://localhost:44318/swagger/index.html`.

## 📡 Endpoints de la API

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| `GET` | `/api-ferreteria/producto/custom` | Obtener productos activos |
| `POST` | `/api-ferreteria/comprobante` | Crear una nueva venta |
| `GET` | `/api-ferreteria/usuario/{user}/{pass}` | Inicio de sesión de usuario |
| `GET` | `/api-ferreteria/reporteventas` | Generar reportes de ventas |

*(Ver Swagger UI para la lista completa de endpoints)*