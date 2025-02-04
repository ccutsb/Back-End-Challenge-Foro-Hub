# Back-End-Challenge-Foro-Hub

Este proyecto es una aplicación backend desarrollada con Spring Boot, diseñada para el manejo de foros en línea. La estructura del proyecto está configurada con Maven como gestor de dependencias y sigue el esquema de una aplicación moderna y escalable.

## Configuración del Proyecto

### Información General
- **Group ID**: `com.backend.challengeforohub`  
- **Artifact ID**: `Challenge_Foro_Hub`  
- **Version**: `0.0.1-SNAPSHOT`  
- **Java Version**: 17  

### Dependencias Principales
El archivo `pom.xml` incluye:
- **Spring Boot Starter Data JPA**: Persistencia de datos  
- **Spring Boot Starter Web**: Controladores REST  
- **Spring Boot DevTools**: Herramientas de desarrollo  
- **MySQL Connector**: Conexión MySQL  
- **Lombok**: Simplificación de código Java  
- **Spring Boot Starter Test**: Pruebas unitarias  
- **Spring Boot Starter Logging** + **Logback Classic**: Manejo de logs  
- **Spring Boot Starter Validation**: Validación de datos  
- **Jackson Databind**: Serialización JSON  
- **ModelMapper**: Mapeo DTO-Entidades  
- **Gson**: Manejo alternativo de JSON  
- **Spring Boot Starter Security**: Seguridad  
- **JWT**: Autenticación con tokens  

### Plugins Configurados
- **Spring Boot Maven Plugin**: Compilación y empaquetado  
- **Maven Surefire Plugin**: Ejecución de pruebas  

## Cómo Iniciar el Proyecto

### Requisitos Previos
- JDK 17+  
- Maven instalado  
- MySQL configurado  

### Pasos para la Ejecución
1. Clona el repositorio:
```bash
git clone https://github.com/CasseliLayza/Challenge_Foro_Hub
```

2. Navega al directorio:
```bash
cd Challenge_Foro_Hub
```

3. Configura las propiedades de MySQL en `application.properties`:
```properties
spring.datasource.url=${DB_URL}
spring.datasource.username=${DB_USER}
spring.datasource.password=${DB_PASS}
spring.datasource.driver-class-name=${DB_DRIVER}
spring.jpa.properties.hibernate.dialect=${DB_PLATFORM}
```

4. Ejecuta con Maven:
```bash
mvn spring-boot:run
```

5. Accede a:
```
http://localhost:8080
```

## Características Principales
- ✅ **Persistencia de Datos**: JPA + MySQL  
- ✅ **Validación Estricta**: Restricciones en entradas  
- ✅ **Autenticación JWT**: Tokens de seguridad  
- ✅ **Mapeo Automático**: DTO ↔ Entidades  

## Rutas de la API por Roles

### Endpoints Públicos
| Método | Ruta                  | Descripción                 | Roles      |
|--------|-----------------------|-----------------------------|------------|
| GET    | `/users/**`           | Acceso público              | Todos      |
| POST   | `/users/register`     | Registro de usuarios        | Todos      |
| POST   | `/users/reesetids`    | Reinicio de identificadores | Todos      |
| GET    | `/roles/**`           | Consulta de roles           | Todos      |
| GET    | `/topics/**`          | Listado de temas            | Todos      |

### Endpoints Protegidos
**Usuarios**  
| Método | Ruta              | Descripción         | Roles  |
|--------|-------------------|---------------------|--------|
| POST   | `/users/create`   | Crear usuario       | USER   |
| DELETE | `/users/**`       | Eliminar usuario    | ADMIN  |

**Temas**  
| Método | Ruta                      | Descripción             | Roles  |
|--------|---------------------------|-------------------------|--------|
| POST   | `/topics/register`        | Registrar tema          | USER   |
| PUT    | `/topics/update/{id}`     | Actualizar tema         | ADMIN  |
| DELETE | `/topics/delete/{id}`     | Eliminar tema           | ADMIN  |

## Estructura del Proyecto
```
src/
└── main/
    ├── java/
    │   └── com/
    │       └── backend/
    │           └── challengeforohub/
    │               ├── controller/          # Controladores REST
    │               │   ├── RolController.java
    │               │   ├── TopicoController.java
    │               │   └── UsuarioController.java
    │               ├── dto/                 # Objetos de Transferencia
    │               │   ├── input/           # DTOs de entrada
    │               │   └── output/          # DTOs de salida
    │               ├── entity/              # Entidades JPA
    │               ├── exception/           # Manejo de excepciones
    │               ├── repository/          # Repositorios Spring Data
    │               ├── security/            # Configuración de seguridad
    │               └── service/             # Lógica de negocio
    └── resources/
        ├── application.properties           # Configuración
        ├── static/                          # Recursos estáticos
        └── templates/                       # Plantillas (si aplica)
```

## Contribuir
1.  Haz un **fork** del repositorio  
2.  Crea una rama: `git checkout -b mi-feature`  
3:  Commits descriptivos: `git commit -m "feat: nueva funcionalidad"`  
4.  Push: `git push origin mi-feature`  
5.  Abre un **Pull Request**  

## Licencia
[![Licencia MIT](https://img.shields.io/badge/Licencia-MIT-green.svg)](LICENSE)  
Este proyecto está bajo la **Licencia MIT** - ver archivo [LICENSE](LICENSE) para detalles.
