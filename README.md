# sistema-educativo-microservicios-yair-cristian
# Sistema Educativo - Microservicios

Este sistema educativo ha sido desarrollado utilizando la arquitectura de microservicios con Spring Boot y Spring Cloud. Cada funcionalidad está separada en servicios independientes para mejorar la escalabilidad y el mantenimiento.

## Autor
- Yair Mauricio Macgrego Perez, Cristian Camilo Osorio Mujica
- Carrera: Ingenieria de Sistemas
- Curso: Programacin Avanzada 2
- Parcial: 2 - Microservicios

## Microservicios
- `usuarios-servicio`: Gestión de estudiantes y docentes.
- `asignaturas-servicio`: CRUD de materias.
- `matriculas-servicio`: Registro de matrículas de estudiantes.

## Tecnologías
- Java 17
- Spring Boot
- Spring Cloud (Eureka, Config Server, Feign)
- Spring Security + JWT
- Docker + Docker Compose
- MongoDB o MySQL

## Arquitectura General

## Objetivo
Transformar el sistema monolítico en una arquitectura distribuida basada en microservicios, con comunicación entre ellos, seguridad y despliegue automatizado.

Documentación del Proyecto Sistema Educativo Microservicios

Información General

Nombre del Proyecto: Sistema Educativo Microservicios

Versión: 1.0

Arquitectura: Microservicios

Descripción del Proyecto

Sistema educativo implementado con arquitectura de microservicios que gestiona usuarios, asignaturas y matrículas. Utiliza Spring Boot y proporciona una API REST segura con autenticación JWT.

Estructura del Proyecto

Microservicios Principales

Servicio de Usuarios (Puerto 9083)

Gestión de autenticación y usuarios

Base de datos propia (MySQL)

Implementa JWT para seguridad

Servicio de Asignaturas (Puerto 9081)

Gestión de asignaturas y profesores

Base de datos propia (MySQL)

Seguridad basada en tokens

Servicio de Matrículas (Puerto 9082)

Gestión de matrículas

Comunicación con otros servicios vía Feign Client

Base de datos propia (MySQL)

Servicios de Infraestructura

Eureka Server (Puerto 9080)

Registro y descubrimiento de servicios

Monitoreo de servicios activos

Config Server (Puerto 9888)

Configuración centralizada

Integración con GitHub para configuraciones

Endpoints Principales

Servicio de Usuarios

Endpoint	Método	Descripción

/api/auth/login	POST	Autenticación de usuarios

/api/auth/register	POST	Registro de nuevos usuarios

Servicio de Asignaturas

Endpoint	Método	Descripción

/api/asignaturas	GET	Listar todas las asignaturas

/api/asignaturas/{id}	GET	Obtener asignatura específica

/api/asignaturas/profesor/{profesorId}	GET	Buscar por profesor

Servicio de Matrículas

Endpoint	Método	Descripción

/api/matriculas	GET	Listar matrículas

/api/matriculas/{id}	GET	Obtener matrícula específica

/api/matriculas/{id}/reducir-cupo	PATCH	Actualizar cupo de asignatura
Seguridad

JWT Authentication

Implementación de filtros JWT personalizados

Token Bearer para autenticación

Roles: ADMIN, PROFESOR, ESTUDIANTE

Validación de tokens en cada solicitud

Configuración de Seguridad
Copiar
@Configuration

@EnableWebSecurity

public class SecurityConfig {

    // Configuración de seguridad por microservicio
    
    // Filtros JWT personalizados
    
    // Gestión de roles y permisos
}
Containerización

Docker Compose

Contenedores independientes para cada servicio

Bases de datos MySQL separadas

Configuración de red y volúmenes

Puertos expuestos:

MySQL Asignaturas: 3307

MySQL Matrículas: 3308

MySQL Usuarios: 3309

Bases de Datos

Estructura
db_usuarios: Almacena información de usuarios y autenticación

db_asignaturas: Gestiona información de asignaturas y profesores

db_matriculas: Mantiene registro de matrículas
Instrucciones de Ejecución

Clonar el repositorio

Configurar variables de entorno:

Copiar

SPRING_DATASOURCE_URL=jdbc:mysql://localhost:330X/db_name

SPRING_DATASOURCE_USERNAME=root

SPRING_DATASOURCE_PASSWORD=Arauca2024**

Ejecutar Docker Compose:

Copiar

docker-compose up -d

Tecnologías Utilizadas

Spring Boot

Spring Cloud (Eureka, Config Server)

MySQL 8.0

Docker & Docker Compose

JWT para autenticación

FeignClient para comunicación entre servicios

Manejo de Errores

Validación de tokens JWT

Control de excepciones personalizado

Manejo de errores en comunicación entre servicios

Respuestas HTTP apropiadas según el error

Pruebas

Endpoints de prueba para validación de conexiones

Test Controller para verificar comunicación entre servicios

Validación de autenticación y autorización


