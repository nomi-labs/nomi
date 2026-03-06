<div align="center">

# Nomi

**Personal intelligence that truly knows you.**

An AI ecosystem for building persistent, context-aware personal assistants
that remember, learn, and evolve with every user.

</div>

---

## Table of Contents

- [Vision](#vision)
- [Architecture](#architecture)
- [Repositories](#repositories)
- [Roadmap](#roadmap)
- [Getting Started](#getting-started)
- [Technology Stack](#technology-stack)
- [Design Principles](#design-principles)

---

## Vision

Today's AI assistants are stateless — every conversation starts from zero. Nomi takes a fundamentally different approach.

We are building the infrastructure for **persistent personal AI**: an intelligence layer that retains context, understands user goals, and becomes more valuable over time.

A personal AI should:

- **Remember** what matters to the user
- **Understand** goals, habits, and preferences
- **Learn** from past decisions and interactions
- **Improve** continuously through accumulated context

Nomi is the foundation for that future — not a single product, but an ecosystem designed to power billions of personal intelligences.

---

## Architecture

Nomi follows a **layered architecture** with clear separation of concerns. Each service has a single responsibility and communicates through well-defined contracts.

```
┌─────────────────────────────────────────┐
│           nomi-company (future)         │
│      Organizational AI — Multi-Agent    │
├─────────────────────────────────────────┤
│               nomi-biseo                │
│         Personal AI Assistant           │
├─────────────────────────────────────────┤
│               nomi-core                 │
│         AI Execution Engine             │
└─────────────────────────────────────────┘
```

### nomi-core — AI Execution Engine

The unified runtime for all AI operations.

- LLM provider communication and abstraction
- Retry logic and fault tolerance
- Structured output validation
- Usage tracking and cost accounting

All AI providers are accessed exclusively through this layer, ensuring consistency and observability across the ecosystem.

### nomi-biseo — Personal AI Assistant

The product layer that understands the user.

- Goals, habits, tasks, and personal context
- Conversational interface and memory management

**nomi-biseo** determines *what* needs to happen. **nomi-core** handles *how* the AI executes it.

### nomi-company — Multi-Agent Intelligence *(Future)*

An organizational AI layer where specialized agents collaborate to perform complex reasoning, planning, and decision-making at scale.

---

## Repositories

| Repository     | Purpose                                      | Status       |
| -------------- | -------------------------------------------- | ------------ |
| `nomi`         | Ecosystem documentation and local development | 🔨 Active    |
| `nomi-shared`  | Shared types, schemas, and service contracts | 🔨 Building  |
| `nomi-core`    | AI execution engine (NestJS microservice)    | 🔨 Building  |
| `nomi-biseo`   | Personal AI assistant                        | 📋 Planned   |
| `nomi-company` | Multi-agent AI layer                         | 🔮 Future    |

---

## Roadmap

### Phase 1 — Foundation

Build the core AI infrastructure.

- [x] Ecosystem architecture
- [x] Repository structure
- [ ] `nomi-shared` — shared interfaces and schemas
- [ ] `nomi-core` MVP
  - Gemini adapter
  - Structured output validation
  - Cost tracking

### Phase 2 — Product

Launch the first personal AI assistant.

- [ ] `nomi-biseo` MVP
- [ ] Authentication
- [ ] Conversational interface
- [ ] Memory system
- [ ] Local development environment

**Deployment targets:**

| Service      | Platform |
| ------------ | -------- |
| `nomi-core`  | Railway  |
| `nomi-biseo` | Vercel   |

### Phase 3 — Scale

Expand capabilities across the ecosystem.

- [ ] Multi-LLM provider support
- [ ] Cost budgets and alerts
- [ ] Multi-agent orchestration
- [ ] Advanced memory and reasoning

---

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/) and Docker Compose
- A valid `GEMINI_API_KEY`

### Setup

```bash
git clone https://github.com/nomi-labs/nomi.git
cd nomi

cp .env.example .env
# Set your GEMINI_API_KEY in the .env file

docker compose up -d
```

### Services

| Service      | Address                 |
| ------------ | ----------------------- |
| nomi-biseo   | `http://localhost:3000`  |
| nomi-core    | `TCP localhost:4000`    |
| PostgreSQL   | `localhost:5432`        |
| Redis        | `localhost:6379`        |

---

## Technology Stack

| Layer              | Technology             |
| ------------------ | ---------------------- |
| Language           | TypeScript             |
| Framework          | NestJS                 |
| AI SDK             | Vercel AI SDK          |
| LLM Provider       | Google Gemini          |
| Schema Validation  | Zod                    |
| Database           | PostgreSQL + pgvector  |
| Cache              | Redis                  |
| Local Development  | Docker Compose         |

---

## Design Principles

| Principle                  | Description                                                              |
| -------------------------- | ------------------------------------------------------------------------ |
| **Single AI Engine**       | One execution engine powers the entire ecosystem.                        |
| **Memory-First AI**        | Context and personalization are first-class architectural concerns.       |
| **Full Observability**     | Every AI request is traceable by user, feature, and cost.                |
| **Provider Independence**  | LLM providers can be swapped without affecting product logic.            |
| **User Simplicity**        | Complex infrastructure, simple experience.                               |

---

<p align="center">
Built with intention by <strong>nomi-labs</strong>
</p>
