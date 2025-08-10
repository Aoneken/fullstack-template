# Proyecto "Mi Super App" (Nombre a definir)

> **Estado del Proyecto (10/08/2025):** ¡Backend inicializado! Se ha creado la estructura del proyecto NestJS en la carpeta `/backend`. El siguiente paso es verificar que el servidor puede arrancar correctamente.

Este proyecto consiste en una aplicación móvil y una aplicación web que comparten un mismo backend. El entorno de desarrollo está completamente contenerizado para asegurar la consistencia y facilitar la puesta en marcha.

## 🛠️ Stack Tecnológico

| Categoría | Herramienta | Versión | Propósito Técnico |
| :--- | :--- | :--- | :--- |
| **Contenerización** | **Docker Desktop** | 28.3.2 | Orquestar y gestionar contenedores para servicios como la base de datos. |
| **Entorno de Ejecución** | **Node.js** | 22.18.0 | Runtime de JavaScript del lado del servidor para el backend. |
| **Gestor de Paquetes** | **npm** | 10.9.3 | Gestión de las dependencias y librerías del proyecto. |
| **Gestor de Versiones** | **nvm** | 0.39.7 | Permite usar la versión correcta de Node.js definida para el proyecto. |
| **Frontend Web** | **Next.js (React)** | A definir | Framework para construir la aplicación web. |
| **Frontend Móvil** | **React Native** | A definir | Framework para construir la aplicación móvil para iOS y Android. |
| **Backend** | **NestJS** | ~10.0.0 | Framework de Node.js para construir una API robusta y escalable. |
| **Base de Datos** | **PostgreSQL** | 15 | Sistema de gestión de bases de datos relacional. |
| **Editor de Código** | **Visual Studio Code** | N/A | IDE principal, integrado con WSL para un desarrollo nativo en Linux. |

---

## 🌎 Entornos de Desarrollo Posibles

Este proyecto se puede desarrollar de dos maneras, dependiendo de los permisos que tengas en tu ordenador.

### **1. Entorno Local Completo (Requiere Permisos de Administrador)**

Este es el método preferido y más potente. Implica instalar WSL 2 y Docker directamente en tu máquina. Te da el control total y el mejor rendimiento. Las instrucciones para esta configuración se detallan a continuación.

### **2. Entorno en la Nube (No requiere permisos)**

Perfecto para trabajar desde ordenadores con restricciones (ej: PC del trabajo). Utiliza **GitHub Codespaces** para crear un entorno de desarrollo completo en la nube al que se accede desde el navegador.

* **Para iniciar:** Ve al repositorio en GitHub, haz clic en el botón `Code` y selecciona `Create codespace on main`.
* Esto te proporcionará una versión de VS Code en el navegador con acceso a una terminal, Docker, Node.js y todo lo necesario para ejecutar el proyecto completo.

---

## 🚀 Guía de Puesta en Marcha (Entorno Local)

### **Parte 1: Configuración del Entorno (Una sola vez por máquina)**

1.  **Instalar Prerrequisitos Base:** WSL 2 con Ubuntu, Docker Desktop, VS Code.
2.  **Calibrar el Entorno WSL:** Actualizar Ubuntu, instalar `nvm` y `Node.js LTS`, configurar VS Code con la extensión "WSL" y las herramientas recomendadas.

### **Parte 2: Configuración del Proyecto (Una sola vez por proyecto)**

1.  **Clonar el Repositorio:** `git clone <URL_DEL_REPOSITORIO>`
2.  **Abrir en VS Code con WSL:** `code .`
3.  **Configurar Git:** `git config --global user.name "Tu Nombre"` y `user.email`.
4.  **Inicializar el Backend:** `npm install -g @nestjs/cli` y luego `nest new backend` (seleccionando `npm`).

### **Parte 3: Comandos de Desarrollo Diario**

1.  **Sincronizar Cambios (si trabajas en varias máquinas):** `git pull`
2.  **Levantar Servicios de Infraestructura:** `docker-compose up -d`
3.  **Instalar Dependencias:** `npm install` (en cada sub-proyecto)
4.  **Ejecutar las Aplicaciones:**
    * **Backend:** `cd backend` y luego `npm run start:dev`
    * **Frontend Web:** `cd frontend-web` y luego `npm run dev`
    * **Frontend Móvil:** `cd frontend-mobile` y luego `npm start`
5.  **Guardar y Subir Cambios:** `git add .`, `git commit -m "..."`, `git push`

---

## 📂 Estructura del Proyecto

```
/
├── backend/           # Contiene la aplicación de NestJS (API)
├── frontend-web/      # Contiene la aplicación de Next.js (Web)
├── frontend-mobile/   # Contiene la aplicación de React Native (Móvil)
├── .github/           # (Futuro) Contendrá los workflows de CI/CD
├── docker-compose.yml # Define los servicios de infraestructura (ej. DB)
└── README.md          # Este archivo
