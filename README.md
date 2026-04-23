<div align="center">

# Duque Ortega Mutis — MLOps Engineer (Production-Focused)

**I don't just deploy ML models. I diagnose why they break at 2am.**

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-3min_Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

---

## Three production incidents — diagnosed from first principles, not guesswork

```
Selected Production Incidents (Root Cause → Fix → Impact)

81% error rate under load: Caused by uvicorn --workers N on Kubernetes, where workers share a single CPU budget, leading to CPU thrashing instead of true parallelism. Resolved using asyncio.run_in_executor with ThreadPoolExecutor(4), leveraging GIL release in sklearn C extensions. Result: 81% → 0% error rate, CPU reduced from 2000m → 1000m. (ADR-014, ADR-015)

SHAP returning all zeros in production: Root cause was incompatibility between TreeExplainer and StackingClassifier. After evaluating four alternatives, implemented KernelExplainer in the original 10-feature space (business-interpretable vs 38 encoded features). (ADR-010)

HPA never scaling down: Memory-based HPA with fixed ML footprint made scale-down mathematically impossible (ceil(replicas × usage/target) ≥ current). Switched to CPU-based HPA, aligning scaling with traffic patterns. Result: 3 → 1 replicas in 8 minutes. (ADR-001)
```

---

<div align="center">

## Production Portfolio — [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)

**3 ML services on GKE + EKS · 18 ADRs · 395+ tests · Multi-cloud Terraform**

