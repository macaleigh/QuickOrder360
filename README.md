##  Integrantes

Macarena Leighton | Desarrolladora FullStack |


##  Descripción del Proyecto

QuickOrder360 es una plataforma de pedidos que permite gestionar clientes, productos, pedidos, pagos, despachos y notificaciones a través de una arquitectura distribuida de 10 microservicios independientes, comunicados mediante REST y centralizados por un API Gateway.


##  Microservicios Implementados

| # | Microservicio | Puerto | Base de Datos | Descripción |
|---|---------------|--------|---------------|-------------|
| 1 | ms-clientes | 8081 | db_clientes | Gestión de clientes registrados |
| 2 | ms-productos | 8082 | db_productos | Catálogo de productos disponibles |
| 3 | ms-inventario | 8083 | db_inventario | Control de stock y stock mínimo |
| 4 | ms-pedidos | 8084 | db_pedidos | Registro y estado de pedidos |
| 5 | ms-detalle-pedido | 8085 | db_detalle_pedido | Detalle de productos por pedido |
| 6 | ms-pagos | 8086 | db_pagos | Procesamiento de pagos |
| 7 | ms-despachos | 8087 | db_despachos | Gestión de despachos y entregas |
| 8 | ms-usuarios | 8088 | db_usuarios | Gestión de usuarios del sistema |
| 9 | ms-reclamos | 8089 | db_reclamos | Registro de reclamos por pedido |
| 10 | ms-notificaciones | 8090 | db_notificaciones | Envío de notificaciones a usuarios |
| 11 | api-gateway | 8080 | — | Enrutamiento centralizado |

---

##  Rutas principales del API Gateway

| Ruta Gateway | Microservicio destino |

| `http://localhost:8080/api/v1/clientes/**` | ms-clientes (8081) |
| `http://localhost:8080/api/v1/productos/**` | ms-productos (8082) |
| `http://localhost:8080/api/v1/inventario/**` | ms-inventario (8083) |
| `http://localhost:8080/api/v1/pedidos/**` | ms-pedidos (8084) |
| `http://localhost:8080/api/v1/detalle-pedido/**` | ms-detalle-pedido (8085) |
| `http://localhost:8080/api/v1/pagos/**` | ms-pagos (8086) |
| `http://localhost:8080/api/v1/despachos/**` | ms-despachos (8087) |
| `http://localhost:8080/api/v1/usuarios/**` | ms-usuarios (8088) |
| `http://localhost:8080/api/v1/reclamos/**` | ms-reclamos (8089) |
| `http://localhost:8080/api/v1/notificaciones/**` | ms-notificaciones (8090) |



##  Documentación Swagger / OpenAPI

Cada microservicio expone su documentación en:

Microservicio | URL Swagger UI 

| ms-clientes | http://localhost:8081/doc/swagger-ui.html |
| ms-productos | http://localhost:8082/doc/swagger-ui.html |
| ms-inventario | http://localhost:8083/doc/swagger-ui.html |
| ms-pedidos | http://localhost:8084/doc/swagger-ui.html |
| ms-detalle-pedido | http://localhost:8085/doc/swagger-ui.html |
| ms-pagos | http://localhost:8086/doc/swagger-ui.html |
| ms-despachos | http://localhost:8087/doc/swagger-ui.html |
| ms-usuarios | http://localhost:8088/doc/swagger-ui.html |
| ms-reclamos | http://localhost:8089/doc/swagger-ui.html |
| ms-notificaciones | http://localhost:8090/doc/swagger-ui.html |



##  Tecnologías utilizadas

- Java 21
- Spring Boot 3.5.14
- Spring Cloud Gateway
- Spring Data JPA / Hibernate
- Spring Boot Validation
- MySQL + Flyway
- Lombok
- JUnit 5 + Mockito
- springdoc-openapi 2.8.3 (Swagger UI)
- Maven
- GitHub



##  Instrucciones de ejecución local

### Requisitos previos
- Java 21 instalado
- MySQL corriendo en `localhost:3306`
- Laragon o MySQL Workbench
- IntelliJ IDEA

### Pasos

1. Clonar el repositorio:
```bash
git clone https://github.com/macaleigh/QuickOrder360.git
```

2. Crear las bases de datos en MySQL:
```sql
CREATE DATABASE db_clientes;
CREATE DATABASE db_productos;
CREATE DATABASE db_inventario;
CREATE DATABASE db_pedidos;
CREATE DATABASE db_detalle_pedido;
CREATE DATABASE db_pagos;
CREATE DATABASE db_despachos;
CREATE DATABASE db_usuarios;
CREATE DATABASE db_reclamos;
CREATE DATABASE db_notificaciones;
```

3. Abrir cada microservicio en IntelliJ y ejecutar desde la clase principal `MsXxxApplication.java`

4. Ejecutar el API Gateway desde `ApiGatewayApplication.java`

5. Verificar que todos los servicios estén corriendo accediendo a sus puertos respectivos.

### Ejecutar pruebas unitarias

Desde cada microservicio:
```bash
./mvnw test
```
O clic derecho sobre la clase de test en IntelliJ → **Run**.

---

## Gestión del proyecto

- **Tablero Trello:** https://trello.com/invite/b/6a3cdb65ab1c3ad641263f9a/ATTI76b80cba912cb7e8ed31b5f7c27261d611C0958E/ev3-quickorder360
- **Repositorio GitHub:** https://github.com/macaleigh/QuickOrder360


