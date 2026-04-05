<div align="center">

# Duque Ortega Mutis — MLOps Engineer

**I don't just deploy ML models. I diagnose why they break at 2am.**

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-3min_Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

---

## Why This Portfolio Stands Out

</div>

Most ML portfolios stop at model metrics. This one focuses on what happens **after deployment**: incidents, root-cause analysis, and the trade-offs behind each architectural decision, documented across 17 Architectural Decision Records with measured outcomes.

### Production incidents resolved from first principles

| Incident | Root cause | Fix | Outcome |
|---------|------------|-----|---------|
| 81% error rate under load | `uvicorn --workers` on K8s caused CPU thrashing rather than true parallelism | Switched to asyncio + `ThreadPoolExecutor`; validated GIL behavior | Errors 81% → 0%; CPU request 2000m → 1000m |
| SHAP returning all zeros | `TreeExplainer` was incompatible with `StackingClassifier` in this setup | Used `KernelExplainer` in the original feature space after evaluating 4 alternatives | Reliable feature attributions restored |
| HPA never scaled down | Memory-based HPA with a fixed ML footprint made scale-down mathematically impossible | Moved to CPU-only HPA | 3 → 1 pods in 8 minutes |

<sub>Concise by design: the details live in the project, the ADRs, and the demo.</sub>

---

<div align="center">

## Flagship Project — [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)

**3 ML services on GKE + EKS · 17 ADRs · 395+ tests · Multi-cloud Terraform**

[![CI](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml/badge.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml)
[![codecov](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio/branch/main/graph/badge.svg)](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)
[![K8s](https://img.shields.io/badge/K8s-GKE%20%2B%20EKS-326CE5?logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-Multi--Cloud-7B42BC?logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)

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

## AI Transparency

These projects use AI-assisted tools (Cursor / Windsurf Cascade) for code generation and boilerplate. All architectural decisions, system design, trade-off analysis, and incident resolution are the author's. AI tools accelerate throughput — they don't replace engineering judgment.

---

<div align="center">

*Open to MLOps / ML Platform / ML Infrastructure roles — Remote preferred — Mexico City*

</div>