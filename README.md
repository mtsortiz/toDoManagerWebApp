# ✅ ToDo Manager Web App

<div align="center">
  <h2>📝 Gestión de Tareas Moderna 📝</h2>
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white" alt="Thymeleaf"/>
  <img src="https://img.shields.io/badge/H2_Database-018bff?style=for-the-badge&logo=database&logoColor=white" alt="H2"/>
</div>

## 📋 Descripción
Aplicación web completa para la gestión de tareas (ToDo) desarrollada con Spring Boot. Permite crear, editar, eliminar y organizar tareas de manera eficiente a través de una interfaz web moderna y responsive. Incluye autenticación de usuarios, persistencia de datos y una API REST completa.

## ✨ Características
- 🔄 **CRUD completo:** Crear, leer, actualizar y eliminar tareas
- 🔐 **Autenticación:** Sistema de login y registro de usuarios
- 📱 **Interfaz responsive:** Diseño adaptable a diferentes dispositivos
- 💾 **Persistencia:** Base de datos H2 integrada
- 🌐 **API REST:** Endpoints para integración con otras aplicaciones
- 🔍 **Filtros y búsqueda:** Organización eficiente de tareas
- 📊 **Estados de tareas:** Pendiente, en progreso, completado
- ⏰ **Fechas de vencimiento:** Gestión de deadlines

## Tecnologías Utilizadas
- **Backend:** Spring Boot 3.2.1
- **Frontend:** Thymeleaf, HTML5, CSS3, JavaScript
- **Base de datos:** H2 Database (embebida)
- **ORM:** Spring Data JPA
- **Security:** Spring Security
- **Build tool:** Maven
- **Java:** JDK 21

## Estructura del Proyecto
```
toDoManagerWebApp/
├── src/main/java/com/masterSpring-Springboot/myFirstWebApp/
│   ├── controller/          # Controladores REST y MVC
│   ├── model/              # Entidades JPA
│   ├── repository/         # Repositorios de datos
│   ├── service/            # Lógica de negocio
│   ├── security/           # Configuración de seguridad
│   └── MyFirstWebAppApplication.java
├── src/main/resources/
│   ├── templates/          # Plantillas Thymeleaf
│   ├── static/            # CSS, JS, imágenes
│   └── application.properties
└── pom.xml
```

## 🚀 Funcionalidades

### ✏️ Gestión de Tareas
- **Crear tarea:** Formulario para agregar nuevas tareas con título, descripción y fecha límite
- **Listar tareas:** Vista de todas las tareas con filtros por estado
- **Editar tarea:** Modificación de tareas existentes
- **Eliminar tarea:** Borrado de tareas completadas o canceladas
- **Marcar como completada:** Cambio de estado de tareas

### 👤 Gestión de Usuarios
- 📝 **Registro:** Creación de nuevas cuentas de usuario
- 🔑 **Login/Logout:** Autenticación segura
- 👤 **Perfil:** Gestión de información personal
- 🔒 **Tareas por usuario:** Cada usuario ve solo sus tareas

### 🎯 Filtros y Organización
- Filtrar por estado (pendiente, completado, vencido)
- Buscar tareas por título o descripción
- Ordenar por fecha de creación o vencimiento
- Paginación para listas grandes

## Requisitos del Sistema
- **Java:** JDK 21 o superior
- **Maven:** 3.6+
- **Navegador:** Chrome, Firefox, Safari, Edge (versiones recientes)
- **Memoria:** 512 MB RAM mínimo

## Instalación y Ejecución

### 1. Clonar el repositorio
```bash
git clone <repository-url>
cd toDoManagerWebApp
```

### 2. Compilar el proyecto
```bash
./mvnw clean install
```

### 3. Ejecutar la aplicación
```bash
./mvnw spring-boot:run
```

### 4. Acceder a la aplicación
Abrir navegador en: `http://localhost:8080`

## Configuración

### Base de Datos
La aplicación utiliza H2 Database embebida por defecto. Para acceder a la consola H2:
- URL: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:testdb`
- Usuario: `sa`
- Contraseña: (vacía)

### Propiedades de la aplicación
Archivo `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.h2.console.enabled=true
spring.jpa.show-sql=true
```

## 🌐 API REST Endpoints

### 📋 Tareas
- `GET /api/todos` - Listar todas las tareas
- `GET /api/todos/{id}` - Obtener tarea por ID
- `POST /api/todos` - Crear nueva tarea
- `PUT /api/todos/{id}` - Actualizar tarea
- `DELETE /api/todos/{id}` - Eliminar tarea

### 👥 Usuarios
- `POST /api/users/register` - Registrar usuario
- `POST /api/users/login` - Iniciar sesión
- `GET /api/users/profile` - Obtener perfil

## 📊 Modelo de Datos

### Entidad ToDo
```java
{
  "id": Long,
  "title": String,
  "description": String,
  "completed": Boolean,
  "dueDate": LocalDate,
  "createdAt": LocalDateTime,
  "userId": Long
}
```

### Entidad User
```java
{
  "id": Long,
  "username": String,
  "email": String,
  "password": String,
  "createdAt": LocalDateTime
}
```

## Testing
Ejecutar tests unitarios y de integración:
```bash
./mvnw test
```

## Desarrollo

### Agregar nuevas funcionalidades
1. Crear entidad en `model/`
2. Crear repositorio en `repository/`
3. Implementar servicio en `service/`
4. Crear controlador en `controller/`
5. Desarrollar plantillas en `templates/`

### Hot reload durante desarrollo
```bash
./mvnw spring-boot:run -Dspring-boot.run.jvmArguments="-Dspring.devtools.restart.enabled=true"
```

## Deployment

### JAR ejecutable
```bash
./mvnw clean package
java -jar target/myFirstWebApp-0.0.1-SNAPSHOT.jar
```

### Docker (opcional)
```dockerfile
FROM openjdk:21-jre-slim
COPY target/myFirstWebApp-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app.jar"]
```

## Seguridad
- Autenticación basada en sesiones
- Protección CSRF habilitada
- Validación de entrada en formularios
- Autorización por usuario para acceso a tareas

## Contribución
Para contribuir al proyecto:
1. Fork del repositorio
2. Crear rama feature/nueva-funcionalidad
3. Implementar cambios siguiendo las convenciones de Spring Boot
4. Agregar tests para nueva funcionalidad
5. Enviar pull request

## 🚀 Próximas mejoras
- 🔔 Notificaciones push para tareas vencidas
- 🏷️ Categorías y etiquetas para tareas
- 👥 Colaboración entre usuarios
- 📱 Aplicación móvil
- 📅 Integración con calendarios externos

## Licencia
Este proyecto es para fines educativos y de demostración de Spring Boot.