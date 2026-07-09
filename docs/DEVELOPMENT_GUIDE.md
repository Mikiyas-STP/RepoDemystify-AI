# RepoDemystify AI — Development Guide

## Overview

This guide explains how developers can set up, run, and contribute to RepoDemystify AI.

The goal is to provide a consistent development experience for all contributors.

---

# Development Philosophy

RepoDemystify AI follows these principles:

## Understand Before Implementing

Developers should understand:

- the problem being solved
- the existing architecture
- the reason behind design decisions

before adding new features.

---

## Small, Focused Changes

Contributions should:

- solve one problem
- have clear scope
- include tests where appropriate

---

## Quality Over Speed

The project prioritises:

- readable code
- maintainability
- documentation
- testing

---

# Required Tools

Before contributing, install:

## Java

Version:

```
Java 21+
```

Used for:

- Spring Boot backend
- AI integration

---

## Node.js

Version:

```
Node.js 20+
```

Used for:

- React frontend

---

## PostgreSQL

Version:

```
PostgreSQL 16+
```

Used for:

- application data storage

---

## Docker

Used for:

- local services
- consistent environments

---

## Git

Used for:

- version control
- collaboration

---

# Project Setup

Clone the repository:

```bash
git clone https://github.com/Mikiyas-STP/RepoDemystify.git
```

Navigate:

```bash
cd RepoDemystify
```

---

# Backend Setup

Navigate:

```bash
cd backend
```

Build project:

```bash
./mvnw clean install
```

Run application:

```bash
./mvnw spring-boot:run
```

Backend runs:

```
http://localhost:8080
```

---

# Frontend Setup

Navigate:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Run development server:

```bash
npm run dev
```

Frontend runs:

```
http://localhost:5173
```

---

# Database Setup

Using Docker:

```bash
docker compose up postgres
```

Environment variables:

```
DATABASE_URL=
DATABASE_USERNAME=
DATABASE_PASSWORD=
```

---

# AI Development Setup

## Local AI

RepoDemystify supports local development using:

```
Ollama
```

Example:

```
Application

↓

Spring AI

↓

Ollama

↓

LLM Model
```

---

# Running Full Application

Start all services:

```bash
docker compose up
```

Expected services:

```
Frontend

Backend

PostgreSQL

AI Service
```

---

# Branch Strategy

The project uses:

```
main

↓

feature branches
```

Example:

```
feature/repository-analysis
```

---

# Commit Convention

Commits should follow:

```
type: description
```

Examples:

```
feat: add repository scanner

fix: resolve authentication bug

docs: update architecture guide

test: add repository service tests
```

---

# Testing Requirements

Before submitting a pull request:

Backend:

```bash
./mvnw test
```

Frontend:

```bash
npm test
```

---

# Pull Request Process

A contribution should include:

- Clear description
- Reason for change
- Tests
- Documentation updates if needed

---

# Code Review

Reviewers focus on:

- correctness
- maintainability
- security
- architectural consistency

---

# Recommended IDEs

Backend:

- IntelliJ IDEA
- VS Code

Frontend:

- VS Code

---

# Debugging

When encountering issues:

1. Check logs
2. Reproduce the problem
3. Create a minimal example
4. Ask for help with context

---

# Future Development Practices

The project may introduce:

- automated code quality checks
- CI pipelines
- dependency scanning
- release automation

---

# Conclusion

RepoDemystify AI is built as a learning-friendly but production-oriented open-source project.

Every contributor should focus on creating software that is understandable, maintainable, and valuable.