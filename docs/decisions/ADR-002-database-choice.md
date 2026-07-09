# ADR-002: Choosing PostgreSQL as Database

## Status

Accepted

---

# Context

RepoDemystify AI requires storage for:

- users
- repositories
- analysis results
- conversations
- repository knowledge

The database must support structured relational data.

---

# Options Considered

## PostgreSQL

Advantages:

- Open source
- Reliable
- Strong SQL support
- Excellent Java integration
- Supports vector extensions

---

## MongoDB

Advantages:

- Flexible document model
- Easy storage of JSON data

Disadvantages:

- Less suitable for highly relational data

---

## MySQL

Advantages:

- Mature ecosystem
- Widely used

Disadvantages:

- PostgreSQL provides stronger advanced features

---

# Decision

PostgreSQL was selected.

---

# Reasoning

The application contains many relationships:

```
User

↓

Repository

↓

Analysis

↓

Knowledge
```

A relational database model fits this structure.

---

# Future Expansion

PostgreSQL can support AI search through:

```
pgvector
```

allowing storage of embeddings.