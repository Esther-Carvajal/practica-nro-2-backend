# practica-nro-2-backend
# 🎓 Sistema de Registro Universitario

Un sistema completo para la gestión universitaria con autenticación JWT, roles de usuario y múltiples módulos funcionales.

## 🌟 Características Principales

- **Autenticación segura** con JWT y roles (Admin, Docente, Estudiante)
- **CRUD completo** para:
  - Estudiantes
  - Materias
  - Docentes
  - Inscripciones
- **Validaciones** en backend y manejo de errores
- **Documentación API** con Swagger UI
- **Caché de alto rendimiento** con Redis
- **Base de datos** PostgreSQL con migraciones automáticas

## 🛠 Tecnologías Utilizadas

| Tecnología         | Uso en el Proyecto                     |
|--------------------|----------------------------------------|
| Spring Boot 3.1    | Framework principal del backend        |
| Spring Security    | Autenticación y autorización           |
| JWT               | Tokens de autenticación                |
| PostgreSQL        | Base de datos relacional               |
| Redis             | Caché para mejorar rendimiento         |
| Swagger/OpenAPI   | Documentación interactiva de la API     |
| Lombok            | Reducción de código boilerplate        |
| Maven             | Gestión de dependencias                |

## 📂 Estructura del Proyecto

src/
├── main/
│ ├── java/
│ │ └── com/
│ │ └── universidad/
│ │ ├── config/ # Configuraciones
│ │ ├── controller/ # Controladores REST
│ │ ├── dto/ # Objetos de transferencia
│ │ ├── exception/ # Manejo de excepciones
│ │ ├── model/ # Entidades JPA
│ │ ├── repository/ # Repositorios Spring Data
│ │ ├── security/ # Configuración de seguridad
│ │ ├── service/ # Lógica de negocio
│ │ └── validation/ # Validaciones personalizadas
│ └── resources/
│ ├── application.properties # Configuración
│ └── static/ # Recursos estáticos (si aplica)


## 🔐 Roles y Permisos

| Rol        | Endpoints Accesibles                     | Descripción                     |
|------------|------------------------------------------|---------------------------------|
| ADMIN      | Todos los endpoints                      | Acceso completo al sistema      |
| DOCENTE    | Gestión de materias, consultas           | Puede ver estudiantes y materias|
| ESTUDIANTE | Sus propias inscripciones                | Acceso limitado a sus datos     |

📌 Endpoints Clave
Autenticación
POST /api/auth/login - Iniciar sesión

POST /api/auth/signup - Registrar nuevo usuario (solo ADMIN)

Estudiantes
GET /api/estudiantes - Listar todos (ADMIN/DOCENTE)

POST /api/estudiantes - Crear nuevo (ADMIN)

Materias
GET /api/materias - Listar todas (ADMIN/DOCENTE)

POST /api/materias/asignar-docente - Asignar docente (ADMIN)

Inscripciones
POST /api/inscripciones - Crear inscripción (ADMIN/ESTUDIANTE)

GET /api/inscripciones/estudiante/{id} - Ver inscripciones
