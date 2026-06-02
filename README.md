<div align="center">

```
███████╗ █████╗ ███╗   ██╗ ██████╗ ██████╗  █████╗ ███╗   ███╗    ███╗   ███╗ ██████╗ ██████╗ ███████╗
██╔════╝██╔══██╗████╗  ██║██╔════╝ ██╔══██╗██╔══██╗████╗ ████║    ████╗ ████║██╔═══██╗██╔══██╗██╔════╝
███████╗███████║██╔██╗ ██║██║  ███╗██████╔╝███████║██╔████╔██║    ██╔████╔██║██║   ██║██████╔╝█████╗  
╚════██║██╔══██║██║╚██╗██║██║   ██║██╔══██╗██╔══██║██║╚██╔╝██║    ██║╚██╔╝██║██║   ██║██╔══██╗██╔══╝  
███████║██║  ██║██║ ╚████║╚██████╔╝██║  ██║██║  ██║██║ ╚═╝ ██║    ██║ ╚═╝ ██║╚██████╔╝██║  ██║███████╗
╚══════╝╚═╝  ╚═╝╚═╝  ╚═══╝ ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝╚═╝     ╚═╝    ╚═╝     ╚═╝ ╚═════╝ ╚═╝  ╚═╝╚══════╝
```

### `Data Scientist · ML Engineer · LLM Systems · MLOps`

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sangrammore)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Sangram-More)
[![University of Colorado Boulder](https://img.shields.io/badge/CU%20Boulder-CFB87C?style=for-the-badge&logo=academia&logoColor=black)](https://www.colorado.edu)

---

*Building production ML systems — from RAG pipelines over SEC filings to MLOps loops that detect drift, retrain, and promote models automatically.*

</div>

---

## 🧠 About Me

I'm a Machine Learning engineer and researcher with a deep focus on **LLM systems**, **MLOps**, and **applied deep learning**. I design and build end-to-end intelligent systems — from data ingestion to live serving — with emphasis on robustness, reproducibility, and real-world impact.

My work sits at the intersection of:
- **LLM & RAG systems** — building, evaluating, and improving retrieval-augmented generation pipelines  
- **MLOps** — closing the full loop: drift detection → retraining → champion promotion → live serving  
- **NLP & Seq2Seq** — fine-tuning code-generation models on specialized corpora  
- **Applied ML** — ensemble learning, deep learning for healthcare and real-estate prediction  

---

## 🚀 Featured Projects

---

### 🏦 FinRAG — Financial RAG System Evaluation
> *Independent Study · University of Colorado Boulder · Spring 2026*

[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)](https://github.com/Sangram-More/Independent-Study---Financial-RAG-System-Evaluation)
[![Pinecone](https://img.shields.io/badge/Pinecone-000000?style=flat-square&logo=pinecone&logoColor=white)](https://www.pinecone.io)
[![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langchain&logoColor=white)](https://github.com/langchain-ai/langgraph)

A comparative study of **five RAG architectures** for question-answering over 14 SEC 10-K filings (Apple, Microsoft, Alphabet, Meta, NVIDIA — FY2023–2026).

**Systems evaluated:** Simple RAG · Self-RAG (LangGraph state machine) · Self-RAG + Query Decomposition · Speculative RAG · Multimodal RAG (chart/graph understanding)

| System | Faithfulness | Numerical Accuracy | Answer Relevance |
|---|---|---|---|
| Simple RAG | 0.256 | 0.296 | 0.335 |
| Self-RAG | 0.431 | 0.336 | 0.307 |
| Self-RAG + QD | 0.353 | **0.810** | **0.546** |
| **Speculative RAG** | **0.612** | 0.236 | 0.312 |
| Multimodal RAG | 0.377 | 0.133 | 0.161 |

**Key insight:** Chunking strategy rivals architecture choice in overall impact. Semantic chunking with Self-RAG + Query Decomposition achieves the highest numerical accuracy.

**Stack:** `BGE embeddings` · `Pinecone` · `Groq LLaMA` · `GPT-4o-mini` · `LangGraph` · `Llama-4 Vision`

🔗 [View Repository](https://github.com/Sangram-More/Independent-Study---Financial-RAG-System-Evaluation)

---

### 📦 Demand Forecasting MLOps Pipeline
> *Production-grade MLOps · Automated drift detection · Champion/challenger promotion*

[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/Sangram-More/demand-forecast-mlops)
[![MLflow](https://img.shields.io/badge/MLflow-3.12-0194E2?style=flat-square&logo=mlflow&logoColor=white)](https://mlflow.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://docker.com)
[![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)](https://grafana.com)

A fully closed MLOps loop — when input distribution shifts, the system **automatically detects drift, retrains, promotes the best model, and hot-swaps it into production without restarting**.

```
Drift Detected (PSI=1.73)
    → retrain_flag.json written
    → Prophet + XGBoost + LSTM compete
    → Best MAPE wins champion alias
    → API hot-swaps within 5 min
    → Grafana shows MAPE recovery
```

**Highlights:**
- 43,800 rows · 730 days · 20 SKUs · 3 stores (synthetic demand with drift at day 500)
- Champion MAPE: **7.78%** | Drift detection: **PSI = 1.73** on first hourly cycle
- p95 API latency: **< 80ms** on `/predict`
- Weekly GitHub Actions CI/CD retraining (every Monday 02:00 UTC)
- Training-serving feature parity via custom `FeatureStore`

**Stack:** `Prophet` · `XGBoost` · `PyTorch LSTM` · `MLflow` · `Evidently AI` · `FastAPI` · `Docker Compose` · `Prometheus` · `Grafana` · `DVC`

🔗 [View Repository](https://github.com/Sangram-More/demand-forecast-mlops)

---

### 💻 NLC2CMD — Natural Language to Bash Command Generation
> *NLP Final Project · University of Colorado Boulder · Spring 2025*

[![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)](https://github.com/Sangram-More/NLC2CMD-Natural-Language-to-Bash-Command-Generation)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)](https://pytorch.org)
[![CodeT5](https://img.shields.io/badge/CodeT5-Salesforce-00A1E0?style=flat-square)](https://huggingface.co/Salesforce/codet5-small)

A **seq2seq NLP system** that translates plain English command descriptions into executable Bash shell commands by fine-tuning `Salesforce/codet5-small` on the nl2bash corpus.

```
"Find all Python files modified in the last 7 days"
    → find . -name "*.py" -mtime -7
```

**Results on 2,070 validation examples:**

| Metric | Epoch 6 | Epoch 10 |
|---|---|---|
| BLEU | 0.3693 | **0.4026** |
| ROUGE-1 | 0.6983 | **0.7236** |
| ROUGE-L | 0.6795 | **0.7024** |
| Exact Match | 11.16% | **13.43%** |

**Stack:** `HuggingFace Transformers` · `CodeT5` · `PyTorch` · `Beam Search (k=5)` · `fp16` · `Google Colab T4`

🔗 [View Repository](https://github.com/Sangram-More/NLC2CMD-Natural-Language-to-Bash-Command-Generation)

---

### 📸 Photo Memory Finder

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/Sangram-More/Photo-Memory-Finder)

A Python tool for intelligent photo search and retrieval — surfacing memories from large local photo collections.

🔗 [View Repository](https://github.com/Sangram-More/Photo-Memory-Finder)

---

## 🛠️ Tech Stack

**LLM & RAG**

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)
![Pinecone](https://img.shields.io/badge/Pinecone-000000?style=flat-square)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Groq](https://img.shields.io/badge/Groq-F54E23?style=flat-square)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)

**ML & Deep Learning**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-FF7800?style=flat-square)
![Prophet](https://img.shields.io/badge/Prophet-0467DF?style=flat-square)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

**MLOps & Infrastructure**

![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)
![DVC](https://img.shields.io/badge/DVC-945DD6?style=flat-square&logo=dvc&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)
![Evidently AI](https://img.shields.io/badge/Evidently%20AI-7C3AED?style=flat-square)

**Data & Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

---

## 🎓 Education

**University of Colorado Boulder**  
*Master's in Data Science*

**University of Pune**  
*Bachelor's of Computer Engineering*

---

<div align="center">

*"The goal is not just to build a model — it's to build a system that stays correct."*

[![LinkedIn](https://img.shields.io/badge/Let's%20Connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sangrammore)

</div>
