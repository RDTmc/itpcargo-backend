# ITPCARGO — Backend

Microservicios backend para la plataforma ITPCARGO (Innovatech Chile).

## Microservicios

| Servicio | Puerto | Descripción |
|---|---|---|
| **Ventas** | 8080 | CRUD de ventas |
| **Despacho** | 8081 | CRUD de despachos |

## Estructura

```
itpcargo-backend/
├── Springboot-API-REST/          ← Microservicio Ventas
└── Springboot-API-REST-DESPACHO/ ← Microservicio Despacho
```

## Tecnologías

- Java 17 + Spring Boot 3.x
- Maven Wrapper
- MySQL / AWS RDS

## Endpoints

### Ventas
- `GET /api/v1/ventas` — Listar ventas
- `GET /api/v1/ventas/{id}` — Obtener venta por ID
- `PUT /api/v1/ventas/{id}` — Actualizar venta

### Despacho
- `GET /api/v1/despachos` — Listar despachos
- `GET /api/v1/despachos/{id}` — Obtener despacho por ID
- `POST /api/v1/despachos` — Crear despacho

---
Evaluación Parcial N°2 — Despliegue de Microservicios en AWS.
