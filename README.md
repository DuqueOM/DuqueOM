<div align="center">

# Duque Ortega Mutis - MLOps & Production ML

**I build ML systems that survive production — three deployed services (GKE + EKS), measured incidents with documented root causes, and an open-source production template. 14 years of operations leadership behind the engineering.**

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

I spent 14 years running business operations — teams, vendors, budgets and
customer-facing processes — before moving into ML engineering. That background
is why my portfolio looks the way it does: a model is useful only when it can
be deployed, monitored, explained, improved, and operated with cost discipline.

I build working ML systems, document trade-offs, measure failures, and turn
those lessons into reusable patterns. Seeking my first formal ML/MLOps role;
experienced in ownership, pressure and making systems easier for the next
person to operate.

**Target roles**: ML Engineer · MLOps / Production ML · Platform Engineer (ML infra) ·
ML Platform / Data Engineering with ML workflows — evaluated on evidence, not tenure.

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
| **38 anti-patterns (D-01→D-38)** | Runtime · Training · Infrastructure · EDA · Security · Closed-loop monitoring · Documentation coherence · Edge protection |
| **SLSA L2 supply chain** | Gitleaks → Trivy → Syft SBOM → Cosign keyless (OIDC) → Kyverno admission, every CI Action pinned by SHA |
| **Closed-loop monitoring** | Ground truth ingestion · Sliced performance · Champion/Challenger (McNemar + bootstrap ΔAUC) |
| **Native-cloud edge protection** | Cloud Armor (GCP) / AWS WAF+Shield by default, Cloudflare opt-in for multi-cloud — never a third-party account forced onto the common single-cloud case |
| **Governed AI-assisted development** | 26 skills, 18 rules, 18 workflows · agent behavior protocol (AUTO/CONSULT/STOP) · audit trail · eval gates — AI coding made reviewable, not hidden |
| **Quad-IDE native** | Devin · Cursor · Claude Code · Codex — same invariants, native config for each |
| **42 ADRs** | Each decision documented with alternatives rejected and revisit triggers |

```bash
# Zero to working fraud detection service in one command
git clone https://github.com/DuqueOM/ML-MLOps-Production-Template.git
cd ML-MLOps-Production-Template && make bootstrap

```

→ [Template repo](https://github.com/DuqueOM/ML-MLOps-Production-Template) &nbsp;|&nbsp; [QUICK_START.md](https://github.com/DuqueOM/ML-MLOps-Production-Template/blob/main/QUICK_START.md) &nbsp;|&nbsp; [42 ADRs](https://github.com/DuqueOM/ML-MLOps-Production-Template/tree/main/docs/decisions)

---

<div align="center">

## Sibling Project — [agent-local](https://github.com/DuqueOM/agent-local): the same governance, a new domain

</div>

The template's philosophy generalized to local, multi-tier LLM agents — not a
fork, a reusable platform (`core/` + thin `usecases/` domains) that proves the
governance model travels beyond tabular ML serving.

| Layer | What's encoded |
|-------|----------------|
| **Deterministic policy gate** | Versioned YAML policy checked before a response ships — never model self-judgment |
| **Reflection isolated from evidence** | A model's self-reflection is structurally unreachable by the policy gate or verifier (ADR-009) |
| **Eval-gated autonomy** | 11 adversarial sets + an offline gate prove a "successfully fooled" model still can't bypass the policy layer |
| **Interop discipline** | MCP/A2A evaluated and rejected on a precise technical conflict, with the evidence that would reverse it on record (ADR-010) |
| **OWASP LLM Top-10 (2025)** | Every category mapped to a concrete control, not a generic security paragraph |

→ [agent-local repo](https://github.com/DuqueOM/agent-local) &nbsp;|&nbsp; [Full write-up](https://duqueom.github.io/ML-MLOps-Portfolio/agent-local/)

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

That story matters because it shows the habit I want to bring to an ML/MLOps role:
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

I use AI-assisted coding tools — and I engineer that workflow instead of hiding
it. My production template encodes the governance layer: behavior protocols
(AUTO/CONSULT/STOP), path-scoped rules, an append-only audit trail and eval
gates that keep AI-generated changes reviewable and bounded. Architecture,
trade-off analysis, incident diagnosis, and final technical decisions are my
responsibility; the tooling accelerates the rest.

I consider this a core engineering skill for 2026, not a disclaimer.

---

<div align="center">

**Open to MLOps, Production ML, Applied AI, and ML Platform roles — evaluated on evidence, not tenure.**<br>
Remote preferred - Mexico City (CST)

</div>
