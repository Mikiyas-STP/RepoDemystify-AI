# ADR-001: Choosing Spring Boot as Backend Framework

## Status

Accepted

## Date

2026

---

# Context

RepoDemystify AI requires a backend capable of:

- handling API requests
- processing repositories
- integrating with AI services
- managing authentication
- scaling as usage grows

The backend technology should support professional software development practices.

---

# Options Considered

## Option 1 — Node.js / Express

Advantages:

- Familiar ecosystem
- Fast development
- Large community

Disadvantages:

- Less aligned with the project's Java learning goals
- Dynamic typing can introduce runtime issues

---

## Option 2 — Python FastAPI

Advantages:

- Excellent AI ecosystem
- Fast development
- Strong ML community

Disadvantages:

- Separates AI application development from Java learning objectives

---

## Option 3 — Java Spring Boot

Advantages:

- Enterprise adoption
- Strong typing
- Mature ecosystem
- Excellent dependency injection
- Strong testing support
- Spring AI integration

Disadvantages:

- More initial complexity
- More verbose than some alternatives

---

# Decision

Spring Boot was selected as the primary backend framework.

---

# Reasoning

RepoDemystify AI is designed to demonstrate:

- professional Java development
- scalable backend architecture
- AI application engineering

Spring Boot provides the best balance between:

- learning value
- industry relevance
- scalability

---

# Consequences

Positive:

- Strong architecture foundation
- Enterprise-ready technology
- Excellent tooling

Negative:

- Higher learning curve
- More configuration compared with simpler frameworks

---

# Future Considerations

Python services may be introduced later for specialised AI workloads if required.