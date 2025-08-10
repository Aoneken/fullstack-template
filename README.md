# Proyecto "Mi Super App" (Nombre a definir)

> **Estado del Proyecto (10/08/2025):** ¡Configuración completada! Todas las fases de puesta a punto (0 a 4) han finalizado con éxito. El entorno de desarrollo está 100% operativo y listo para la fase de construcción de la aplicación.

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
| **Backend** | **NestJS** | A definir | Framework de Node.js para construir una API robusta y escalable. |
| **Base de Datos** | **PostgreSQL** | 15 | Sistema de gestión de bases de datos relacional. |
| **Editor de Código** | **Visual Studio Code** | N/A | IDE principal, integrado con WSL para un desarrollo nativo en Linux. |

---

## 🚀 Guía de Puesta en Marcha

### **Parte 1: Configuración del Entorno (Una sola vez por máquina)**

1.  **Instalar Prerrequisitos Base:**
    * **WSL 2 con Ubuntu:** `wsl --install` en PowerShell como Administrador.
    * **Docker Desktop:** Desde su web oficial, configurado para usar WSL 2.
    * **Visual Studio Code:** Desde su web oficial.
    * **Windows Terminal:** Recomendado, desde la Microsoft Store.

2.  **Calibrar el Entorno WSL (Dentro de la terminal de Ubuntu):**
    * **Actualizar Ubuntu:** `sudo apt update && sudo apt upgrade -y`
    * **Instalar nvm:** `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash`
    * **Instalar Node.js LTS:** `nvm install --lts`
    * **Configurar VS Code:** Instalar la extensión "WSL" y conectar el editor. Instalar `ESLint`, `Prettier`, `Thunder Client`, `GitLens` en el entorno WSL.

### **Parte 2: Configuración del Proyecto (Una sola vez por proyecto)**

1.  **Clonar el Repositorio:**
    ```bash
    git clone <URL_DEL_REPOSITORIO>
    cd <NOMBRE_DEL_PROYECTO>
    ```

2.  **Abrir en VS Code con WSL:**
    * Desde la terminal dentro de la carpeta del proyecto, ejecuta `code .`

3.  **Configurar Git (si es la primera vez en la máquina):**
    ```bash
    git config --global user.name "Tu Nombre"
    git config --global user.email "tu@email.com"
    git config --global init.defaultBranch main
    ```

4.  **Verificar el `docker-compose.yml`:**
    * Asegúrate de que el archivo `docker-compose.yml` existe en la raíz del proyecto.

### **Parte 3: Comandos de Desarrollo Diario**

1.  **Levantar Servicios de Infraestructura:**
    * Este comando lee el `docker-compose.yml` y enciende la base de datos.
    ```bash
    docker-compose up -d
    ```

2.  **Instalar Dependencias (cuando sea necesario):**
    * Desde la carpeta de cada sub-proyecto (`backend`, `frontend-web`, etc.).
    ```bash
    npm install
    ```

3.  **Ejecutar las Aplicaciones:**
    * Desde la carpeta de cada sub-proyecto.
    * **Backend:** `npm run start:dev`
    * **Frontend Web:** `npm run dev`
    * **Frontend Móvil:** `npm start`

---

## 📂 Estructura del Proyecto

/
├── backend/           \# Contiene la aplicación de NestJS (API)
├── frontend-web/      \# Contiene la aplicación de Next.js (Web)
├── frontend-mobile/   \# Contiene la aplicación de React Native (Móvil)
├── .github/           \# (Futuro) Contendrá los workflows de CI/CD
├── docker-compose.yml \# Define los servicios de infraestructura (ej. DB)
└── README.md          \# Este archivo