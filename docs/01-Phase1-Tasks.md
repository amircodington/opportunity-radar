# Phase 1: MVP Data Pipeline – Opportunity Radar

**Objective:**  
Collect raw signals from news, RSS feeds, and public sources, deduplicate them, store in PostgreSQL, and expose a simple API.

---

## Epic 1: Environment Setup
**Goal:** Prepare development environment, dependencies, and project structure.

### Tasks:
1. **Create project skeleton**
   - Setup Python project structure (`src/`, `tests/`, `scripts/`, `docs/`)
   - Initialize Git repository
   - Setup `.gitignore`
2. **Setup virtual environment & dependencies**
   - Python 3.11+
   - FastAPI, Pydantic, SQLAlchemy/SQLModel
   - Celery or Dramatiq + Redis
   - PostgreSQL client (`psycopg2-binary`)
   - `feedparser`, `requests`, `beautifulsoup4`
3. **Setup Docker**
   - Dockerfile for backend
   - Docker Compose for Postgres + Redis + API
4. **Setup code quality tools**
   - `black`, `ruff`, `mypy`
   - Pre-commit hooks
5. **Create initial README placeholders**
   - Add project description, basic structure, license

---

## Epic 2: Data Source Integration
**Goal:** Collect signals from various sources reliably.

### Tasks:
1. **RSS feeds**
   - Identify initial RSS sources (tech, AI, startups)
   - Build Python ingestion script for RSS
2. **News APIs**
   - Connect to free news APIs (e.g., NewsAPI.org)
   - Implement Python script to fetch latest articles
3. **Company blogs / Product Launches**
   - Select 3–5 sample blogs
   - Build scraping script (requests + BeautifulSoup or Playwright)
   - Ensure legal compliance
4. **Other public sources**
   - Hacker News API integration
   - GitHub Trending scraping / API
   - Product Hunt API (where allowed)
5. **Signal metadata**
   - Capture source URL, timestamp, title, summary, content, tags

---

## Epic 3: Data Storage & Deduplication
**Goal:** Store raw signals in PostgreSQL and remove duplicates.

### Tasks:
1. **PostgreSQL database setup**
   - Define schema for `RawSignal`, `Source`, `Company`
   - Connect Python scripts to PostgreSQL
2. **Deduplication strategy**
   - URL hash check
   - Semantic similarity check using pgvector embeddings
   - Store embedding vectors in DB
3. **Redis caching**
   - Cache ingestion results
   - Store temporary embeddings for deduplication

---

## Epic 4: Background Jobs & Automation
**Goal:** Automate ingestion and processing.

### Tasks:
1. **Task queue setup**
   - Configure Celery / Dramatiq with Redis
2. **Scheduled ingestion**
   - Schedule periodic jobs for RSS and API fetching
3. **Error handling & logging**
   - Log failed fetches or parsing errors
   - Retry logic for transient errors
4. **Monitoring**
   - Simple console/log monitoring for ingestion status

---

## Epic 5: API Exposure
**Goal:** Provide access to collected signals via FastAPI.

### Tasks:
1. **FastAPI app setup**
   - Create main app structure
   - Configure database connection
2. **Endpoints**
   - `/signals` – List all collected signals
   - `/signals/{id}` – Get single signal details
   - Optional filters: source, date range
3. **Pydantic models**
   - `RawSignal`, `Source` models for API output
4. **Testing**
   - Basic endpoint tests (pytest + test database)
   - Ensure API returns expected JSON structure

---

## Epic 6: Documentation & Project Readiness
**Goal:** Ensure Phase 1 is properly documented and maintainable.

### Tasks:
1. **README updates**
   - Add installation instructions
   - Usage guide for API
2. **Docstrings**
   - Add docstrings to all Python functions/classes
3. **Folder structure documentation**
   - Explain purpose of `src/`, `tests/`, `scripts/`, `docs/`
4. **Next phase preparation**
   - Define placeholders for Phase 2 AI Classification layer

---

## Phase 1 Deliverables

- Dockerized backend with Postgres & Redis ready  
- Working ingestion scripts for RSS, news, blogs, GitHub, Hacker News  
- Deduplicated raw signals stored in PostgreSQL  
- Celery/Dramatiq scheduled ingestion jobs  
- FastAPI endpoints exposing raw signals  
- Documentation, code quality, and README ready
