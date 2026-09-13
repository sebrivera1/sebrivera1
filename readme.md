# Sebastian Rivera

**AI/ML Engineering Manager · Agentic AI & LLM Systems · Quantitative Research**

I lead applied AI/ML teams and build the systems myself: agent workflows, retrieval pipelines, fine-tuned models, and the production infrastructure under them. My background is economics, statistics, and ML, with hands-on software and DevOps depth. I like taking research-quality work all the way into systems that people use every day.

## Selected work

### Enterprise AI — United Airlines
- **AI for the Mechanics Toolbox app:** Applied AI features for the first AI app used by aircraft maintenance technicians on the job.
- **AI for Airline Operations** Confidential 

### Agentic AI and LLM systems

- **Autonomous Quantitative Investment Research** *(UChicago MSADS capstone, 3-person team, private repo)*: A multi-agent **LangGraph** system that does the work of a junior quant researcher. It reads academic-finance papers and produces factor specifications and runnable replication code on Sharadar data. It runs 8 agents: paper triage → economic-quantity extraction → factor logic → spec planning → data mapping → spec building → time-series and cross-sectional code generation. **I was the top contributor (108 of 171 commits, ~13k lines of non-notebook code)** and owned: Data ingestion: via MinerU, Agent orchestration, Retrieval, Open-model tool-calling reliability, Inference infrastructure:, vLLM** on Lambda Labs GPUs, and Execution and evaluation infrastructure.

- **Liberated Learning RAG chatbot ("Embodied Alchemy")** *(solo build, 176 commits, private repo)*: A production retrieval-augmented guidance assistant for Liberated Learning LLC, grounded in the organization's somatic, teaching, and healing materials. I built it end to end:
  - **Retrieval:** **LangChain** with a persistent **Zilliz Cloud (managed Milvus)** vector store, so the knowledge base isn't rebuilt for each chat. It uses sentence-transformer embeddings and top-k retrieval, and answers include conversation history and optional source citations.
  - **Multimodal ingestion:** PDF, text, audio, and video. Audio and video are transcribed through **AssemblyAI**, and document metadata is validated with schema-error recovery before indexing.
  - **Swappable LLM backends:** OpenAI (GPT-4o-mini), **Kimi-K2-Instruct**, or any self-hosted **vLLM** endpoint, chosen through configuration.
  - **Serving:** a **FastAPI** service with guidance, admin-initialization, collection-status, and file-upload endpoints (admin-key auth, CORS), plus a password-protected, custom-themed **Gradio** chat front end. Deployed on Railway and DigitalOcean, with separate branches for the API and the UI.

### Applied ML and computer vision

- **SafeNet** *(private)*: Content-safety image classification. I ran a controlled comparison of three ways to adapt a ViT classifier on human-labeled screenshots: (A) partial fine-tuning with layer freezing, (B) a lightweight head on frozen ViT features, and (C) **LoRA via PEFT**. The comparison used repeated stratified k-fold cross-validation with per-fold seed control. Evaluation went beyond accuracy: ROC-AUC, PR-AUC, and balanced accuracy, bootstrap confidence intervals, **McNemar's test** for paired model comparison, and threshold diagnostics tuned to catch false negatives.
- **LLM fine-tuning:** Supervised fine-tuning of Llama-2-7B and TinyLlama with **Unsloth 4-bit QLoRA** and TRL's `SFTTrainer` on instruction data, tracked in Weights & Biases.
- **North Atlantic hurricane frequency and outcome prediction:** A hurricane-risk model trained on 60+ years of data. It combines NASA/NOAA climate signals (sea-surface temperature, wind shear) with EM-DAT and World Bank impact data to forecast hurricane frequency and economic damage across U.S. regions.

### Quantitative research

- **Factor research on WRDS data with PySpark:** Signal construction, portfolio sorts, cross-sectional regressions, and portfolio optimization on CRSP/Compustat data pulled from WRDS and FRED. Heavy joins and window operations run in **PySpark**. One example is a stock-level CAPE (Campbell & Shiller) value signal with a decile long-short backtest.

### Production systems I ship

- **liberated-learning-web**: A full production platform for an education organization. It has **180+ commits and ~50k lines** across an Astro site, a headless **Strapi 5** backend, a paid curriculum portal, and supporting microservices, all on Railway.
  - **Commerce-to-access automation:** A Shopify order-paid webhook creates buyer accounts and grants curriculum access automatically. I **found and fixed a race condition in find-or-create user under a live stress test**, made email delivery idempotent, and added webhook timeouts.
  - **Secure content delivery:** Curriculum files live in private **S3** with per-entry access scoping. A cron sweep migrates files from public storage to private S3.
  - **Security hardening:** CORS allowlisting, a login rate limiter that fixes IP detection behind the proxy (it reads `X-Forwarded-For`), a Strapi upgrade with CVE remediation, security headers, and an RBAC penetration test.
  - **Architecture:** I replaced ~30 hand-written routes with one CMS-driven catch-all, so publishing a new page no longer needs a deploy. I also built a standalone draft-preview microservice and publish-triggered auto-rebuild webhooks with cache-busting, and wrote incident write-ups and ops runbooks for non-technical editors.

## Technical toolkit

**LLM and agentic AI:** LangGraph, CrewAI, LangChain, ReAct tool-calling agents, RAG, BM25 retrieval, Milvus/Zilliz Cloud, LanceDB, GraphRAG, Neo4j, MinerU document parsing, AssemblyAI, vLLM (multi-LoRA serving), Kimi-K2, Hugging Face Transformers, PEFT/LoRA, Unsloth QLoRA, TRL, LLM-as-judge evaluation, OpenAI/Anthropic APIs

**ML and modeling:** Python, PyTorch, scikit-learn, Vision Transformers, time-series analysis, Monte Carlo simulation, hyperparameter optimization, statistical testing (bootstrap, McNemar, κ agreement), R

**Data engineering:** PySpark, Apache Airflow, Feast, LakeFS, SQL/Postgres, WRDS (CRSP/Compustat), pandas, Parquet

**MLOps and infrastructure:** MLflow, Databricks, Weights & Biases, FastAPI, Gradio, Docker, Railway, Lambda Labs GPUs, AWS S3, GCP, CI/CD, Git/GitHub

**Web and backend:** TypeScript/JavaScript, Node.js, Astro, Strapi, Shopify webhooks, React

## Let's connect

- [LinkedIn](https://www.linkedin.com/in/sebastian-rivera-01212)
- [GitHub](https://github.com/sebrivera1)

