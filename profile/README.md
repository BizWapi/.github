# BizWapi

**Contributor-powered local intelligence, business viability reports and a verified property marketplace.**

Local contributors map the businesses in their neighbourhoods. Entrepreneurs buy reports built on that verified data. Contributors earn rewards whenever their data informs a paid report, and verified property listings later add viewing and transaction income.

---

## What we're building

Our first release focuses on **one complete commercial loop in a single, limited area**:

1. A contributor records and verifies a business location (for example, an M-Pesa agent in Nyalenda).
2. An entrepreneur purchases a viability report for that business type and area.
3. PostGIS queries identify the relevant verified locations and market signals.
4. The report records which version of each contribution influenced its conclusions.
5. A deterministic allocation credits the contributor's reward ledger.
6. The contributor sees the earning and can later redeem an eligible balance.

## Principles

- **Modular monolith first.** We split services only when an evidenced scaling or ownership boundary appears.
- **Geospatial data and provenance are first-class.** Every observation keeps its source, contributor and history.
- **Auditable rewards.** Financial entries are immutable, deterministic and safe against duplicate processing.
- **AI explains, it doesn't invent.** Measurements, scoring and regulatory facts come from deterministic, cited sources. AI only writes narrative from structured evidence.
- **RabbitMQ now, Kafka when justified.** We adopt streaming only when replay or high fan-out is measurably needed.

## Technology direction

| Area | Choice |
|---|---|
| Language / framework | Java, Spring Boot |
| Data | PostgreSQL + PostGIS |
| Messaging | RabbitMQ (Kafka only if criteria are met) |
| Reliability | Transactional outbox, idempotent consumers |
| Architecture style | Modular monolith, with a defined path to service extraction |

## How we make decisions

Significant decisions are recorded as **Architecture Decision Records (ADRs)** in [`docs/architecture`]([link-to-architecture-repo]).

- Every ADR has an owner, a decision deadline, supporting evidence, consequences and a measurable review trigger.
- ADRs are **immutable once accepted**. Changes are made through a superseding ADR, with both records linked.
- Implementation pull requests must reference the ADRs that govern them.

### Delivery gates

| Gate | Focus | ADRs |
|---|---|---|
| 1 | Product and platform foundation | 000–005 |
| 2 | Trusted contribution system | 006–009 |
| 3 | Paid reports and contributor earnings | 010–014 |
| 4 | Marketplace, security and operations | 015–019 |
| 5 | Scale and service evolution (only when triggered) | 020–022 |

### Roadmap

1. **Architecture inception**: platform boundary, module structure and spatial foundation
2. **Neighbourhood mapping MVP**: submit, verify and update places reliably
3. **Paid report pilot**: reproducible reports that create auditable contributor earnings
4. **Redemption launch**: reconciled balances and approved payment controls
5. **Property pilot**: verified listings, owner authority, paid viewings and contributor payouts
6. **Scale programme**: streaming, projections or service extraction, only when measured workloads justify it

## Repositories

| Repository | Description |
|---|---|
| [`[architecture-repo]`]([link]) | ADRs, templates and diagrams |
| [`[platform-repo]`]([link]) | Spring Boot modular monolith |
| [`[other-repo]`]([link]) | [Description] |

## Contributing

1. Read the relevant ADRs before proposing changes.
2. For architectural changes, open a new ADR using the [ADR template]([link-to-template]).
3. Reference governing ADRs in your pull request.
4. See `CONTRIBUTING.md` in each repository for local setup and code standards.

## Contact

[Contact email or link] · [Website]