# 🏢 Ferreteria Yerias - Backend API

![.NET](https://img.shields.io/badge/.NET-5.0-512BD4?style=flat-square&logo=dotnet)
![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white)
![EF Core](https://img.shields.io/badge/Entity%20Framework-Core-512BD4?style=flat-square)
![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=flat-square&logo=microsoft-sql-server&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

> A comprehensive RESTful API built with .NET Core to power the Ferreteria Yerias ecosystem, managing business logic, data persistence, and authentication.

---

### 🇪🇸 Versión en Español: [Leer aquí](./README.es.md)

---

## 🔗 Ecosystem & Related Repositories

This repository provides the backend services for the **Ferreteria Yerias Ecosystem**.

*   **Web Client (React):** [React-System-Sales-Yerias-Web](https://github.com/dariverap/React-System-Sales-Yerias-Web)

---

## 👨‍💻 Author

**Created by Diego Rivera**

---

## 💻 Tech Stack

This backend solution utilizes enterprise-grade technologies for reliability and structure:

*   **Framework:** .NET 5.0 Web API
*   **Language:** C#
*   **ORM:** Entity Framework Core (Code-First approach).
*   **Database:** Microsoft SQL Server.
*   **Documentation:** Swagger / OpenAPI.
*   **Security:** JWT (JSON Web Tokens) & Password Hashing (PBKDF2).

## 🏗️ Architecture

The API follows a Controller-Service-Repository pattern (simplified via Controllers using DbContext directly for MVC patterns):

1.  **Controllers:** Expose RESTful endpoints (GET, POST, PUT, DELETE) at `api-ferreteria/[resource]`.
2.  **Entity Models:** Defines the database schema (Products, Clients, Sales, Users, Roles).
3.  **Migrations:** Manages database schema changes via EF Core.
4.  **CORS:** Configured to allow requests from the Web Client (`http://localhost:3000`).

### Key Entities
*   **Inventory:** `Producto`, `Categoria`, `Marca`, `Proveedor`.
*   **Operations:** `Compra` (Purchase Orders), `Comprobante` (Sales Receipts), `Detalle` (Line Items).
*   **Access:** `Usuario`, `Rol`, `Empleado`.

## 🚀 Installation & Setup

### Prerequisites
*   .NET 5.0 SDK
*   Microsoft SQL Server (LocalDB or Standard)
*   Visual Studio 2019/2022 or VS Code

### Steps

1.  **Clone the repository**
    ```bash
    git clone https://github.com/dariverap/Net5-System-Sales-Yerias-RestAPI
    cd Net5-System-Sales-Yerias-RestAPI
    ```

2.  **Configure Database Connection**
    Update the `appsettings.json` file with your local SQL Server connection string:
    ```json
    "ConnectionStrings": {
      "defaultConnection": "Data Source=.; Initial Catalog=dbferreteria; Integrated Security=true;"
    }
    ```

3.  **Apply Migrations**
    Create the database schema using Entity Framework Core tools:
    ```bash
    dotnet tool install --global dotnet-ef
    dotnet ef database update
    ```

4.  **Run the API**
    ```bash
    dotnet run
    ```
    The API will launch at `https://localhost:44318` (or configured port).
    Access Swagger documentation at: `https://localhost:44318/swagger/index.html`.

## 📡 API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/api-ferreteria/producto/custom` | Get active products |
| `POST` | `/api-ferreteria/comprobante` | Create a new sale |
| `GET` | `/api-ferreteria/usuario/{user}/{pass}` | User login |
| `GET` | `/api-ferreteria/reporteventas` | Generate sales reports |

*(See Swagger UI for the full list of endpoints)*