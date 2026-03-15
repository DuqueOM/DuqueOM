<div align="center">

# Hey, I'm Duque Ortega Mutis 👋

**Junior MLOps Engineer** | Multi-Cloud K8s | Terraform | 395+ Tests | Entrepreneur → MLOps

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-3min_Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/qmw9VlgUcn8)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

---

## About Me

MLOps engineer with a production multi-cloud platform deployed from scratch (GKE + EKS, 6 K8s services, 395+ tests). 11 years running 5 businesses — managing teams, P&L, and vendor operations — now applied to building reliable ML systems.

- **AWS Certified Machine Learning — Specialty** | TripleTen Data Science Graduate
- Open to **MLOps / ML Infrastructure** roles (Remote preferred)
- Mexico City | Spanish (Native) & English (B2)

---

## Flagship Project

### [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio) — 3 ML Services on GKE + EKS

<div align="center">

[![CI Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml/badge.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml)
[![codecov](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio/branch/main/graph/badge.svg)](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)
[![Python](https://img.shields.io/badge/Python-3.11%20%7C%203.12-blue.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![K8s](https://img.shields.io/badge/K8s-GKE%20%2B%20EKS-326CE5?logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-Multi--Cloud-7B42BC?logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)
[![Docs](https://img.shields.io/badge/Docs-GitHub_Pages-blue?logo=github)](https://duqueom.github.io/ML-MLOps-Portfolio/)

</div>

| Project | Type | Key Metric | Tests |
|---------|------|------------|-------|
| [BankChurn Predictor](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/BankChurn-Predictor) | Classification | AUC 0.87 | 199 tests, 90% cov |
| [NLPInsight Analyzer](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/NLPInsight-Analyzer) | NLP Sentiment | Acc 80.6% | 74 tests, 98% cov |
| [ChicagoTaxi Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/ChicagoTaxi-Demand-Pipeline) | Demand Forecasting | R² 0.96 | 122 tests |

**What makes it production-grade:**
- **Multi-Cloud K8s**: GKE (4 nodes) + EKS (3 nodes), Terraform IaC, Kustomize overlays, HPA autoscaling, Network Policies, PDB
- **CI/CD**: GitHub Actions — 10-job matrix, security scanning (Trivy/Bandit/Gitleaks), automated deploy to both clouds
- **MLOps**: Daily drift detection CronJob (PSI), MLflow tracking (9 experiments), Prometheus + Grafana (26 panels, 16 alert rules)
- **Quality**: 395+ tests, 90–98% coverage ([Codecov](https://app.codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)), 13 ADRs, model cards, fairness audits, Pandera validation

<div align="center">

| GKE + EKS Side-by-Side | Grafana Monitoring |
|:---:|:---:|
| ![Multi-Cloud](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/aws-terminal/36-multicloud-side-by-side.png) | ![Grafana](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/monitoring/34-grafana-dashboard.png) |

<a href="https://youtu.be/qmw9VlgUcn8">
  <img src="https://img.shields.io/badge/▶_Watch_3min_Demo-YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="YouTube Demo">
</a>

</div>

---

## Tech Stack

<div align="center">

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/.github/workflows/ci-mlops.yml)
[![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=google-cloud&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform/gcp)
[![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform/aws)
[![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat-square&logo=apache-spark&logoColor=white)](https://spark.apache.org)
[![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Codecov](https://img.shields.io/badge/Codecov-F01F7A?style=flat-square&logo=codecov&logoColor=white)](https://app.codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)

</div>

---

## AI Transparency

These projects use AI-assisted tools (Cursor / Windsurf Cascade) for code generation and boilerplate acceleration. All architectural decisions, deployment strategy, and evaluation methodology are the author's. AI tools are accelerators, not replacements for understanding.

---

<div align="center">

[![Email](https://img.shields.io/badge/Email-DuqueOrtegaMutis@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-DuqueOM-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Docs-blue?style=flat-square&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![YouTube](https://img.shields.io/badge/YouTube-Demo-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://youtu.be/qmw9VlgUcn8)

*"I don't just train models — I build the infrastructure that makes them reliable."*

</div>
