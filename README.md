# Rooibos Radar AI Agent

An AI-powered content assistant for [Rooibos Radar](https://rooibosradar.com) — your go-to newsletter covering African startups, innovation, and policy.  
The agent automates **topic discovery**, **research**, **draft writing**, and **Substack draft publishing**.

---

## 🚀 Features
- Collects trending African tech news from RSS feeds & curated sources.
- Summarizes and indexes content in a vector database.
- Uses LLM + RAG to generate newsletter-ready drafts in the Rooibos Radar voice.
- Provides citations for all claims.
- Exports drafts directly to Substack for final editing.

---

## 🛠 Tech Stack
- **Backend**: Python, FastAPI
- **Worker Queue**: Celery + Redis
- **Vector DB**: Chroma
- **Embeddings**: OpenAI
- **Scraping**: Playwright / Newspaper3k
- **Deployment**: Docker, Render/Vercel

---

## 📂 Project Structure
rooibos-radar-ai-agent/
│
├── src/                     # All application source code
│   ├── __init__.py
│   ├── main.py               # FastAPI entrypoint
│   ├── config.py             # Settings/env variables
│   ├── ingestion/            # Feed & web scraping
│   │   ├── __init__.py
│   │   ├── rss_collector.py
│   │   └── web_scraper.py
│   ├── indexing/             # Embedding & vector DB ops
│   │   ├── __init__.py
│   │   ├── embedder.py
│   │   └── indexer.py
│   ├── generation/           # LLM & prompt templates
│   │   ├── __init__.py
│   │   ├── prompt_templates.py
│   │   ├── rag_pipeline.py
│   │   └── draft_writer.py
│   ├── publishing/           # Draft export & Substack integration
│   │   ├── __init__.py
│   │   ├── substack_api.py
│   │   └── formatter.py
│   └── utils/                # Helpers
│       ├── __init__.py
│       ├── text_cleaner.py
│       └── logger.py
│
├── tests/                    # Unit & integration tests
│   ├── __init__.py
│   ├── test_ingestion.py
│   ├── test_indexing.py
│   └── test_generation.py
│
├── data/                     # Sample feeds, cached pages (gitignored)
│   └── sample_feeds.json
│
├── .env.example              # Environment variable template
├── requirements.txt          # Python dependencies
├── README.md                 # Project documentation
├── .gitignore
└── LICENSE
