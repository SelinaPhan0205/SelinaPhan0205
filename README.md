<h1 align="center">Phan Thi Xuan Tien</h1>

<p align="center">
  <b>Data &amp; AI Systems Engineering Student @ UIT VNU-HCM</b><br/>
  I build data and LLM systems end-to-end — ingestion and lakehouse pipelines, retrieval and multi-agent workflows, model serving
</p>

<p align="center">
  <a href="mailto:xuantienphan2005@gmail.com">
    <img src="https://img.shields.io/badge/Email-xuantienphan2005%40gmail.com-0d1117?style=flat-square&logo=gmail&logoColor=EA4335&labelColor=161b22"/>
  </a>
  <a href="https://www.linkedin.com/in/selinaphan">
    <img src="https://img.shields.io/badge/LinkedIn-selinaphan-0d1117?style=flat-square&logo=linkedin&logoColor=0A66C2&labelColor=161b22"/>
  </a>
  <a href="https://github.com/SelinaPhan0205">
    <img src="https://img.shields.io/badge/GitHub-SelinaPhan0205-0d1117?style=flat-square&logo=github&logoColor=white&labelColor=161b22"/>
  </a>
</p>

---

## About

Information Technology undergraduate at the University of Information Technology (UIT), VNU-HCM — GPA **9.0/10.0**, expected graduation **March 2027**.

My work sits where data infrastructure meets applied AI. On the data side I build ingestion, streaming, and lakehouse pipelines; on the model side I reproduce recent papers, adapt them to a real domain, and measure what actually changed. Most of my projects need both, so I tend to own the flow from raw data through to a served result.

Currently targeting **Data Engineer** and **AI / LLM Engineer** internship and entry-level roles, and spending my own time on LLM serving and inference optimization.

- **UIT VNU-HCM** — Information Technology, GPA **9.0/10.0**
- Academic merit scholarship for **5 consecutive semesters**
- Second author on a paper accepted at **ACOMPA 2026**
- **IELTS Academic** — 6.5/9.0
- NVIDIA Certificate — Applications of AI for Anomaly Detection
- Ho Chi Minh City, Vietnam

---

## Applied AI / LLM Systems

### [Viet-Contract Auditor — Multi-Agent Legal Contract Audit with Graph RAG](https://github.com/SelinaPhan0205/Viet-Contract-Auditor)
> Automated auditing of Vietnamese contracts: LangGraph multi-agent pipeline over a LightRAG legal knowledge graph, with production storage and an incremental knowledge-update pipeline

**Role:** Paper reproduction lead / AI workflow

- Led the reproduction of LightRAG (Guo et al., 2024) and its adaptation to Vietnamese legal contract auditing
- Replaced relation sorting that dropped the subject of each relation with a **directed entity graph in Neo4j**
- Replaced fixed 1,200-token chunking with **semantic chunking**, so the article–clause–point structure of a statute survives retrieval
- Built the contract benchmark and ground truth the team used to verify model performance
- Redesigned the final agent flow and added a **context validator** node scoring coverage, relevance, and cross-references, with reworked retry/pass conditions
- Benchmarked generation backends end to end: Qwen 7B/14B/32B locally via Ollama, several Gemini Flash and Pro versions, free-tier hosted providers, then `gpt-4o-mini` to match the paper's setup

`Python` `LangGraph` `LightRAG` `Neo4j` `Qdrant` `PostgreSQL/pgvector` `MinIO` `PyIceberg` `Docker Compose` `Streamlit`

---

### [LAMPS Reproduction — LLM Multi-Agent Malicious Package Detection](https://github.com/SelinaPhan0205/LAMPS-system)
> Reproduction of an LLM-based multi-agent system for detecting malicious PyPI packages, restructured from a single script into composable modules

**Role:** Dataset reconstruction / benchmark

- Rebuilt **D2**, the multi-file benchmark the paper does not publish, from the public DataDog PyPI malware corpus and a local benign pool
- Deduplicated against D1 by file hash, and labelled **per file by CodeBERT inference** instead of propagating package-level labels
- Reconstructed benchmark reached **98.09% package-level accuracy at 100% recall** (paper: 99.5% on the original D2)
- Follow-up imbalance experiment: precision falls to **29.6% at a 1:50** malicious-to-benign ratio — not reported in the original paper

