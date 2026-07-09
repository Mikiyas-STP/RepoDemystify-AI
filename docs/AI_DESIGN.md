# RepoDemystify AI — AI Architecture Design

## Overview

The AI system is the intelligence layer of RepoDemystify AI.

Its purpose is not to replace developers, but to help them understand software systems faster.

The AI layer provides:

- Repository explanations
- Code understanding
- Architecture descriptions
- Developer guidance
- Contribution recommendations

---

# AI Strategy

RepoDemystify AI follows an AI Application Engineering approach.

The project does not train a new LLM.

Instead, it builds a specialised application around existing models.

Architecture:

```
Repository Knowledge

        +

Large Language Model

        +

Application Logic

        =

AI Developer Assistant
```

---

# Why Use Existing LLMs?

Training a foundation model requires:

- enormous datasets
- expensive infrastructure
- specialised research teams

For this project, the valuable engineering challenge is:

- integrating AI
- designing context retrieval
- building useful workflows

---

# AI Pipeline Overview

```
Repository

    ↓

Repository Analysis

    ↓

Knowledge Extraction

    ↓

Embeddings Generation

    ↓

Vector Storage

    ↓

Context Retrieval

    ↓

Prompt Construction

    ↓

LLM

    ↓

Developer Response
```

---

# 1. Repository Analysis Layer

## Purpose

Convert raw code into structured information.

The system analyses:

- files
- directories
- dependencies
- configuration
- documentation

---

Example:

Input:

```
Spring Boot repository
```

Output:

```
Framework:
Spring Boot

Language:
Java

Database:
PostgreSQL

Architecture:
MVC
```

---

# 2. Knowledge Extraction

The system creates meaningful information.

Examples:

## Component Understanding

```
UserController

handles

User API requests
```

---

## Dependency Understanding

```
Controller

uses

UserService

uses

UserRepository
```

---

# 3. Embeddings

## Purpose

Convert text/code information into numerical representations.

Example:

```
Authentication service code

        ↓

Embedding vector

        ↓

Searchable meaning
```

---

# 4. Vector Database

Purpose:

Store and search repository knowledge.

Possible technologies:

- pgvector
- Chroma
- Weaviate

---

Example:

Question:

```
Where is authentication implemented?
```

The system finds:

```
SecurityConfig.java

UserDetailsService.java

AuthController.java
```

---

# 5. Retrieval Augmented Generation (RAG)

RAG is the core AI technique.

Instead of asking:

```
LLM:
Answer this question.
```

We ask:

```
LLM:

Here is relevant repository information.

Answer using this context.
```

---

# RAG Flow

```
User Question

        ↓

Search Repository Knowledge

        ↓

Retrieve Relevant Code

        ↓

Create Prompt

        ↓

LLM Response
```

---

# 6. LLM Integration

Initial approach:

```
Spring AI

↓

Ollama

↓

Local Model
```

---

Possible models:

- Llama
- Mistral
- Qwen

---

Future providers:

- OpenAI
- Anthropic
- Google Gemini
- Azure OpenAI

---

# AI Provider Architecture

The application should depend on an interface.

Example:

```
AIService

     |

     |

---------------------

|        |           |

Ollama   OpenAI   Gemini
```

This prevents vendor lock-in.

---

# Prompt Engineering

The system will use specialised prompts.

Example:

```
You are a senior software engineer.

Explain this repository to a junior developer.

Focus on architecture,
important files,
and contribution opportunities.
```

---

# AI Features

## Repository Explanation

Generate:

- purpose
- architecture
- technologies

---

## Code Explanation

Explain:

- classes
- functions
- relationships

---

## Contribution Guidance

Suggest:

- beginner tasks
- learning paths
- relevant files

---

# AI Quality Evaluation

AI responses should be evaluated.

Metrics:

## Accuracy

Is the explanation correct?

---

## Relevance

Does it answer the question?

---

## Context Usage

Did it use repository information?

---

# AI Safety Considerations

The system should:

- avoid exposing secrets
- protect private repositories
- respect permissions
- clearly communicate uncertainty

---

# Future AI Improvements

Possible additions:

## Agent Workflows

AI agents that:

- explore repositories
- create documentation
- suggest issues

---

## Code Graph Understanding

Build relationships between:

- classes
- functions
- modules

---

## Personalised Learning Paths

Adapt explanations based on developer experience.

---

# AI Philosophy

RepoDemystify AI focuses on:

```
Understanding before changing.

Knowledge before automation.

Assistance before replacement.
```

The goal is to help developers become better engineers.