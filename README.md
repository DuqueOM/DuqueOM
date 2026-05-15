<div align="center">

# Duque Ortega Mutis - MLOps & Production ML

**Entry-level MLOps / Production ML candidate with 14 years of operations experience now applied to reliable machine learning systems.**

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-blue?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/YouTube-3min_Demo-FF0000?style=for-the-badge&logo=youtube)](https://youtu.be/7dFFqq2ROPw)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

---

## Three production incidents — diagnosed from first principles, not guesswork

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

## [About Me](https://duqueom.github.io/ML-MLOps-Portfolio/about/)

I am building my first formal career step in ML/MLOps after 14 years running
business operations, teams, vendors, budgets, and customer-facing processes.
That background shaped how I approach machine learning: a model is useful only
when it can be deployed, monitored, explained, improved, and operated with cost
discipline.

I am looking for entry-level or junior roles such as:

- Junior MLOps / Production ML
- Junior Machine Learning Engineer
- AI Engineer I / Applied AI
- Junior ML Platform or Data Engineering roles with ML workflows

My portfolio is designed to show how I think and learn: I build working ML
systems, document trade-offs, measure failures, and turn those lessons into
reusable patterns.

---

## [What I Bring](https://duqueom.github.io/ML-MLOps-Portfolio/recruiter-brief/)


| Strength | How it shows up |
|---------|------------------|
| **Operations mindset** | I care about reliability, cost, handoffs, and real user impact. |
| **Production ML fundamentals** | FastAPI, Docker, Kubernetes, MLflow, CI/CD, monitoring, drift detection, and model versioning. |
| **Debugging discipline** | I document root causes instead of only showing final demos. |
| **Business judgment** | I connect engineering decisions to cost, risk, and maintainability. |
| **Learning velocity** | I use open-source projects to turn new tools into working systems. |

---
<div align="center">

## Flagship Open-Source — [ML-MLOps-Production-Template](https://github.com/DuqueOM/ML-MLOps-Production-Template)  

</div>

Is a reusable foundation for teams that want safer defaults when moving machine
learning services toward production.

I created it after building my portfolio and seeing the same failure patterns
repeat: blocked APIs, fragile deployments, missing monitoring, unclear model
promotion rules, weak secrets handling, and documentation that does not match
how the system actually behaves.

The template packages those lessons into a reusable starting point:

| Layer | What's encoded |
|-------|----------------|
| **32 anti-patterns (D-01→D-32)** | Runtime · Training · Infrastructure · EDA · Security · Closed-loop monitoring |
| **SLSA L2 supply chain** | Gitleaks → Trivy → Syft SBOM → Cosign keyless (OIDC) → Kyverno admission |
| **Closed-loop monitoring** | Ground truth ingestion · Sliced performance · Champion/Challenger (McNemar + bootstrap ΔAUC) |
| **Quad-IDE native** | Windsurf · Claude Code · Cursor · Codex — same invariants, native config for each |
| **26 ADRs** | Each decision documented with alternatives rejected and revisit triggers |

```bash
# Zero to working fraud detection service in one command
git clone https://github.com/DuqueOM/ML-MLOps-Production-Template.git
cd ML-MLOps-Production-Template && make bootstrap

```

→ [Template repo](https://github.com/DuqueOM/ML-MLOps-Production-Template) &nbsp;|&nbsp; [QUICK_START.md](https://github.com/DuqueOM/ML-MLOps-Production-Template/blob/main/QUICK_START.md) &nbsp;|&nbsp; [26 ADRs](https://github.com/DuqueOM/ML-MLOps-Production-Template/tree/main/docs/decisions)

---

<div align="center">

## Production Portfolio —[ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)

</div>

Shows three end-to-end ML projects built beyond notebooks: model training,
APIs, containers, deployment artifacts, monitoring, tests, and documented
engineering decisions.

<div align="center">
<img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Portfolio Demo" width="600">
</div>

| Project | What it demonstrates | Main result |
|---------|----------------------|-------------|
| [BankChurn Predictor](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/BankChurn-Predictor) | Classification API, SHAP explanations, threshold tuning, model serving. | AUC 0.87, 90% coverage. |
| [NLPInsight Analyzer](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/NLPInsight-Analyzer) | Financial sentiment API, honest dataset selection, CPU-friendly serving. | 80.6% accuracy, 98% coverage. |
| [ChicagoTaxi Pipeline](https://github.com/DuqueOM/ML-MLOps-Portfolio/tree/main/ChicagoTaxi-Demand-Pipeline) | PySpark ETL, demand forecasting, data leakage correction. | R2 0.96, 6.3M rows processed. |

One example from the portfolio: a load test exposed an 81% error rate in an ML
API. I traced the issue to a serving pattern that created CPU contention under
Kubernetes, then redesigned the inference path with asynchronous execution and
a thread pool. The result dropped the error rate to 0% and reduced CPU needs.

That story matters because it shows the habit I want to bring to a junior role:
measure the problem, understand the cause, fix it, and document the lesson.

📐 [18 ADRs →](https://duqueom.github.io/ML-MLOps-Portfolio/architecture/decisions/) &nbsp;|&nbsp; 📋 [Engineering Highlights →](https://github.com/DuqueOM/ML-MLOps-Portfolio/blob/main/ENGINEERING_HIGHLIGHTS.md) &nbsp;|&nbsp; 📺 [3min Demo →](https://youtu.be/7dFFqq2ROPw)

---

## Core Stack

`Python` `scikit-learn` `XGBoost` `LightGBM` `PySpark` `FastAPI` `Docker`
`Kubernetes` `Terraform` `GitHub Actions` `MLflow` `DVC` `Prometheus`
`Grafana` `SHAP` `AWS` `GCP`

**TripleTen Data Science**<br>
**14 years operations -> MLOps & Production ML**

---

## AI Transparency

I use AI-assisted coding tools to move faster on boilerplate, tests, and
documentation structure. Architecture, trade-off analysis, incident diagnosis,
and final technical decisions are my responsibility.

My goal is not to present myself as a senior engineer. My goal is to show that I
can learn quickly, work carefully, communicate clearly, and contribute to teams
building reliable ML systems.

---

<div align="center">

**Open to entry-level and junior opportunities in MLOps, Production ML, Applied AI, and ML Platform.**<br>
Remote preferred - Mexico City (CST)

</div>
