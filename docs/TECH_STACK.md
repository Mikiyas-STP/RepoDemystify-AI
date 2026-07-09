# RepoDemystify AI — Technology Stack

## Overview

RepoDemystify AI is designed as a scalable full-stack AI application.

The technology choices are based on:

- Maintainability
- Scalability
- Developer experience
- Open-source ecosystem support
- Industry relevance

The platform uses Java for backend development, React for the user interface, PostgreSQL for data management, and modern AI technologies for repository understanding.

---

# System Architecture Overview

```
                    React Frontend
                         |
                         |
                         ↓
                  Spring Boot API
                         |
        --------------------------------
        |                              |
        ↓                              ↓
 PostgreSQL Database              AI Layer
                                        |
                                        ↓
                                   LLM Provider
```

---

# Backend Stack

## Java

### Version

Java 21+

### Purpose

Java is the primary backend language for RepoDemystify AI.

### Why Java?

Java was chosen because:

- It is widely used in enterprise software development
- It provides strong type safety
- It has excellent tooling and ecosystem support
- It is designed for large-scale applications
- It encourages maintainable object-oriented design

Java also provides an opportunity to apply professional software engineering principles:

- Object-oriented programming
- Design patterns
- Clean architecture
- Testing practices

---

# Spring Boot

### Purpose

Spring Boot provides the foundation for the backend application.

Responsibilities:

- REST API development
- Dependency injection
- Application configuration
- Security
- Database communication

### Why Spring Boot?

Spring Boot was selected because:

- It is one of the most popular Java backend frameworks
- It is widely used in professional environments
- It provides production-ready features
- It supports scalable application design

---

# Spring AI

### Purpose

Spring AI provides integration between Java applications and AI models.

Responsibilities:

- LLM communication
- Prompt management
- AI service abstraction
- Retrieval Augmented Generation (RAG)

### Why Spring AI?

Spring AI allows RepoDemystify AI to keep AI functionality inside the Java ecosystem.

Benefits:

- Maintains a Java-first architecture
- Uses Spring patterns developers already understand
- Simplifies LLM integration

---

# Backend Architecture Pattern

The backend will follow a layered architecture.

```
Controller Layer

        ↓

Service Layer

        ↓

Repository Layer

        ↓

Database
```

---

## Controller Layer

Responsible for:

- Receiving HTTP requests
- Validating input
- Returning responses

Example:

```
POST /repositories/analyse
```

---

## Service Layer

Responsible for:

- Business logic
- Repository analysis workflows
- AI orchestration

---

## Repository Layer

Responsible for:

- Database communication
- Data persistence

---

# Frontend Stack

## React

### Purpose

React provides the user interface for interacting with RepoDemystify AI.

Responsibilities:

- Dashboard
- Repository analysis views
- AI chat interface
- Architecture visualisations

### Why React?

React was chosen because:

- Large developer ecosystem
- Component-based architecture
- Strong industry adoption
- Excellent support for interactive applications

---

# TypeScript

### Purpose

Type-safe frontend development.

Benefits:

- Reduces runtime errors
- Improves maintainability
- Provides better developer experience

---

# Styling

## Tailwind CSS

Purpose:

- Rapid UI development
- Consistent design system
- Maintainable styling

---

# Database

## PostgreSQL

### Purpose

Primary relational database.

Stores:

- Users
- Repositories
- Analysis results
- Repository metadata
- AI conversations

---

## Why PostgreSQL?

Chosen because:

- Reliable relational database
- Strong SQL support
- Open-source
- Widely used professionally
- Works well with Spring Data JPA

---

# AI Technology

## Large Language Models (LLMs)

LLMs provide the reasoning capability behind RepoDemystify AI.

Responsibilities:

- Explain code
- Answer repository questions
- Generate documentation
- Create contributor guidance

---

# Initial AI Development Strategy

The project will support local AI models first.

Example:

```
Spring AI

↓

Ollama

↓

Local LLM
```

---

# Ollama

### Purpose

Ollama allows developers to run AI models locally.

Benefits:

- No API costs during development
- Privacy-friendly
- Easy experimentation

Possible models:

- Llama
- Mistral
- Qwen

---

# Retrieval Augmented Generation (RAG)

RAG allows the AI to answer questions using repository-specific information.

Flow:

```
Repository Code

        ↓

Code Analysis

        ↓

Embeddings

        ↓

Vector Storage

        ↓

Relevant Context Retrieval

        ↓

LLM Response
```

---

# Future AI Components

Possible future additions:

## Vector Database

Examples:

- pgvector
- Chroma
- Weaviate

Purpose:

Store searchable representations of code.

---

## AI Evaluation System

Measure:

- Answer accuracy
- Context relevance
- Response quality

---

# Development Tools

## Git & GitHub

Purpose:

- Version control
- Collaboration
- Open-source workflow

---

## Docker

Purpose:

Containerise:

- Backend
- Frontend
- Database
- AI services

Benefits:

- Consistent development environment
- Easier deployment

---

## GitHub Actions

Purpose:

Continuous Integration.

Automates:

- Testing
- Building
- Quality checks

---

# Testing Stack

## Backend

- JUnit
- Mockito
- Spring Boot Test

## Frontend

- Vitest
- React Testing Library

---

# Deployment (Future)

Possible deployment options:

## Backend

- AWS
- Azure
- Google Cloud

## Database

- Managed PostgreSQL

## AI

- Cloud LLM providers
- Self-hosted models

---

# Technology Philosophy

RepoDemystify AI follows these principles:

## Use proven technologies

Prefer stable, widely adopted tools.

---

## Keep architecture flexible

AI providers and infrastructure should be replaceable.

---

## Build for learning and production

The project should demonstrate:

- professional Java development
- modern AI application design
- scalable engineering practices

---

# Summary

| Area | Technology |
|---|---|
| Backend | Java 21 + Spring Boot |
| AI Integration | Spring AI |
| Frontend | React + TypeScript |
| Database | PostgreSQL |
| AI Runtime | Ollama + LLMs |
| Containerisation | Docker |
| CI/CD | GitHub Actions |
| Testing | JUnit + React Testing Library |