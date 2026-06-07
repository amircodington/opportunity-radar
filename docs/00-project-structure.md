backend/
├── src/
│   ├── api/                        # FastAPI endpoints
│   │   ├── routes/                 # Individual route files
│   │   │   ├── signals.py
│   │   │   └── __init__.py
│   │   └── __init__.py
│   │
│   ├── core/                       # Core utilities & configuration
│   │   ├── config.py               # Environment variables & settings
│   │   ├── db.py                   # Database connection (PostgreSQL + pgvector)
│   │   ├── logger.py               # Centralized logging
│   │   └── utils.py                # Helper functions
│   │
│   ├── ingestion/                  # Data collection & crawling
│   │   ├── scrapy_project/         # Scrapy project for crawling
│   │   │   ├── scrapy.cfg
│   │   │   └── opportunity_radar/
│   │   │       ├── spiders/        # Individual spiders
│   │   │       │   ├── rss_spider.py
│   │   │       │   ├── news_api_spider.py
│   │   │       │   ├── github_trending_spider.py
│   │   │       │   └── blogs_spider.py
│   │   │       ├── items.py        # Scrapy Item definitions (RawSignalItem)
│   │   │       ├── pipelines.py    # Deduplication + PostgreSQL storage
│   │   │       └── settings.py     # Scrapy settings
│   │   └── scripts/                # Helper scripts (DB init, embeddings, tests)
│   │
│   ├── agents/                     # LangGraph agent workflows (future)
│   │   └── placeholder.py
│   │
│   ├── models/                     # Pydantic + SQLAlchemy/SQLModel schemas
│   │   ├── raw_signal.py
│   │   ├── source.py
│   │   └── company.py
│   │
│   └── main.py                     # FastAPI app entrypoint
│
├── tests/                           # Unit tests for backend
│   ├── test_api.py
│   └── test_ingestion.py
│
├── docs/                            # Project documentation
│   └── Phase1-Tasks.md
│
├── Dockerfile                        # Backend container
├── docker-compose.yml                 # Backend + Postgres + Redis
├── requirements.txt                   # Python dependencies
├── .gitignore
└── README.md
