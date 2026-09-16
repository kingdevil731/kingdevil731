# Ruben Folhento

Full-stack engineer, 7+ years, TypeScript across the whole stack.

At [Quipu](https://getquipu.com) I own a Node.js compliance microservice end to end — Prisma, PostgreSQL, BullMQ, Docker — alongside React and React Native work on a live SaaS platform.

Outside that I design and build complete systems, and publish the architecture rather than the code. The repositories below document the decisions, the trade-offs, and what each system does *not* do.

📍 Maputo, Mozambique (UTC+2, full overlap with the European working day) · 🇵🇹 Portuguese citizen, EU work rights · relocating to Europe in 2027

---

## Architecture showcases

### [Events Platform](https://github.com/kingdevil731/events-platform-architecture)
Turborepo monorepo with six deployable surfaces — an Express/Prisma API, a React Native (Expo) app, three Next.js web surfaces, and a universal-link bridge — sharing one Zod contract package.

The interesting decision is a build-time product-mode system that ships a discovery-only V1 while keeping the entire transactional V2 path compiled and flagged off, so the transition is a config change rather than a rewrite. Also documents an offline venue check-in design with a six-state sync queue that routes every server disagreement to a human supervisor instead of resolving it silently.

`TypeScript` `Next.js` `React Native` `Express` `Prisma` `PostgreSQL` `Redis` `Docker`

### [Nome Terra](https://github.com/kingdevil731/nome-terra-architecture)
Realtime multiplayer word game. Socket.IO with the Redis adapter for multi-instance fanout, room state in Redis behind a repository interface with TTL-based expiry, typed socket contracts shared between client and server so a renamed event is a compile error.

Production refuses to fall back to in-memory state — it throws at boot instead, because a server that silently works under one instance and loses rooms under two is the expensive kind of bug.

[Live](https://nometerra.kingdevil731.dev) · `TypeScript` `Socket.IO` `Redis` `Node.js` `React`

### [Inventory & Operations Platform](https://github.com/kingdevil731/inventory-erp-architecture)
Multi-tenant business system, ~30 backend domain modules across stock, commerce and operations. Stock on hand is derived from an append-only movement ledger rather than stored as a mutable quantity, so any historical balance is reconstructible.

Currently being rebuilt. The repo includes a retrospective on why — it was competent software built for the wrong market, and that is the more useful thing to read.

`TypeScript` `Node.js` `Prisma` `PostgreSQL` `React`

---

## Stack

**Frontend** React · Next.js · React Native · TypeScript
**Backend** Node.js · Express · Prisma · PostgreSQL · REST · microservices
**Systems** Docker · Redis · BullMQ · Socket.IO · Turborepo · pnpm

---

## Open to

Remote product engineering, senior full-stack and founding-engineer roles. Contract, EOR or direct employment.

[Portfolio](https://kingdevil731.dev) · [LinkedIn](https://www.linkedin.com/in/ruben-folhento) · rubendejesusforner@gmail.com
