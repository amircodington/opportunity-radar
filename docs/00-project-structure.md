opportunity-radar/
│
├── backend/                # Backend code (Python API + ingestion + AI agents)
│   ├── src/
│   │   ├── api/            # FastAPI endpoints
│   │   │   ├── routes/
│   │   │   └── __init__.py
│   │   ├── core/           # Core logic: DB, settings, utils
│   │   ├── ingestion/      # Scripts for RSS, news APIs, scraping
│   │   ├── agents/         # LangGraph nodes & workflows
│   │   ├── models/         # Pydantic models + SQLAlchemy/SQLModel schemas
│   │   └── main.py         # FastAPI app entrypoint
│   │
│   ├── tests/              # Unit tests for backend
│   ├── scripts/            # Helper scripts (DB init, embeddings, maintenance)
│   ├── requirements.txt    # Python dependencies
│   ├── Dockerfile          # Backend container
│   └── docker-compose.yml  # Backend + DB + Redis services
│
├── frontend/               # (Future) Next.js dashboard
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── next.config.js
│
├── docs/                   # Project documentation
│
├── .gitignore
├── LICENSE
└── README.md
