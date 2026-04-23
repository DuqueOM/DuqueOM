<div align="center">

# Duque Ortega Mutis — MLOps Engineer (Production-Focused)

**I don't just deploy ML models. I diagnose why they break at 2am — and build the systems that prevent it.**

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-3min_Demo-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

---

## Flagship Open-Source — [ML-MLOps-Production-Template](https://github.com/DuqueOM/ML-MLOps-Production-Template)

> *The patterns my portfolio cost $200/mo and 18 ADRs to learn — packaged so other teams don't have to.*

[![Release](https://img.shields.io/github/v/release/DuqueOM/ML-MLOps-Production-Template.svg)](https://github.com/DuqueOM/ML-MLOps-Production-Template/releases)
[![Anti-Patterns](https://img.shields.io/badge/anti--patterns-22%20encoded-red.svg)](https://github.com/DuqueOM/ML-MLOps-Production-Template#anti-pattern-detection)
[![Agentic](https://img.shields.io/badge/agentic-Windsurf_%7C_Claude_Code_%7C_Cursor-blueviolet.svg)](https://github.com/DuqueOM/ML-MLOps-Production-Template#agentic-system)

An **enterprise agentic MLOps framework** — not a scaffold generator, but a system that encodes what goes wrong in production as executable constraints for AI coding assistants.

**What makes it different from every other MLOps template:**

```
Most templates give you files.
This one gives you a behavioral protocol.

AUTO / CONSULT / STOP — 21 operations mapped to agent modes.
STOP on production deploys cannot be bypassed by human insistence.
If env=production and audit.passed=False → DeploymentRequest refuses to construct.

The invariants aren't in the README. They're in the code.
```

| Layer | What's encoded |
|-------|---------------|
| **22 anti-patterns** (D-01→D-22) | Runtime · Training · Infrastructure · EDA · Security · Closed-loop monitoring |
| **SLSA L2 supply chain** | Gitleaks → Trivy → Syft SBOM → Cosign keyless (OIDC) → Kyverno admission |
| **Closed-loop monitoring** | Ground truth ingestion · Sliced performance · Champion/Challenger (McNemar + bootstrap ΔAUC) |
| **Tri-IDE native** | Windsurf (13r/12s/11w) · Claude Code (8r) · Cursor (8r) — same invariants, native config each |
| **9 ADRs** | Each decision documented with alternatives rejected and revisit triggers |

```bash
# Zero to working fraud detection service in one command
git clone https://github.com/DuqueOM/ML-MLOps-Production-Template.git
cd ML-MLOps-Production-Template && make bootstrap
```

→ [Template repo](https://github.com/DuqueOM/ML-MLOps-Production-Template) &nbsp;|&nbsp; [QUICK_START.md](https://github.com/DuqueOM/ML-MLOps-Production-Template/blob/main/QUICK_START.md) &nbsp;|&nbsp; [9 ADRs](https://github.com/DuqueOM/ML-MLOps-Production-Template/tree/main/docs/decisions)

---

## Production Portfolio — [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)

**The source of truth the template was extracted from: 3 live ML services, real incidents, real data.**

[![CI](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml/badge.svg)](https://github.com/DuqueOM/ML-MLOps-Portfolio/actions/workflows/ci-mlops.yml)
[![codecov](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio/branch/main/graph/badge.svg)](https://codecov.io/gh/DuqueOM/ML-MLOps-Portfolio)

<img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Portfolio Demo" width="600">

### Three production incidents — diagnosed from first principles, not guesswork:

```
Incident 1: 81% error rate under load
  Root cause: uvicorn --workers N on K8s → workers share one CPU budget
              → CPU thrashing, not parallelism
  Fix:        asyncio.run_in_executor + ThreadPoolExecutor(4)
              sklearn C extensions release the GIL — this is the key
  Result:     81% errors → 0% · 2000m CPU → 1000m
  Documented: ADR-014 + ADR-015

Incident 2: SHAP returning all zeros in production
  Root cause: TreeExplainer incompatible with StackingClassifier
              Evaluated 4 alternatives before deciding
  Fix:        KernelExplainer in original 10-feature space
              (business-interpretable, not 38 encoded columns)
  Documented: ADR-010

Incident 3: HPA never scaled down
  Root cause: Memory-based HPA + fixed ML footprint
              ceil(replicas × usage/target) ≥ current replicas — always
              Mathematically impossible to scale down
  Fix:        CPU-only HPA — CPU correlates with traffic, memory doesn't
              3 replicas → 1 in 8 minutes
  Documented: ADR-001
```

| Project | Metric | Key decision |
|---------|--------|-------------|
| [BankChurn Predictor](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/BankChurn-Predictor) | AUC **0.87** · 90% cov | Threshold 0.35, not 0.50 — 30:1 cost ratio, quantified |
| [NLPInsight Analyzer](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/NLPInsight-Analyzer) | Acc **80.6%** · 98% cov | Chose harder dataset (97%→80.6%) — honest over impressive |
| [ChicagoTaxi Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/ChicagoTaxi-Demand-Pipeline) | R² **0.96** · 6.3M rows | Found & fixed data leakage · R² 0.905→0.965 with honest features |

**Selected "Don't Build" decisions** *(often harder than building)*:
- Removed CarVision: MAPE 32.9% is not defensible — ADR-009
- Deferred Feature Store: designed full Feast architecture for when it's needed — ADR-007
- Rejected Airflow: CronJob + GitHub Actions is sufficient for 3 models — ADR-006
- Documented $24/mo GCP vs $145/mo AWS gap — both meet SLA, chose FinOps — ADR-016

📐 [18 ADRs →](https://duqueom.github.io/ML-MLOps-Portfolio/architecture/decisions/) &nbsp;|&nbsp; 📋 [Engineering Highlights →](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/ENGINEERING_HIGHLIGHTS.md) &nbsp;|&nbsp; 📺 [3min Demo →](https://youtu.be/7dFFqq2ROPw)

---

## Stack

`Kubernetes (GKE · EKS)` `Terraform` `GitHub Actions` `FastAPI` `MLflow` `Prometheus` `Grafana`
`Argo Rollouts` `Docker` `PySpark` `LightGBM` `XGBoost` `SHAP` `Evidently` `DVC` `Pandera`
`GCP` `AWS` `SageMaker` `Vertex AI` `Cosign` `Kyverno` `OpenTelemetry` `Python 3.11+`
`Windsurf Cascade` `Claude Code` `Cursor`

**AWS Certified Machine Learning Engineer – Associate** · TripleTen Data Science · 14 years ops → MLOps

---

## AI Transparency

These projects use Windsurf Cascade for code generation and boilerplate.
All architectural decisions, trade-off analysis, incident resolution, and system design are the author's.

The `.windsurf/` and `.claude/` configurations are themselves a demonstration of the philosophy:
**the agent is governed by documented decisions, not given free rein.**
That governance design is original and independently authored.

---

<div align="center">

*Open to MLOps · ML Platform · ML Infrastructure roles — Remote preferred — Mexico City (CST)*

</div>
