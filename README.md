# IluminAI
1. Short Description (GitHub About / Tagline) IluminAi: Next-generation AI atlas for rare diseases connecting patients, researchers, and biotechnology through shared cellular mechanisms and biological signatures
# 🧬 IluminAi: Next-Generation Rare Disease Atlas & Knowledge Engine

**IluminAi** is an interactive, AI-driven biomedical atlas built on knowledge graphs designed to dismantle research silos across more than 10,000 rare conditions by connecting patients, researchers, and biotechnology through shared cellular mechanisms and biological signatures.

---

## 🧭 Project Vision & Architecture

The repository decouples the bioinformatic data processing pipelines from the spatial visualization client:

* **Bioinformatics & Data Pipeline (`/scripts` and `/data`):** Python pipelines for ingesting, mapping, and validating genomic entities from PubMed, ClinVar, HPO, and clinical trial registries (including monogenic pathway modeling such as CACNA1A and Dee69 dataset batches).
* **Atlas Frontend Client (`/atlas`):** Interactive web application built with Vite, React, and TypeScript featuring 3D biomedical graph rendering (`Graph3D.tsx`), dual-language localization (`i18n.ts`), and an empathetic conversational assistant guided by Ziva (`ZivaChat.tsx`).
* **Brand Assets & Governance (`/docs`):** Complete brand identity manual (`IluminAI-Brand-Book.pdf`), design tokens, voice guidelines, and mascot state assets.

---

## 📂 Repository Structure

```text
iluminai/
├── atlas/                       # Web Application (Frontend + Graph Explorer)
│   ├── api/
│   │   └── ask.ts               # Serverless endpoint function for queries
│   ├── eval/
│   │   └── ask_eval.ts          # Response benchmarking and evaluation suite
│   ├── public/
│   │   ├── brand/               # Official logos and Ziva mascot asset illustrations
│   │   └── data/                # Pre-built graph exports (graph.json, gaps.json, runs)
│   ├── src/
│   │   ├── App.tsx              # Application root component
│   │   ├── Graph3D.tsx          # 3D interactive knowledge graph visualization
│   │   ├── FindInGraph.tsx      # Multi-entity filtering and search engine
│   │   ├── SidePanel.tsx        # Clinical detail views and evidence explorer
│   │   ├── ZivaChat.tsx         # Conversational multimodal chat interface
│   │   ├── subgraph.ts          # Local subgraph calculations and pathway tracing
│   │   └── i18n.ts              # Internationalization engine (Spanish / English)
│   ├── package.json             # Vite/React configuration and dependencies
│   └── vite.config.ts           # Bundler build configuration
├── data/                        # Knowledge graph data stores and analysis
│   ├── nodes.json / edges.json  # Primary biomedical graph nodes and relational edges
│   ├── gaps.md                  # Literature gap and research asymmetry reports
│   ├── id_map.json              # Cross-reference identifier normalizations
│   └── contrib/                 # Ingestion datasets (dee69, scrapers)
├── scripts/                     # Automated data pipelines and bioinformatic scripts
│   ├── build_graph.py           # Core graph assembly and harmonization
│   ├── build_full_cacna1a.py    # CACNA1A monogenic disease pathway pipeline
│   ├── search_clinvar_variants.py
│   ├── verify_ids.py            # Biomedical entity cross-validation (OMIM/ClinVar)
│   ├── gap_map.py               # Research gap detection and density mapping
│   └── openai_extract.py        # Abstract entity extraction pipeline
├── docs/                        # Brand identity guide, typography, and UX specs
├── DEPLOY.md                    # Production deployment instructions
└── README.md                    # Core project documentation
