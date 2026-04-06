<div align="center">

# Duque Ortega Mutis — MLOps Engineer

**I don't just deploy ML models. I diagnose why they break at 2am.**

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-3min_Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

---

## What Makes This Portfolio Different

</div>

Most ML portfolios show models that score well. This one shows what happens **after you deploy** — the incidents, the wrong decisions corrected, and 17 Architectural Decision Records documenting every trade-off with measured data.

```
Three production incidents diagnosed from first principles:

 81% error rate under load  →  uvicorn --workers is anti-pattern under K8s
                                (shared CPU budget = thrashing, not parallelism)
                                Fixed: asyncio + ThreadPoolExecutor, GIL analysis
                                Result: 81% errors → 0%, 2000m CPU → 1000m

 SHAP returning all zeros   →  TreeExplainer incompatible with StackingClassifier
                                Fixed: KernelExplainer in original feature space
                                Evaluated 4 alternatives before deciding

 HPA never scales down      →  Memory-based HPA + fixed ML footprint
                                = mathematically impossible to scale down
                                Fixed: CPU-only HPA, 3→1 pods in 8 minutes
```

---

<div align="center">

## Flagship Project — [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)

**3 ML services on GKE + EKS · 17 ADRs · 395+ tests · Multi-cloud Terraform**

[![CI](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml/badge.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml)
[![codecov](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio/branch/main/graph/badge.svg)](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)
[![K8s](https://img.shields.io/badge/K8s-GKE%20%2B%20EKS-326CE5?logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-Multi--Cloud-7B42BC?logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)

<img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Portfolio Demo" width="600">

</div>

| Project | Metric | Key Engineering Decision |
|---------|--------|--------------------------|
| [BankChurn Predictor](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/BankChurn-Predictor) | AUC **0.87** · 90% cov | Async inference via ThreadPoolExecutor · threshold 0.35 (30:1 cost ratio) |
| [NLPInsight Analyzer](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/NLPInsight-Analyzer) | Acc **80.6%** · 98% cov | Upgraded from curated dataset to 11.9K real noisy tweets — honest benchmark |
| [ChicagoTaxi Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/ChicagoTaxi-Demand-Pipeline) | R² **0.96** · 6.3M rows | Found & fixed data leakage · temporal split · R² 0.905→0.965 |

**Selected "Don't Build" decisions** *(harder than building)*:
- Removed CarVision because MAPE 32.9% is not defensible — documented in ADR-009
- Deferred Feature Store with full Feast architecture designed for when it's needed — ADR-007
- Rejected Airflow for drift retraining: CronJob→GitHub Actions is sufficient — ADR-006

📐 [View all 17 ADRs →](https://duqueom.github.io/ML-MLOps-Portfolio/architecture/decisions/) &nbsp;|&nbsp; 📋 [Engineering Highlights →](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/ENGINEERING_HIGHLIGHTS.md) &nbsp;|&nbsp; 📺 [3min Demo →](https://youtu.be/7dFFqq2ROPw)

---

## Stack

`Kubernetes` `GKE` `EKS` `Terraform` `GitHub Actions` `FastAPI` `MLflow` `Prometheus` `Grafana`
`Argo Rollouts` `Docker` `PySpark` `LightGBM` `XGBoost` `SHAP` `Evidently` `DVC` `Pandera`
`GCP` `AWS` `SageMaker` `Vertex AI` `OpenTelemetry` `Python 3.11+`

**AWS Certified Machine Learning — Specialty** · TripleTen Data Science Graduate · 14 years ops → MLOps

---

## Other Projects

| Repo | Description |
|------|-------------|
| [RestoPilotAI](https://github.com/DuqueOM/RestoPilotAI) | Full-stack AI app: FastAPI + Next.js 15 + Gemini · 17-stage agentic pipeline · 80+ endpoints |

---

## AI Transparency

These projects use AI-assisted tools (Cursor / Windsurf Cascade) for code generation and boilerplate. All architectural decisions, system design, trade-off analysis, and incident resolution are the author's. AI tools accelerate throughput — they don't replace engineering judgment.

---

<div align="center">

*Open to MLOps / ML Platform / ML Infrastructure roles — Remote preferred — Mexico City*

</div>