# Foro API en Java con Spring Boot

Este proyecto es una API REST desarrollada en Java utilizando Spring Boot, que implementa autenticación con JWT y permite la gestión de usuarios y tópicos en un foro.

El desafío consiste en aplicar conocimientos de Java, Programación Orientada a Objetos y el ecosistema de Spring, además de aprender a implementar seguridad con JWT, una habilidad fundamental para cualquier desarrollador backend.

---

## Descripción del Proyecto

La aplicación expone una API que permite a los usuarios autenticarse y crear, listar y consultar tópicos dentro de un foro.  
El flujo principal es:

1. Autenticar al usuario mediante `/auth` (devuelve un JWT).
2. Usar el token en los headers para acceder a los endpoints protegidos.
3. Crear y listar tópicos en el foro utilizando la API.

Este proyecto forma parte de un reto de aprendizaje enfocado en el uso de Spring Security y JWT para proteger servicios REST.

---

## Tecnologías Utilizadas

- Java 24+
- Spring Boot 3.5.4
- Spring Data JPA (Hibernate)
- Spring Security con JWT
- H2 Database (base de datos en memoria)
- Maven
- Git & GitHub (control de versiones)

---

## Endpoints principales

| Método | Endpoint   | Descripción                          |
|--------|------------|--------------------------------------|
| POST   | /auth      | Autentica al usuario y devuelve JWT  |
| GET    | /topicos   | Lista todos los tópicos (requiere JWT) |
| POST   | /topicos   | Crea un nuevo tópico (requiere JWT)   |

### Ejemplo de uso
**Autenticación:**
```json
POST /auth
{
  "username": "admin",
  "password": "1234"
}

Respuesta:

{
  "token": "eyJhbGciOiJIUzI1NiJ9..."
}

Consulta de tópicos (GET /topicos):

[
  {
    "id": 1,
    "titulo": "Duda sobre Spring Security",
    "mensaje": "¿Cómo implementar JWT en un proyecto?",
    "autor": "Juan",
    "fechaCreacion": "2025-08-18T10:15:30"
  },
  {
    "id": 2,
    "titulo": "Error con Hibernate",
    "mensaje": "Me da error al mapear una entidad.",
    "autor": "Maria",
    "fechaCreacion": "2025-08-18T11:02:10"
  }
]

Estructura del Proyecto
foro-api/
├── src/
│   ├── main/java/com/foro/
│   │   ├── ForoApiApplication.java
│   │   ├── controller/
│   │   ├── entity/
│   │   ├── repository/
│   │   ├── security/
│   │   └── service/
│   └── main/resources/
│       └── application.properties
├── README.md
├── .gitignore
└── pom.xml
