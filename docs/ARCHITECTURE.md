# RepoDemystify AI — System Architecture

## Overview

RepoDemystify AI is designed as a modular full-stack AI application.

The system analyses software repositories, extracts useful information, stores knowledge about the codebase, and provides AI-powered guidance to developers.

The architecture is designed around these principles:

- Separation of responsibilities
- Scalability
- Maintainability
- Replaceable AI providers
- Clear boundaries between components

---

# High-Level Architecture

```
                         User

                          |
                          |
                          ↓

                  React Frontend

                          |
                          |
                          ↓

                 Spring Boot Backend

                          |
        -------------------------------------

        |                 |                 |

        ↓                 ↓                 ↓

 Repository        Analysis Engine      AI Service
 Service

        |                 |                 |

        ↓                 ↓                 ↓

             PostgreSQL Database

                          |

                          ↓

                  Vector Knowledge Store

                          |

                          ↓

                         LLM
```

---

# Core Components

RepoDemystify AI consists of several major components:

1. Frontend Application
2. Backend API
3. Repository Analysis Engine
4. Knowledge Management System
5. AI Processing Layer
6. Database Layer

---

# 1. Frontend Application

## Technology

- React
- TypeScript
- Tailwind CSS

## Responsibility

The frontend provides the user interface for developers interacting with RepoDemystify AI.

Users can:

- Submit repositories
- View repository analysis
- Explore architecture
- Ask questions
- Follow contribution guidance

---

## Main Features

### Repository Dashboard

Displays:

- Repository information
- Technologies detected
- Structure overview
- Analysis status

---

### Architecture Explorer

Provides:

- Module relationships
- Dependency information
- System diagrams

---

### AI Assistant Interface

Allows developers to ask:

Examples:

```
Explain authentication.

Where should I start reading this project?

Which files are responsible for user management?
```

---

# 2. Spring Boot Backend

## Responsibility

The backend is the central application layer.

It handles:

- API requests
- Business logic
- Authentication
- Repository processing
- AI coordination

---

# Backend Layer Architecture

```
Controller Layer

        ↓

Service Layer

        ↓

Domain Layer

        ↓

Repository Layer

        ↓

Database
```

---

# Controller Layer

Purpose:

Handle HTTP communication.

Examples:

```
POST /repositories

GET /repositories/{id}

POST /chat
```

Responsibilities:

- Validate requests
- Call services
- Return responses

---

# Service Layer

Purpose:

Contains application logic.

Examples:

- Repository analysis workflow
- AI orchestration
- User management

---

# Repository Layer

Purpose:

Database interaction.

Uses:

- Spring Data JPA
- Hibernate

---

# 3. Repository Analysis Engine

## Purpose

The analysis engine is responsible for understanding software repositories.

This is the foundation of RepoDemystify AI.

---

## Analysis Pipeline

```
Repository

     ↓

File Scanner

     ↓

Language Detection

     ↓

Dependency Analysis

     ↓

Structure Analysis

     ↓

Knowledge Extraction
```

---

## Repository Scanner

Responsibilities:

- Read repository files
- Identify project structure
- Ignore unnecessary files

Examples:

Ignored:

```
node_modules/
target/
.git/
```

Important:

```
src/
pom.xml
package.json
README.md
docker-compose.yml
```

---

## Language Detection

Identifies:

Examples:

```
Java
Python
JavaScript
TypeScript
SQL
```

---

## Dependency Analysis

Detects:

Examples:

Java:

```
Spring Boot
Hibernate
Maven dependencies
```

JavaScript:

```
React
Express
Packages
```

---

# 4. Knowledge Management System

## Purpose

Convert repository information into structured knowledge.

The system creates:

- Repository summaries
- Architecture information
- Component relationships
- Searchable context

---

# Knowledge Flow

```
Repository Data

      ↓

Processed Information

      ↓

Structured Knowledge

      ↓

AI Context
```

---

# 5. AI Processing Layer

## Purpose

Provides intelligence using LLMs.

Responsibilities:

- Explanation generation
- Question answering
- Documentation creation
- Contribution guidance

---

# AI Architecture

```
User Question

       ↓

Context Retrieval

       ↓

Relevant Repository Information

       ↓

Prompt Construction

       ↓

LLM

       ↓

Response
```

---

# Retrieval Augmented Generation (RAG)

RAG allows the AI to answer based on the repository instead of general knowledge.

Example:

Question:

```
Where is authentication implemented?
```

Process:

```
Search repository knowledge

↓

Find authentication files

↓

Provide context to LLM

↓

Generate answer
```

---

# 6. Database Layer

## PostgreSQL

Stores:

- Users
- Repositories
- Analysis results
- Conversations
- Metadata

---

# Future Vector Database

A vector database may store:

- Code embeddings
- Documentation embeddings
- Repository knowledge

Possible technologies:

- pgvector
- Chroma
- Weaviate

---

# Data Flow Example

User imports repository:

```
User

↓

Frontend

↓

Spring Boot API

↓

Repository Service

↓

Analysis Engine

↓

Database

↓

AI Processing

↓

Generated Explanation

↓

Frontend Display
```

---

# Scalability Considerations

## Asynchronous Processing

Repository analysis may take time.

Future architecture:

```
API Request

↓

Message Queue

↓

Background Worker

↓

Analysis Result
```

Possible technologies:

- RabbitMQ
- Kafka

---

## AI Provider Abstraction

The system should not depend on one AI provider.

Architecture:

```
Application

↓

AI Interface

↓

Ollama
OpenAI
Anthropic
Gemini
```

---

# Security Considerations

Important areas:

- Repository access permissions
- API authentication
- Sensitive code handling
- Secret detection

---

# Architecture Principles

## Single Responsibility

Each component has one clear purpose.

---

## Loose Coupling

Components can be replaced without rewriting the whole system.

---

## Open Source Friendly

The architecture should allow contributors to work independently.

---

# Future Architecture Vision

RepoDemystify AI can evolve into a complete software intelligence platform:

```
Repository

↓

Understanding

↓

Documentation

↓

Learning Path

↓

Contribution Assistance
```

The goal is to make complex software understandable.