`Python` `Hugging Face Transformers` `CodeBERT` `CrewAI` `FastAPI` `Git`

---

## Data &amp; Platform Engineering

### [TrustFlow — Real-Time KOL Analytics Platform](https://github.com/SelinaPhan0205/TrustFlow)
> Real-time KOL trustworthiness and campaign analytics on a hybrid Lambda architecture, across a nine-microservice Dockerized cluster

**Role:** End-to-end system flow owner

- Owned the flow from ingestion through to model serving across the cluster
- Built event ingestion and Spark Structured Streaming processing on Kafka/Redpanda
- Built the **FastAPI serving layer** with three-tier graceful degradation, and a dual-role Redis acting as both online feature store and streaming state store — keeping a separate state-store service off the hot path
- Profiled latency percentiles under sustained load: mean run-level **p50 of 28.98 s (p95 29.98 s)** against a 30 s objective at 80 events/s
- Ran the five-criterion labelling pipeline as one of three annotators

`Python` `FastAPI` `Redis` `Spark Structured Streaming` `Kafka/Redpanda` `MinIO` `Iceberg` `Trino` `Airflow` `Docker`

---

### [SME Pulse — Financial Data Processing System](https://github.com/SelinaPhan0205/SME_Pulse)
> Financial analytics for SME data processing, revenue forecasting, and payment decision support

**Role:** Project Lead

- Led data collection, preprocessing, and lakehouse-oriented data organization
- Designed heuristic-based invoice and payment prioritization logic
- Supported the Prophet-based revenue forecasting workflow
- Designed the web workflow, UI flow, and API interaction flow for the application

`Python` `SQL` `Lakehouse` `Prophet` `Airflow` `PostgreSQL` `Figma`

---

## Research

**TrustFlow: A Real-Time Hybrid Lambda Architecture for KOL Analytics under Platform Anti-Bot Constraints**
Nguyen Anh Tuan, **Phan Thi Xuan Tien**, Pham Nguyen Phuc Toan, Ha Minh Tan
*Accepted at ACOMPA 2026 — Application track*

**Senior thesis (in progress)** — detecting coordinated inauthentic engagement around Vietnamese TikTok KOL/KOC campaigns with continuous-time dynamic graph neural networks

---

## Tech Stack

**AI / ML Systems**

![LangGraph](https://img.shields.io/badge/LangGraph-0d1117?style=flat-square&logo=langchain&logoColor=white)
![LightRAG](https://img.shields.io/badge/LightRAG-0d1117?style=flat-square&logo=openai&logoColor=white)
![RAG](https://img.shields.io/badge/RAG%20Workflow-0d1117?style=flat-square)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Neo4j](https://img.shields.io/badge/Neo4j-4581C3?style=flat-square&logo=neo4j&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=flat-square&logo=qdrant&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-0d1117?style=flat-square&logo=ollama&logoColor=white)
![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![Prophet](https://img.shields.io/badge/Prophet-0d1117?style=flat-square&logo=meta&logoColor=white)

**Data Engineering**

![Apache Spark](https://img.shields.io/badge/Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white)
![dbt](https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white)
![Apache Iceberg](https://img.shields.io/badge/Iceberg-2D2D2D?style=flat-square&logo=apache&logoColor=white)
![Trino](https://img.shields.io/badge/Trino-DD00A1?style=flat-square&logo=trino&logoColor=white)

**Serving &amp; Infrastructure**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![MinIO](https://img.shields.io/badge/MinIO-C72E49?style=flat-square&logo=minio&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Linux](https://img.shields.io/badge/Linux/WSL-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)

---

## GitHub Stats

<p align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=SelinaPhan0205&show_icons=true&theme=github_dark&hide_border=true&count_private=true&hide_title=true&rank_icon=github"/>
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SelinaPhan0205&layout=compact&theme=github_dark&hide_border=true&langs_count=6"/>
</p>

---

<p align="center">
  <sub>Open to Data Engineer / AI Engineer roles · Ho Chi Minh City · 2026</sub>
</p>
