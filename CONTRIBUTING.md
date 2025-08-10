# Guía de Desarrollo y Contribución

Este documento establece las convenciones, estándares y mejores prácticas a seguir durante el desarrollo de este proyecto. El objetivo es mantener un código limpio, consistente y fácil de mantener.

## 📜 Principios Generales

1. **Código Limpio y Legible:** El código debe ser auto-explicativo. Prioriza la claridad sobre la brevedad.
2. **Consistencia:** Sigue las convenciones definidas en este documento en todo el proyecto.
3. **Commits Atómicos:** Cada `commit` debe representar una unidad de trabajo lógica y completa. Evita los commits con mensajes como "arreglos" o "más cambios".

## 💻 Convenciones de Código

### **Lenguaje**
* Todo el código, comentarios, nombres de variables y funciones se escribirán en **inglés**. Esto es un estándar de la industria que facilita el uso de librerías y la colaboración global.

### **Formato y Estilo**
* **Prettier:** Todo el código será formateado automáticamente por Prettier. La configuración se encuentra en el archivo `.prettierrc`.
* **ESLint:** Se utilizará para detectar problemas de calidad de código y estilo. No se deben ignorar las reglas de ESLint sin una justificación clara.

### **Nomenclatura**
* **Variables y Funciones:** `camelCase` (ej: `myVariable`, `calculateTotal`).
* **Clases y Componentes React:** `PascalCase` (ej: `UserService`, `UserProfileCard`).
* **Archivos de Componentes (React/Next.js):** `PascalCase` (ej: `UserProfileCard.jsx`).
* **Archivos de Backend (NestJS):** `kebab-case` seguido del tipo (ej: `user.service.ts`, `auth.controller.ts`).

## 🏛️ Arquitectura y Flujo de Trabajo

### **Flujo de Git (Git Flow)**
* **`main`:** Es la rama principal. Refleja el código en producción. Solo se fusiona desde `develop` para nuevos lanzamientos.
* **`develop`:** Es la rama de integración principal. Todas las nuevas funcionalidades se fusionan aquí.
* **Ramas de Funcionalidad (`feature/...`):**
  * Para cada nueva tarea, se crea una rama a partir de `develop`.
  * Nombre de la rama: `feature/descripcion-corta-en-kebab-case` (ej: `feature/user-login-api`).
  * Una vez completada, se crea un "Pull Request" para fusionarla de vuelta a `develop`.

### **Mensajes de Commit**
Se seguirá el estándar de **Conventional Commits**. Esto facilita la generación automática de registros de cambios (changelogs).
* **Formato:** `<tipo>(<ámbito opcional>): <descripción>`
* **Ejemplos:**
  * `feat(auth): add password hashing on user registration`
  * `fix(ui): correct button alignment on mobile view`
  * `docs(readme): update setup instructions`
* **Tipos comunes:** `feat` (nueva funcionalidad), `fix` (corrección de error), `docs` (documentación), `style` (formato), `refactor` (refactorización de código), `test` (pruebas), `chore` (tareas de mantenimiento).

## 🔌 Definición y Estilo de la API (Backend)

### **Diseño**
* La API seguirá el estilo **RESTful**.
* Los endpoints deben ser sustantivos en plural (ej: `/users`, `/products`).
* Se utilizarán los métodos HTTP correctamente:
  * `GET`: Para obtener recursos.
  * `POST`: Para crear nuevos recursos.
  * `PUT` / `PATCH`: Para actualizar recursos existentes.
  * `DELETE`: Para eliminar recursos.

### **Respuestas**
* Las respuestas exitosas (`2xx`) devolverán los datos en formato JSON.
* Los errores (`4xx`, `5xx`) devolverán un objeto JSON con una estructura consistente:
  ```json
  {
    "statusCode": 404,
    "message": "User not found",
    "error": "Not Found"
  }
````