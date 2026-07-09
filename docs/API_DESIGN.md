# RepoDemystify AI — API Design

## Overview

The RepoDemystify AI backend exposes REST APIs that allow the frontend and external clients to interact with repository analysis, AI assistance, and user functionality.

The API design follows REST principles:

- Clear resource-based URLs
- HTTP methods
- JSON communication
- Stateless requests

---

# API Base URL

Development:

```
http://localhost:8080/api
```

Future production:

```
https://api.repodemystify.ai/api
```

---

# Authentication

Future versions will support:

- User registration
- Login
- JWT authentication
- OAuth with GitHub

Example:

```
Authorization: Bearer <token>
```

---

# Repository API

## Create Repository Analysis

### Endpoint

```
POST /repositories
```

Purpose:

Submit a repository for analysis.

---

## Request

```json
{
  "repositoryUrl": "https://github.com/example/project"
}
```

---

## Response

```json
{
  "id": 1,
  "status": "ANALYSING",
  "repositoryUrl": "https://github.com/example/project"
}
```

---

# Get Repository Information

## Endpoint

```
GET /repositories/{id}
```

Purpose:

Retrieve repository analysis.

---

## Response

```json
{
  "id": 1,
  "name": "example-project",
  "language": "Java",
  "framework": "Spring Boot",
  "status": "COMPLETED"
}
```

---

# Repository Structure API

## Endpoint

```
GET /repositories/{id}/structure
```

Purpose:

Retrieve analysed file structure.

---

Response:

```json
{
  "directories": [
    "src/main/java",
    "src/test/java"
  ],
  "importantFiles": [
    "pom.xml",
    "application.properties"
  ]
}
```

---

# Architecture API

## Endpoint

```
GET /repositories/{id}/architecture
```

Purpose:

Return architecture analysis.

---

Response:

```json
{
  "layers": [
    {
      "name": "Controller",
      "description": "Handles HTTP requests"
    },
    {
      "name": "Service",
      "description": "Contains business logic"
    }
  ]
}
```

---

# AI Assistant API

## Ask Repository Question

### Endpoint

```
POST /repositories/{id}/chat
```

Purpose:

Ask questions about a repository.

---

Request:

```json
{
  "question": "How does authentication work?"
}
```

---

Response:

```json
{
  "answer": "Authentication is handled through Spring Security configuration..."
}
```

---

# Contribution Guidance API

## Generate Contributor Path

Endpoint:

```
POST /repositories/{id}/contribution-guide
```

Purpose:

Generate a learning path for contributors.

---

Response:

```json
{
  "recommendations": [
    {
      "title": "Understand authentication module",
      "difficulty": "Beginner"
    },
    {
      "title": "Improve documentation",
      "difficulty": "Easy"
    }
  ]
}
```

---

# Analysis Status API

## Endpoint

```
GET /repositories/{id}/status
```

Purpose:

Check analysis progress.

---

Response:

```json
{
  "status": "PROCESSING",
  "progress": 65
}
```

---

# User API

## Register User

```
POST /users/register
```

---

Request:

```json
{
  "username": "developer",
  "email": "user@example.com",
  "password": "password"
}
```

---

# Health Check API

Endpoint:

```
GET /health
```

Response:

```json
{
  "status": "UP"
}
```

---

# Error Handling

All errors follow a standard format.

Example:

```json
{
  "timestamp": "2026-01-01T12:00:00",
  "status": 404,
  "message": "Repository not found"
}
```

---

# API Versioning

Future versions will use:

```
/api/v1/
```

Example:

```
/api/v1/repositories
```

This allows future changes without breaking clients.

---

# API Design Principles

## Consistency

All endpoints follow predictable patterns.

---

## Security

Sensitive operations require authentication.

---

## Scalability

Long-running operations such as repository analysis will move to asynchronous processing.

---

# Future API Expansion

Possible additions:

## Webhooks

For GitHub repository updates.

---

## Real-time Analysis

Using:

- WebSockets
- Server Sent Events

---

## External Integrations

Future support:

- GitHub Apps
- GitLab
- Bitbucket

---

# Summary

The API layer provides the bridge between developers, repositories, and AI intelligence.

It is designed to support the growth of RepoDemystify AI from a simple analysis tool into a complete developer onboarding platform.