# Nomi

> **AI for Everyone — Personal intelligence that truly knows you.**

Nomi is an AI ecosystem built around one belief:

**Every person deserves a personal AI that understands them.**

Not a chatbot that resets every conversation.
Not a generic assistant.

But an intelligence that **remembers, learns, and grows with you over time.**

---

# Vision

The future of AI is not one super-intelligence.

It is **billions of personal intelligences — one for every human.**

An AI that understands your life, remembers your context, and evolves with you.

Today's assistants forget everything.
Every conversation starts from zero.

We believe AI should be different.

A personal AI should:

* remember what matters to you
* understand your goals and habits
* learn from your decisions
* become more useful over time

AI should not be something you occasionally ask questions to.

It should be **an intelligence that grows with you.**

**Nomi is building the foundation for that future.**

---

# Ecosystem Architecture

Nomi is designed as a **layered ecosystem**, where each service has a single responsibility.

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

Each layer focuses on a different role in the system.

### `nomi-core`

The **AI execution engine**.

Responsible for:

* LLM communication
* retries and reliability
* structured output validation
* usage and cost tracking

All AI providers are accessed through this layer.

---

### `nomi-biseo`

The **personal AI assistant**.

It understands the user:

* goals
* habits
* tasks
* personal context

`nomi-biseo` decides **what needs to happen**.
`nomi-core` executes **how the AI performs it**.

---

### `nomi-company` (Future)

A **multi-agent intelligence layer**.

Specialized AI agents collaborate like a team to perform complex reasoning, planning, and decision-making.

---

# Repositories

| Repository     | Purpose                                       | Status      |
| -------------- | --------------------------------------------- | ----------- |
| `nomi`         | Ecosystem documentation and local development | 🔨 Active   |
| `nomi-shared`  | Shared types, schemas, and service contracts  | 🔨 Building |
| `nomi-core`    | AI execution engine (NestJS microservice)     | 🔨 Building |
| `nomi-biseo`   | Personal AI assistant                         | 📋 Planned  |
| `nomi-company` | Multi-agent AI layer                          | 🔮 Future   |

---

# Roadmap

Nomi is built in progressive phases.

## Phase 1 — Foundation

Build the AI infrastructure layer.

* [x] Ecosystem architecture
* [x] Repository structure
* [ ] `nomi-shared` — shared interfaces and schemas
* [ ] `nomi-core` MVP

  * Gemini adapter
  * structured output validation
  * cost tracking

---

## Phase 2 — Product

Launch the first personal AI assistant.

* [ ] `nomi-biseo` MVP
* [ ] authentication
* [ ] conversational interface
* [ ] memory system
* [ ] local development environment

Deployment:

```
nomi-core  → Railway
nomi-biseo → Vercel
```

---

## Phase 3 — Scale

Expand the ecosystem.

* [ ] multi-LLM provider support
* [ ] cost budgets and alerts
* [ ] multi-agent orchestration
* [ ] advanced memory and reasoning

---

# Local Development

Run the entire ecosystem locally.

```bash
git clone https://github.com/nomi-labs/nomi.git
cd nomi

cp .env.example .env
# Add GEMINI_API_KEY

docker compose up -d
```

Services:

| Service    | Address               |
| ---------- | --------------------- |
| nomi-biseo | http://localhost:3000 |
| nomi-core  | TCP localhost:4000    |
| PostgreSQL | localhost:5432        |
| Redis      | localhost:6379        |

---

# Technology Stack

| Layer             | Technology            |
| ----------------- | --------------------- |
| Language          | TypeScript            |
| Framework         | NestJS                |
| AI SDK            | Vercel AI SDK         |
| LLM               | Google Gemini         |
| Schema Validation | Zod                   |
| Database          | PostgreSQL + pgvector |
| Cache             | Redis                 |
| Local Dev         | Docker Compose        |

---

# Design Principles

Nomi is built with long-term architectural discipline.

**Single AI Engine**
One execution engine powers the ecosystem.

**Memory-First AI**
Context and personalization are first-class citizens.

**Full Observability**
Every AI request is traceable — user, feature, and cost.

**Provider Independence**
LLM providers can be swapped without affecting product logic.

**User Simplicity**
Complex infrastructure, simple experience.

---

<p align="center">
Built with intention by <b>nomi-labs</b>
</p>
