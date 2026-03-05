# Nomi

> AI for Everyone — Personal intelligence that knows you.

Nomi is an AI ecosystem built around one belief: every person deserves an AI that truly knows them. Not a chatbot that resets every conversation. Not a generic assistant. A personal AI that remembers, learns, and grows with you over time.

---

## Ecosystem

Nomi is composed of three layers. Each layer is an independent service with a single responsibility.

```
┌─────────────────────────────────────────┐
│           nomi-company (future)         │
│       Organizational AI — Multi-agent   │
├─────────────────────────────────────────┤
│               nomi-biseo                │
│         Personal AI Assistant           │
├─────────────────────────────────────────┤
│               nomi-core                 │
│         AI Execution Engine             │
└─────────────────────────────────────────┘
```

| Repo | Role | Status |
|------|------|--------|
| [`nomi-shared`](https://github.com/nomi-labs/nomi-shared) | Shared types, interfaces & schemas | 🔨 Building |
| [`nomi-core`](https://github.com/nomi-labs/nomi-core) | AI execution engine (NestJS Microservice) | 🔨 Building |
| [`nomi-biseo`](https://github.com/nomi-labs/nomi-biseo) | Personal AI assistant | 📋 Planned |
| [`nomi-company`](https://github.com/nomi-labs/nomi-company) | Multi-agent organizational AI | 🔮 Future |

---

## How It Works

**nomi-core** is the execution backbone. It handles all LLM communication, retries, structured output validation, and cost tracking. No other layer talks to an AI provider directly.

**nomi-biseo** is the human-facing product. It knows the user — their goals, habits, tasks, and context. It defines *what* to do. Core defines *how* to execute it.

**nomi-company** (future) is where AI operates like an organization — multiple agents with different roles collaborating to handle complex reasoning on behalf of the user.

---

## Local Development

Run the entire Nomi ecosystem locally with a single command.

```bash
# Clone this repo
git clone https://github.com/nomi-labs/nomi.git
cd nomi

# Copy environment variables
cp .env.example .env
# Fill in: GEMINI_API_KEY

# Start everything
docker compose up -d
```

| Service | URL / Port |
|---------|------------|
| nomi-biseo | http://localhost:3000 |
| nomi-core | TCP localhost:4000 |
| PostgreSQL | localhost:5432 |
| Redis | localhost:6379 |

---

## Design Principles

- **One engine, multiple products** — nomi-core powers everything, stays infrastructure-only
- **Memory is not optional** — context and personalization are first-class citizens
- **Every AI call is traceable** — user, feature, cost tracked on every request
- **Infrastructure is replaceable** — swap any LLM provider without touching product logic
- **Simple for the user, disciplined in the architecture**

---

## Roadmap

### Phase 1 — Foundation
- [x] Ecosystem architecture design
- [x] Repository structure
- [ ] `nomi-shared` — interfaces & schemas
- [ ] `nomi-core` MVP — execution engine, Gemini adapter, cost tracking

### Phase 2 — Product
- [ ] `nomi-biseo` MVP — auth, chat, memory
- [ ] Local docker-compose setup
- [ ] Cloud deployment (nomi-core → Railway, nomi-biseo → Vercel)

### Phase 3 — Scale
- [ ] Multiple LLM provider support
- [ ] Cost budget & alerts
- [ ] `nomi-company` — multi-agent orchestration

---

## Tech Stack

| Layer | Technology |
|-------|------------|
| Language | TypeScript |
| Framework | NestJS |
| AI SDK | Vercel AI SDK |
| Primary LLM | Google Gemini |
| Schema Validation | Zod |
| Database | PostgreSQL + pgvector |
| Cache | Redis |
| Local Dev | Docker Compose |

---

## Repository Structure

```
github.com/nomi-labs/
├── nomi          ← You are here (docs + local dev)
├── nomi-shared   ← Shared contracts between all services
├── nomi-core     ← AI execution microservice
├── nomi-biseo    ← Personal assistant application
└── nomi-company  ← Multi-agent layer (future)
```

---

<p align="center">
  Built with intention by <a href="https://github.com/nomi-labs">nomi-labs</a>
</p>