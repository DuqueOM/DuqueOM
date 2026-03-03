<div align="center">

# Hey, I'm Duque Ortega Mutis 👋

**ML Engineer** | Multi-Cloud MLOps · Kubernetes · Terraform · 85-99% Test Coverage (323 tests)

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/qmw9VlgUcn8)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

![Profile Views](https://komarev.com/ghpvc/?username=DuqueOM&color=blue&style=flat-square&label=Profile+Views)

</div>

---

## 🎯 About Me

ML Engineer based in Mexico City with 14 years of high-pressure operations experience, now building cloud-native ML systems. My background taught me that **production systems must remain reliable under pressure** and that consistency beats short-term heroics.

- 🎓 **TripleTen Data Science Professional Program** (Completed March 2026)
- 📜 **AWS Machine Learning Specialty** — Certified
- 💼 Open to **ML Engineer / MLOps** opportunities (Remote/Hybrid)
- 🌎 Mexico City, Mexico | Spanish (Native) & English (B2)

| Strength | Evidence |
|----------|----------|
| **Multi-Cloud Production** | Same 6-service stack deployed on **GCP (GKE)** and **AWS (EKS)** via Terraform IaC |
| **Testing & Security** | **85-99% test coverage** (323 tests, [Codecov verified](https://app.codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)), security scanning (Trivy/Bandit/Gitleaks/pip-audit) |
| **Full MLOps Lifecycle** | Data versioning (DVC) → Training → MLflow tracking (9 experiments) → API serving → Monitoring → CI/CD |
| **Observability** | OpenTelemetry tracing, Prometheus + Grafana dashboards, SHAP explainability, drift detection |
| **Responsible AI** | Fairness audits (all 3 projects), automated drift detection (KS + PSI + Evidently), Pandera data validation |

---

## 🚀 Flagship Project

### [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio) — Production-Grade Multi-Cloud MLOps Platform

<div align="center">

[![CI Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml/badge.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml)
[![codecov](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio/branch/main/graph/badge.svg)](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)
[![Python](https://img.shields.io/badge/Python-3.11%20%7C%203.12-blue.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Kubernetes](https://img.shields.io/badge/K8s-GKE%20%2B%20EKS-326CE5?logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-Multi--Cloud-7B42BC?logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)
[![Docs](https://img.shields.io/badge/Docs-GitHub_Pages-blue?logo=github)](https://duqueom.github.io/ML-MLOps-Portfolio/)

</div>

**3 end-to-end ML projects** deployed on **GCP (GKE) + AWS (EKS)** — 6 Kubernetes services per cloud, Terraform IaC, CI/CD pipelines, MLflow experiment tracking, Prometheus/Grafana monitoring, and **85-99% test coverage** (323 tests).

| Project | Type | Key Metric | Tech Highlights |
|---------|------|------------|-----------------|
| 🏦 **[BankChurn Predictor](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/BankChurn-Predictor)** | Binary Classification | **AUC 0.87**, F1 0.62 | StackingClassifier (5 models), SHAP, fairness audits, 90% coverage (198 tests) |
| 🚗 **[CarVision Intelligence](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/CarVision-Market-Intelligence)** | Regression | **R² 0.80**, RMSE $6,744 | LightGBM + FeatureEngineer, fairness audits, Streamlit, 96% coverage (52 tests) |
| 📝 **[NLPInsight Analyzer](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/NLPInsight-Analyzer)** | NLP Sentiment (3-class) | **Acc 97%**, F1-w 0.97 | FinBERT (ProsusAI), fairness audits, TF-IDF fallback, 98% coverage (73 tests) |

<div align="center">

**Infrastructure at a Glance:**

| Layer | GCP | AWS |
|-------|-----|-----|
| **Compute** | GKE (3 nodes, e2-medium) | EKS (3 nodes, t3.medium) |
| **Registry** | Artifact Registry | ECR |
| **Storage** | GCS (models + datasets) | S3 (versioned, encrypted) |
| **Database** | Cloud SQL (PostgreSQL) | RDS (PostgreSQL) |
| **IaC** | Terraform (10+ resources) | Terraform (25+ resources) |
| **CI/CD** | GitHub Actions → GKE | GitHub Actions → EKS |
| **Monitoring** | Prometheus + Grafana | Prometheus + Grafana |

</div>

<div align="center">

**Production Evidence:**

| GKE Workloads | Grafana Monitoring | MLflow Experiments |
|:---:|:---:|:---:|
| ![GKE](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/gcp-console/05-gke-workloads-running.png) | ![Grafana](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/monitoring/34-grafana-dashboard.png) | ![MLflow](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/monitoring/39-mlflow-experiments.png) |
| *6 pods running on GKE* | *Real-time dashboard* | *9 tracked experiments* |

| FastAPI APIs | Streamlit Dashboard | SHAP Explainability |
|:---:|:---:|:---:|
| ![APIs](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/apis/31-tres-apis-pestanas.png) | ![Streamlit](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/apis/81-streamlit-full-dashboard.png) | ![SHAP](https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/screenshots/apis/82-shap-prediction-response.png) |
| *3 APIs on Kubernetes* | *Interactive analytics* | *Feature importance* |

  <a href="https://youtu.be/qmw9VlgUcn8">
    <img src="https://img.shields.io/badge/▶_Watch_Full_Demo-YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="YouTube Demo">
  </a>

</div>

---

## 🛠️ Tech Stack

<div align="center">

**MLOps & Infrastructure**

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/docker-compose.demo.yml)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/.github/workflows/ci-mlops.yml)
[![MLflow](https://img.shields.io/badge/MLflow-0194E2?style=flat-square&logo=mlflow&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![DVC](https://img.shields.io/badge/DVC-945DD6?style=flat-square&logo=dvc&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)

**Cloud**

[![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat-square&logo=google-cloud&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform/gcp)
[![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform/aws)
[![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)

**ML & Data**

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-FF6600?style=flat-square)](https://xgboost.readthedocs.io)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)](https://pandas.pydata.org)

**Testing & Security**

[![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Codecov](https://img.shields.io/badge/Codecov-F01F7A?style=flat-square&logo=codecov&logoColor=white)](https://app.codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)
[![Trivy](https://img.shields.io/badge/Trivy-1904DA?style=flat-square&logo=aqua&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio)
[![Bandit](https://img.shields.io/badge/Bandit-Security-green?style=flat-square)](https://github.com/DuqueOM/ML-MLOps-Portfolio)

</div>

---

## 📊 GitHub Stats

<div align="center">

<a href="https://github.com/DuqueOM">
  <img src="https://github-readme-stats-zeta-seven-14.vercel.app/api?username=DuqueOM&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&rank_icon=github" width="48%" alt="GitHub Stats">
</a>

<br>

<a href="https://github.com/DuqueOM">
  <img src="https://streak-stats.demolab.com/?user=DuqueOM&theme=tokyonight&hide_border=true" width="48%" alt="GitHub Streak">
</a>

<br>

<a href="https://github.com/DuqueOM">
  <img src="https://github-readme-stats-zeta-seven-14.vercel.app/api/top-langs/?username=DuqueOM&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" width="48%" alt="Top Languages">
</a>

</div>

---

## 🔧 Development Process & AI Transparency

These projects were developed using **AI-assisted tools** (Cursor / Windsurf Cascade) for code generation, boilerplate acceleration, and documentation drafting. All architectural decisions, modeling choices, feature engineering, evaluation methodology, deployment strategy, and business analysis were performed by the author.

AI tools were used as **accelerators, not replacements** for understanding — the same way senior engineers use code completion and documentation generators to increase throughput while retaining full ownership of design decisions.

---

## 📫 Let's Connect

<div align="center">

[![Email](https://img.shields.io/badge/Email-DuqueOrtegaMutis@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-DuqueOM-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=flat-square&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![YouTube](https://img.shields.io/badge/YouTube-Demo_Video-FF0000?style=flat-square&logo=youtube&logoColor=white)](https://youtu.be/qmw9VlgUcn8)

📍 Mexico City, Mexico

</div>

---

<div align="center">

*"I don't just train models — I build the infrastructure that makes them valuable."*

</div>
