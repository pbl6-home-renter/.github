<div align="center">

# Rentify

**A full-stack rental management ecosystem for landlords and tenants.**

From identity and tenancy to web/mobile apps, API contracts, and infrastructure, Rentify is built as a multi-repo platform for real-world product development.

</div>

---

## ✨ What is Rentify?

Rentify helps rental businesses and room owners manage the full lifecycle of a rental operation:

- User identity and authentication
- Building/room management
- Contract and billing workflows
- Landlord web operations
- Tenant + landlord mobile experience
- API-first collaboration across teams

The project is organized as a microservice-friendly ecosystem with clear boundaries between domain services, frontend clients, and deployment infrastructure.

---

## 🧩 Repository Map (10 main repos)

| Repository | Purpose |
|---|---|
| [`api-gateway`](https://github.com/pbl6-home-renter/api-gateway) | Single entry point: routing, JWT/JWKS auth, CORS, rate limiting, correlation IDs. |
| [`Identity-Service`](https://github.com/pbl6-home-renter/Identity-Service) | Authentication and identity domain: accounts, users, landlord profile, token issuing. |
| [`Tenancy-Service`](https://github.com/pbl6-home-renter/Tenancy-Service) | Tenancy domain: buildings, rooms, and Vietnam administrative units. |
| [`community-service`](https://github.com/pbl6-home-renter/community-service) | Community domain foundation (chat/notification track and service-level integrations). |
| [`fe`](https://github.com/pbl6-home-renter/fe) | Landlord web app (React + TypeScript + Vite). |
| [`mobile`](https://github.com/pbl6-home-renter/mobile) | Native Android apps for landlord and tenant (Kotlin, multi-module). |
| [`api-doc`](https://github.com/pbl6-home-renter/api-doc) | Canonical OpenAPI contract shared across backend, web, and mobile. |
| [`infra`](https://github.com/pbl6-home-renter/infra) | Deployment setup (Docker Compose + Caddy) for AWS EC2 environments. |
| [`boilerplate`](https://github.com/pbl6-home-renter/boilerplate) | Backend template (NestJS, Clean Architecture, DDD, CQRS) used to bootstrap services. |
| [`docs`](https://github.com/pbl6-home-renter/docs) | Product/PM documentation by phases (requirements, plans, decisions, issue breakdown). |

> This `.github` repository is used for organization-level metadata and shared collaboration context.

---

## 🏗️ High-level Architecture

```text
Clients (fe, mobile)
        |
        v
   API Gateway
        |
        +--> Identity-Service
        +--> Tenancy-Service
        +--> community-service
        |
   Shared contract: api-doc (OpenAPI)
        |
Deployment & ops: infra
```

### Design principles

- **API-first collaboration**: define/lock contracts in `api-doc`.
- **Domain separation**: each service owns a clear business boundary.
- **Reusable backend patterns**: bootstrap from `boilerplate`.
- **Multi-client consistency**: web and mobile consume the same API contract.

---

## 🚀 Why this project is interesting

- Covers both **product** and **engineering** layers end-to-end.
- Demonstrates a realistic **multi-repo teamwork model**.
- Balances delivery speed with maintainable architecture.
- Suitable for learning modern backend/frontend/mobile integration in one ecosystem.

---

## 💡 Next ideas / roadmap

Potential directions to make Rentify even stronger:

1. **Public architecture portal**: diagrams + service ownership + onboarding paths.
2. **Unified release notes** across repos (changelog automation).
3. **Cross-repo CI quality gates** for API compatibility checks.
4. **Observability baseline**: tracing, metrics dashboards, error budgets.
5. **Security hardening**: secret scanning policies + dependency risk gates.
6. **Developer experience**: one-command local dev bootstrap for all services.

---

## 🤝 Contribution mindset

If you want to contribute, start with:

1. Reading `docs` to understand phase goals and scope.
2. Checking `api-doc` before implementing API changes.
3. Following service/app conventions in each repository.
4. Opening focused PRs with clear scope per repo.

---

## 📌 Project status

Rentify is an actively evolving academic-product ecosystem (PBL6 context) with production-style architecture and delivery practices.
