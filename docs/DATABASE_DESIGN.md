# RepoDemystify AI — Database Design

## Overview

The database is responsible for storing the core information required by RepoDemystify AI.

It stores:

- Users
- Imported repositories
- Repository analysis results
- Code structure information
- AI conversations
- Contribution recommendations

The database design follows relational modelling principles to ensure:

- Data consistency
- Clear relationships
- Scalability
- Maintainability

---

# Database Technology

## Primary Database

PostgreSQL

---

## Why PostgreSQL?

PostgreSQL was chosen because:

- It is open source
- It is reliable for production systems
- It supports complex relationships
- It integrates well with Java and Spring Boot
- It supports future vector search through pgvector

---

# High-Level Entity Relationship

```
User

 |

 |

Repository

 |

 |

Analysis

 |

 |

Repository Knowledge

 |

 |

AI Conversation
```

---

# Core Entities

The initial database contains:

1. User
2. Repository
3. Analysis
4. Repository File
5. Technology
6. AI Conversation
7. Contribution Recommendation

---

# Entity 1 — User

## Purpose

Stores application users.

---

## Table

```
users
```

---

## Fields

| Field | Type | Description |
|-|-|-|
| id | UUID | Primary key |
| username | VARCHAR | User display name |
| email | VARCHAR | User email |
| password_hash | VARCHAR | Encrypted password |
| created_at | TIMESTAMP | Account creation date |

---

## Relationships

One user can analyse many repositories.

```
User

1

|

*

Repository
```

---

# Entity 2 — Repository

## Purpose

Stores imported repositories.

---

## Table

```
repositories
```

---

## Fields

| Field | Type | Description |
|-|-|-|
| id | UUID | Primary key |
| user_id | UUID | Owner |
| name | VARCHAR | Repository name |
| url | VARCHAR | GitHub URL |
| description | TEXT | Repository description |
| status | VARCHAR | Analysis status |
| created_at | TIMESTAMP | Creation date |

---

## Status Example

```
PENDING

ANALYSING

COMPLETED

FAILED
```

---

# Entity 3 — Analysis

## Purpose

Stores generated repository analysis.

---

## Table

```
analyses
```

---

## Fields

| Field | Type |
|-|-|
| id | UUID |
| repository_id | UUID |
| summary | TEXT |
| architecture_description | TEXT |
| generated_at | TIMESTAMP |

---

## Relationship

```
Repository

1

|

1

Analysis
```

---

# Entity 4 — Repository File

## Purpose

Stores important files discovered during analysis.

---

## Table

```
repository_files
```

---

## Fields

| Field | Type |
|-|-|
| id | UUID |
| repository_id | UUID |
| file_path | VARCHAR |
| language | VARCHAR |
| importance_score | FLOAT |

---

## Example Data

```
src/main/java/UserController.java

Language:
Java

Importance:
0.92
```

---

# Entity 5 — Technology

## Purpose

Stores detected technologies.

Examples:

- Spring Boot
- React
- PostgreSQL
- Docker

---

## Table

```
technologies
```

---

## Fields

| Field | Type |
|-|-|
| id | UUID |
| name | VARCHAR |
| category | VARCHAR |

---

## Relationship

Many technologies can belong to many repositories.

```
Repository

*

|

*

Technology
```

Requires:

```
repository_technology
```

join table.

---

# Entity 6 — AI Conversation

## Purpose

Stores user questions and AI responses.

---

## Table

```
ai_conversations
```

---

## Fields

| Field | Type |
|-|-|
| id | UUID |
| repository_id | UUID |
| question | TEXT |
| answer | TEXT |
| created_at | TIMESTAMP |

---

# Entity 7 — Contribution Recommendation

## Purpose

Stores AI-generated contribution guidance.

---

## Table

```
contribution_recommendations
```

---

## Fields

| Field | Type |
|-|-|
| id | UUID |
| repository_id | UUID |
| title | VARCHAR |
| description | TEXT |
| difficulty | VARCHAR |

---

# Future Vector Data Storage

For AI search, the system may use embeddings.

Possible option:

PostgreSQL + pgvector

---

## Vector Storage Example

```
Code File

↓

Embedding

↓

Vector

↓

Similarity Search

↓

Relevant Context
```

---

# Database Relationships Summary

```
User

 |
 |

Repository

 |
 |

Analysis

 |
 |

Repository Files

 |
 |

AI Knowledge

 |
 |

AI Conversation
```

---

# Data Migration

The project will use:

- Flyway
or
- Liquibase

for database version control.

Example:

```
V1_create_users.sql

V2_create_repository.sql

V3_create_analysis.sql
```

---

# Design Principles

## Normalisation

Avoid duplicate information.

---

## Clear Ownership

Every piece of data has a clear relationship.

---

## Future Scalability

The design allows:

- more AI features
- more users
- more repository types
- enterprise support

---

# Future Improvements

Possible additions:

- Team organisations
- Repository permissions
- GitHub integration
- Issue tracking
- Pull request analysis
