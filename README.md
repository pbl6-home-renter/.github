<div align="center">

# 🏠 Rentify

### Rental management, connected from end to end

**A multi-repository platform that helps landlords and tenants manage the rental journey—from identity and property setup to contracts, billing, and mobile experiences.**

[Repositories](#-repository-map) · [Architecture](#-architecture-at-a-glance) · [Getting started](#-getting-started) · [Contributing](#-contributing)

</div>

---

## 📖 About

Rentify is an academic product ecosystem developed in the context of **PBL6**. It brings together backend services, web and mobile clients, shared API contracts, and deployment infrastructure in a coordinated multi-repository project.

The platform is designed around clear domain boundaries. Each service or client has its own responsibility, while the shared OpenAPI contract helps teams coordinate changes across the system.

> **This repository is the organization-level overview.** See the individual repositories for implementation details, setup instructions, and contribution guidelines.

## ✨ What Rentify supports

- **Identity and access** — account management, authentication, landlord profiles, and token issuing.
- **Property operations** — buildings, rooms, and Vietnam administrative units.
- **Rental workflows** — a foundation for contract and billing flows.
- **Landlord web experience** — browser-based tools for managing rental operations.
- **Mobile experience** — native Android apps for landlords and tenants.
- **Service integration** — API gateway routing and shared contracts across clients and services.
- **Deployment** — container-based deployment setup for AWS EC2 environments.

## 🧩 Repository map

| Repository | Role |
|---|---|
| [`api-gateway`](https://github.com/pbl6-home-renter/api-gateway) | Platform entry point for routing, JWT/JWKS authentication, CORS, rate limiting, and correlation IDs. |
| [`Identity-Service`](https://github.com/pbl6-home-renter/Identity-Service) | Identity domain: accounts, users, landlord profiles, and token issuing. |
| [`Tenancy-Service`](https://github.com/pbl6-home-renter/Tenancy-Service) | Tenancy domain: buildings, rooms, and Vietnam administrative units. |
| [`community-service`](https://github.com/pbl6-home-renter/community-service) | Community foundation for chat, notifications, and service-level integrations. |
| [`fe`](https://github.com/pbl6-home-renter/fe) | Landlord web application built with React, TypeScript, and Vite. |
| [`mobile`](https://github.com/pbl6-home-renter/mobile) | Native Android applications for landlords and tenants, built with Kotlin and a multi-module structure. |
| [`api-doc`](https://github.com/pbl6-home-renter/api-doc) | Shared OpenAPI contract for backend services, web, and mobile clients. |
| [`infra`](https://github.com/pbl6-home-renter/infra) | Deployment configuration using Docker Compose and Caddy for AWS EC2 environments. |
| [`boilerplate`](https://github.com/pbl6-home-renter/boilerplate) | NestJS backend starter using Clean Architecture, DDD, and CQRS patterns. |
| [`docs`](https://github.com/pbl6-home-renter/docs) | Product and project documentation, organized by phases: requirements, plans, decisions, and issue breakdowns. |

## 🏗️ Architecture at a glance

```text
┌───────────────────────┐       ┌───────────────────────┐
│      Landlord Web     │       │ Landlord & Tenant App │
│      React + Vite     │       │     Android / Kotlin  │
└───────────┬───────────┘       └───────────┬───────────┘
            │                               │
            └───────────────┬───────────────┘
                            ▼
                  ┌───────────────────┐
                  │    API Gateway    │
                  │ Auth, routing,    │
                  │ rate limits, etc. │
                  └─────────┬─────────┘
                            │
              ┌─────────────┼─────────────┐
              ▼             ▼             ▼
       ┌────────────┐ ┌────────────┐ ┌──────────────┐
       │  Identity  │ │  Tenancy   │ │  Community   │
       │  Service   │ │  Service   │ │   Service    │
       └────────────┘ └────────────┘ └──────────────┘

          Shared API contract: api-doc (OpenAPI)
          Deployment and operations: infra
```

### 🧭 Design principles

- **API-first collaboration** — coordinate API changes through `api-doc`.
- **Clear domain ownership** — services own their respective business areas.
- **Consistent client integration** — web and mobile use the shared API contract.
- **Reusable backend foundations** — bootstrap services from `boilerplate`.
- **Independent repositories** — teams can work within focused codebases and deliver scoped changes.

## 🛠️ Technology overview

| Area | Technologies |
|---|---|
| Landlord web | React, TypeScript, Vite |
| Android apps | Kotlin, multi-module architecture |
| Identity and gateway | JWT/JWKS-based authentication; see each repository for its implementation stack |
| Backend foundation | NestJS, Clean Architecture, DDD, CQRS |
| API contract | OpenAPI |
| Deployment | Docker Compose, Caddy, AWS EC2 |

> Technology details can vary by repository. Check that repository’s README for its current stack and setup.

## 🚀 Getting started

Rentify is split across repositories, so there is no single root application to install. A practical onboarding path is:

1. **Read [`docs`](https://github.com/pbl6-home-renter/docs)** to understand the product phases, scope, and decisions.
2. **Review [`api-doc`](https://github.com/pbl6-home-renter/api-doc)** to learn about the shared API contract.
3. **Choose a repository** based on the area you want to work on.
4. **Follow that repository’s README** for prerequisites, configuration, and local development steps.
5. **Check [`infra`](https://github.com/pbl6-home-renter/infra)** for deployment setup and environment-specific guidance.

## 🗺️ Roadmap ideas

These are potential directions for the ecosystem, not commitments or a release schedule:

- **Architecture portal** — publish diagrams, service ownership, and onboarding paths.
- **Unified release notes** — collect changes across repositories into one changelog.
- **API compatibility checks** — catch breaking contract changes in CI.
- **Observability baseline** — establish tracing, metrics, dashboards, and service health signals.
- **Security checks** — add secret scanning and dependency risk checks across repositories.
- **Local development bootstrap** — make it easier to start the services needed for a development task.

## 🤝 Contributing

Contributions are welcome. To keep work coordinated across repositories:

1. Read the relevant phase and scope documentation in [`docs`](https://github.com/pbl6-home-renter/docs).
2. Check [`api-doc`](https://github.com/pbl6-home-renter/api-doc) before changing or consuming an API.
3. Follow the conventions and setup instructions in the repository you are changing.
4. Keep pull requests focused, with a clear description of their scope and impact.
5. Coordinate cross-repository changes with the teams responsible for the affected components.

## 📌 Project status

Rentify is an **actively evolving academic product ecosystem** built in the PBL6 context. Its repositories demonstrate a production-style approach to service boundaries, client integration, API collaboration, and deployment.

---

<div align="center">

**Built as a connected product ecosystem, one focused repository at a time.**

</div>
