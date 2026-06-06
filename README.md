# Opportunity Radar

**AI-powered Market Intelligence System**

Opportunity Radar monitors technology news, startup activity, product launches, and market signals to detect emerging business opportunities. This system combines AI agents, data pipelines, semantic search, and dashboards to produce actionable insights for businesses and technology strategists.

---

## Features

- Collects signals from news, RSS feeds, Hacker News, GitHub trending, and public business APIs.
- Deduplicates and stores signals in PostgreSQL using URL hashing and semantic similarity.
- Classifies signals by industry, technology, business model, and urgency with LLMs.
- Detects trends, market pain points, and opportunities using LangGraph AI workflows.
- Performs risk analysis and gathers supporting evidence.
- Provides semantic search across all signals and opportunity reports.
- Generates weekly AI-powered strategic reports in Markdown/PDF.
- Visualizes trends and opportunities in a Next.js + React dashboard with Recharts.

---

## Tech Stack

- **Backend:** Python, FastAPI, SQLAlchemy/SQLModel, Celery/Dramatiq
- **AI / Agent Layer:** LangGraph, LangChain/LlamaIndex (optional), OpenAI/Anthropic
- **Database:** PostgreSQL, pgvector, Redis
- **Frontend:** Next.js, TypeScript, Tailwind CSS, shadcn/ui, Recharts
- **DevOps:** Docker, Docker Compose, GitHub Actions, pre-commit hooks

---

## Installation

```bash
git clone https://github.com/your-username/opportunity-radar.git
cd opportunity-radar
docker-compose up --build
