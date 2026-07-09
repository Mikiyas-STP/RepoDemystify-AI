# ADR-003: AI Provider Strategy

## Status

Accepted

---

# Context

RepoDemystify AI requires LLM capabilities for:

- code explanation
- repository questions
- documentation generation

The system should avoid depending on one AI provider.

---

# Options Considered

## Single Cloud Provider

Example:

OpenAI only

Advantages:

- Simple integration

Disadvantages:

- Vendor lock-in
- API costs

---

## Self-hosted Models Only

Example:

Ollama only

Advantages:

- Privacy
- No API cost

Disadvantages:

- Hardware requirements
- Model limitations

---

## Provider Abstraction

Support multiple providers.

Examples:

- Ollama
- OpenAI
- Gemini
- Anthropic

---

# Decision

RepoDemystify AI will use an AI abstraction layer.

Architecture:

```
Application

↓

AI Interface

↓

Provider Implementation
```

---

# Initial Development

Primary:

```
Spring AI

+

Ollama
```

Reason:

- Free development
- Local experimentation
- Privacy

---

# Future Support

Cloud providers can be added without changing business logic.

---

# Consequences

Benefits:

- Flexible architecture
- Lower costs
- Easier experimentation

Challenges:

- Additional abstraction complexity

---

# Final Principle

The project should own the intelligence workflow, not depend on one AI company.