[![CI](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml/badge.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml)
[![codecov](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio/branch/main/graph/badge.svg)](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)
[![K8s](https://img.shields.io/badge/K8s-GKE%20%2B%20EKS-326CE5?logo=kubernetes&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/k8s)
[![Terraform](https://img.shields.io/badge/Terraform-Multi--Cloud-7B42BC?logo=terraform&logoColor=white)](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/infra/terraform)

<img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Portfolio Demo" width="600">

</div>

Most ML portfolios show models that score well. This one shows what happens **after you deploy** — the incidents, the wrong decisions corrected, and 18 Architectural Decision Records documenting every trade-off with measured data.

| Project | Metric | Key Engineering Decision |
|---------|--------|--------------------------|
| [BankChurn Predictor](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/BankChurn-Predictor) | AUC **0.87** · 90% cov | Async inference via ThreadPoolExecutor · threshold 0.35 (30:1 cost ratio, quantified) |
| [NLPInsight Analyzer](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/NLPInsight-Analyzer) | Acc **80.6%** · 98% cov | Upgraded from curated dataset to 11.9K real noisy tweets — honest over impressive |
| [ChicagoTaxi Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/ChicagoTaxi-Demand-Pipeline) | R² **0.96** · 6.3M rows | Found & fixed data leakage · temporal split · R² 0.905→0.965 |

**Selected "Don't Build" decisions** *(often harder than building)*:
- Removed CarVision: MAPE 32.9% is not defensible — ADR-009
- Deferred Feature Store: full Feast architecture designed for when it's needed — ADR-007
- Rejected Airflow: CronJob + GitHub Actions is sufficient for 3 models — ADR-006
- Documented $24/mo GCP vs $145/mo AWS gap — both meet SLA, chose FinOps — ADR-016

📐 [18 ADRs →](https://duqueom.github.io/ML-MLOps-Portfolio/architecture/decisions/) &nbsp;|&nbsp; 📋 [Engineering Highlights →](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/ENGINEERING_HIGHLIGHTS.md) &nbsp;|&nbsp; 📺 [3min Demo →](https://youtu.be/7dFFqq2ROPw)

---

<div align="center">

## Flagship Open-Source — [ML-MLOps-Production-Template](https://github.com/DuqueOM/ML-MLOps-Production-Template)

> *The patterns my portfolio cost $200/mo and 18 ADRs to learn — packaged so other teams don't have to.*

[![Release](https://img.shields.io/github/v/release/DuqueOM/ML-MLOps-Production-Template.svg)](https://github.com/DuqueOM/ML-MLOps-Production-Template/releases)
[![Anti-Patterns](https://img.shields.io/badge/anti--patterns-22%20encoded-red.svg)](https://github.com/DuqueOM/ML-MLOps-Production-Template#anti-pattern-detection)
[![Agentic](https://img.shields.io/badge/agentic-Windsurf_%7C_Claude_Code_%7C_Cursor-blueviolet.svg)](https://github.com/DuqueOM/ML-MLOps-Production-Template#agentic-system)

</div>

```
Most templates provide files; this one enforces a behavioral protocol.
Defines AUTO / CONSULT / STOP across 21 operations, where production deploys require explicit approval and cannot be bypassed. If env=production and audit.passed=False, DeploymentRequest fails at construction.

The invariants aren’t in the README — they’re enforced in code.
```

| Layer | What's encoded |
|-------|----------------|
| **22 anti-patterns** (D-01→D-22) | Runtime · Training · Infrastructure · EDA · Security · Closed-loop monitoring |
| **SLSA L2 supply chain** | Gitleaks → Trivy → Syft SBOM → Cosign keyless (OIDC) → Kyverno admission |
| **Closed-loop monitoring** | Ground truth ingestion · Sliced performance · Champion/Challenger (McNemar + bootstrap ΔAUC) |
| **Tri-IDE native** | Windsurf · Claude Code · Cursor — same invariants, native config for each |
| **9 ADRs** | Each decision documented with alternatives rejected and revisit triggers |

```bash

Zero to production-ready fraud detection service in one command:
git clone https://github.com/DuqueOM/ML-MLOps-Production-Template.git && cd ML-MLOps-Production-Template && make bootstrap

```

→ [Template repo](https://github.com/DuqueOM/ML-MLOps-Production-Template) &nbsp;|&nbsp; [QUICK_START.md](https://github.com/DuqueOM/ML-MLOps-Production-Template/blob/main/QUICK_START.md) &nbsp;|&nbsp; [9 ADRs](https://github.com/DuqueOM/ML-MLOps-Production-Template/tree/main/docs/decisions)

---

## Agentic Development Configuration

The portfolio includes a production-grade agentic setup (`AGENTS.md` + `.windsurf/`) that encodes 18 ADRs and 3 production incidents into the development environment itself.

```
.windsurf/
├── rules/       7 context-aware rules (glob-triggered per file type)
├── skills/      6 operational procedures (debug, deploy-gke, deploy-aws,
│                drift-detection, model-retrain, release-checklist)
└── workflows/   6 structured prompt workflows (/incident, /retrain,
                 /release, /load-test, /new-adr, /drift-check)
```

The agent knows: never use `uvicorn --workers N` under K8s (ADR-014), always use `KernelExplainer` for SHAP with StackingClassifier (ADR-010), CPU targets are 50%/60%/60% — not 70% (ADR-001). Operational knowledge encoded, not just referenced.

→ [AGENTS.md](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/AGENTS.md) &nbsp;|&nbsp; [.windsurf/](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/.windsurf)

---

## Stack

`Kubernetes (GKE · EKS)` `Terraform` `GitHub Actions` `FastAPI` `MLflow` `Prometheus` `Grafana`
`Argo Rollouts` `Docker` `PySpark` `LightGBM` `XGBoost` `SHAP` `Evidently` `DVC` `Pandera`
`GCP` `AWS` `SageMaker` `Vertex AI` `Cosign` `Kyverno` `OpenTelemetry` `Python 3.11+`

**AWS Certified Machine Learning Engineer – Associate (MLA-C01)** · TripleTen Data Science · 14 years ops → MLOps

---

## AI Transparency

These projects use AI-assisted tools (Windsurf Cascade, Claude Code) for code generation and boilerplate.
All architectural decisions, system design, trade-off analysis, and incident resolution are the author's.
AI tools accelerate throughput — they don't replace engineering judgment.

The `.windsurf/` and `.claude/` configurations are themselves a demonstration of this philosophy:
**the agent is governed by documented decisions, not given free rein.**
That governance design is original and independently authored.

---

<div align="center">

*Open to MLOps · ML Platform · ML Infrastructure roles — Remote preferred — Mexico City (CST)*

</div>
