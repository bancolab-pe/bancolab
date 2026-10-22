# Arquitectura general

## Diagrama

```mermaid
flowchart TB
    app[App móvil del cliente]

    subgraph BancoLab
        bff[home-bff-service<br/>Pantalla de inicio]
        ex[exchange-service<br/>Tipo de cambio]
        pay[payment-service<br/>Pagos]
        tr[transfer-orchestrator<br/>Transferencias]
        acc[account-service<br/>Cuentas y saldos]
        fr[fraud-service<br/>Validación de fraude]
    end

    kafka[(Kafka)]
    redis[(Redis)]
    db[(PostgreSQL)]

    app --> bff
    app --> pay
    app --> tr
    bff --> ex
    ex --> redis
    ex --> db
    pay --> redis
    pay --> db
    tr <--> kafka
    acc <--> kafka
    fr <--> kafka
```

## Servicios

| Servicio | Responsabilidad | Tecnología | Estado |
|---|---|---|---|
| `exchange-service` | Calcula el tipo de cambio según el segmento del cliente | Spring WebFlux, Redis, PostgreSQL | Planificado |
| `home-bff-service` | Arma la pantalla de inicio llamando a varios servicios en paralelo | Spring WebFlux, Resilience4j | Planificado |
| `payment-service` | Procesa pagos sin cobros duplicados y controla límites diarios | Quarkus, Redis, PostgreSQL | Planificado |
| `transfer-orchestrator` | Coordina las transferencias interbancarias | Spring Boot, Kafka | Planificado |
| `account-service` | Gestiona cuentas y saldos | Spring Boot, Kafka | Planificado |
| `fraud-service` | Valida las operaciones antes de confirmarlas | Spring Boot, Kafka | Planificado |

## Infraestructura

- **Desarrollo local:** Docker Compose.
- **Nube:** Azure (AKS, ACR, Key Vault, Azure Database for PostgreSQL, Azure Cache for Redis, Event Hubs).
- **CI/CD:** GitHub Actions.