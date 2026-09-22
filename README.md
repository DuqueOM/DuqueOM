<div align="center">

# Duque Ortega Mutis - MLOps & Production ML

**I build ML systems that survive production — three deployed services (GKE + EKS), measured incidents with documented root causes, and two open-source templates: one for a single governed ML service, one for the enterprise platform above that boundary. 14 years of operations leadership behind the engineering.**

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

## Template I — [ml-service-template](https://github.com/DuqueOM/ml-service-template): one governed service

</div>

A reusable foundation for teams that want safer defaults when moving machine
learning services toward production.

I created it after building my portfolio and seeing the same failure patterns
repeat: blocked APIs, fragile deployments, missing monitoring, unclear model
promotion rules, weak secrets handling, and documentation that does not match
how the system actually behaves.

**Its scope is one tabular ML service, and that limit is an ADR rather than an
omission** — small-team calibration throughout ("2–3 models → CronJob, not
Airflow"; "in-memory DataFrames → Pandera, not Great Expectations"). Widening
it would destroy the property that makes it recommendable: it is small enough
to read in an afternoon. The work above that boundary got its own repository
instead — [Template II](#template-ii--ml-platform-the-substrate-many-projects-share).

The template packages those lessons into a reusable starting point:

| Layer | What's encoded |
|-------|----------------|
| **38 anti-patterns (D-01→D-38)** | Runtime · Training · Infrastructure · EDA · Security · Closed-loop monitoring · Documentation coherence · Edge protection |
| **SLSA L2 supply chain** | Gitleaks → Trivy → Syft SBOM → Cosign keyless (OIDC) → Kyverno admission, every CI Action pinned by SHA |
| **Closed-loop monitoring** | Ground truth ingestion · Sliced performance · Champion/Challenger (McNemar + bootstrap ΔAUC) |
| **Native-cloud edge protection** | Cloud Armor (GCP) / AWS WAF+Shield by default, Cloudflare opt-in for multi-cloud — never a third-party account forced onto the common single-cloud case |
| **Governed AI-assisted development** | 27 skills, 19 rules, 20 workflows · agent behavior protocol (AUTO/CONSULT/STOP) · audit trail · eval gates — AI coding made reviewable, not hidden |
| **Audit-grade quality guardian** | 8 more anti-patterns (Q-01→Q-08) for standards that erode silently — unpinned actions, license drift, evidence-free releases — owned by a recurring 23-domain enterprise audit, not a one-off report |
| **Quad-IDE native** | Devin · Cursor · Claude Code · Codex — same invariants, native config for each |
| **52 ADRs** | Each decision documented with alternatives rejected and revisit triggers |

```bash
# Zero to working fraud detection service in one command
git clone https://github.com/DuqueOM/ml-service-template.git
cd ml-service-template && make bootstrap

```

→ [Template repo](https://github.com/DuqueOM/ml-service-template) &nbsp;|&nbsp; [QUICK_START.md](https://github.com/DuqueOM/ml-service-template/blob/main/QUICK_START.md) &nbsp;|&nbsp; [52 ADRs](https://github.com/DuqueOM/ml-service-template/tree/main/docs/decisions)

---

<div align="center">

## Template II — [ml-platform](https://github.com/DuqueOM/ml-platform): the substrate many projects share

</div>

The second template, and the enterprise one. Where Template I answers *"I need
one governed ML service in production"*, `ml-platform` answers *"I need a
substrate several unlike ML projects sit on"* — tabular, time series, deep
learning, LLM/RAG and agents, on GCP and AWS.

It exists **because Template I's scope limits were correct.** A single-service
scaffold cannot hold point-in-time feature retrieval, lakehouse table formats
with schema evolution, orchestration with lineage, GitOps reconciliation or LLM
evaluation gates. So that work got its own repository — and `ml-platform`
*consumes* Template I through `copier` rather than replacing it. Where the two
disagree about serving, containers, probes or supply chain, **Template I wins**.

| Layer | What's encoded |
|-------|----------------|
| **Four project kinds** | Tabular · time series · deep learning · LLM/RAG · agents — diversity is the point: a substrate serving one shape hasn't been shown to be a substrate |
| **Lakehouse + real data engineering** | Apache Iceberg (partitioning + time travel, verified against MinIO) · BigLake / S3 Tables · DuckDB + Polars · dbt · Spark scoped to backfill by a *measured* crossover threshold |
| **Point-in-time correct features** | `as_of_join` + a leakage detector that runs on the joined frame — with a `naive_join` kept deliberately so the detector can be shown to catch something real |
| **Orchestration with lineage** | Airflow 3 + KFP v2 → Vertex AI Pipelines / SageMaker Pipelines — precisely the tier Template I refuses on calibration grounds |
| **GitOps** | ArgoCD + ApplicationSets + Argo Rollouts, instead of governed `kubectl apply` |
| **Observability** | OpenTelemetry → Grafana LGTM (Loki · Tempo · Mimir), Jaeger locally |
| **LLMOps as a first-class plane** | LiteLLM · prompt registry · semantic cache · guardrails · Langfuse · promptfoo eval gates — all out of scope for Template I by decision |
| **Drift per project kind (ADR-007)** | Four detectors on one contract: PSI (tabular) · embedding-space (documents) · recall on a frozen eval set (retrieval) · tool-use & escalation rates (agents) — plus provider-fingerprint drift, where evals degrade with zero code, data or deploy change |
| **Technology triage (ADR-004)** | Every tool tiered publicly: core · demonstrated · studied · **rejected**, each with its reason. A reader never guesses whether something is operated or merely present |
| **Status derived from the filesystem** | **48 done · 2 partial · 5 absent** of 55 components. ⬜ means *absent*, not "planned" — because a status table a human maintains will drift |
| **Evidence layers, L4 printed at zero** | 37 at L1 (suite passes) · 11 at L2 (it executes) · 4 with L3 evidence not run in CI · **0 at L4** — no cloud rollout claimed, because none has happened |
| **A falsifiable claim** | *C1: a second project reuses ≥3 shared libraries with no fork, verified by a dependency-graph test in CI.* If C1 fails, the platform claim is false |

```bash
git clone https://github.com/DuqueOM/ml-platform.git
cd ml-platform && uv sync && make verify
```

→ [Platform repo](https://github.com/DuqueOM/ml-platform) &nbsp;|&nbsp; [Charter — what it refuses to be](https://github.com/DuqueOM/ml-platform/blob/main/docs/decisions/ADR-000-charter-and-scope.md) &nbsp;|&nbsp; [Implementation status](https://github.com/DuqueOM/ml-platform/blob/main/docs/architecture/implementation-status.md) &nbsp;|&nbsp; [Full write-up](https://duqueom.github.io/ML-MLOps-Portfolio/ml-platform/)

> **If you have one model to ship, Template I is the right answer and Template II
> is over-engineering.** Template II earns its complexity only once several
> projects of different kinds need to share substrate. Two templates exist
> because one of them said no — and the boundary is written down as a decision,
> not left to taste.

---

<div align="center">

## The Agent Core — [agent-local](https://github.com/DuqueOM/agent-local): the same governance, a new domain

</div>

The governance philosophy generalized to local, multi-tier LLM agents — a
business-agnostic platform (`core/` + thin `usecases/` domains) that proves
the model travels beyond tabular ML serving.

**It is also the LLM plane inside `ml-platform`**, vendored in with full git
history (ADR-002): `core/` → `libs/llm-core/`, `usecases/tienda/` →
`projects/store-assistant/`. The standalone repo stays live because the two
aren't the same value — the platform gives this core one particular, governed
use; `agent-local` remains the agnostic upstream for anyone who wants the
agent core without a platform around it.

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

**ML & data** `Python` `scikit-learn` `XGBoost` `LightGBM` `PySpark` `Polars`
`DuckDB` `dbt` `Apache Iceberg` `Pandera` `Great Expectations` `SHAP`

**Serving & infra** `FastAPI` `Docker` `Kubernetes` `Terraform` `ArgoCD`
`Argo Rollouts` `Kyverno` `GKE` `EKS` `GCP` `AWS`

**Lifecycle & orchestration** `MLflow` `DVC` `Airflow 3` `Kubeflow Pipelines`
`Vertex AI Pipelines` `SageMaker Pipelines` `GitHub Actions` `Copier`

**Observability** `Prometheus` `Grafana` `OpenTelemetry` `Loki` `Tempo`
`Mimir` `Jaeger` `Evidently`

**GenAI & agentic** `LiteLLM` `llama.cpp` `pgvector` `RAG` `Langfuse`
`promptfoo` `LoRA / PEFT` `AUTO · CONSULT · STOP governance`

**TripleTen Data Science**<br>
**14 years operations -> MLOps & Production ML**

---

## AI Transparency

I use AI-assisted coding tools — and I engineer that workflow instead of hiding
it. Both templates encode the governance layer: behavior protocols
(AUTO/CONSULT/STOP), path-scoped rules, an append-only audit trail and eval
gates that keep AI-generated changes reviewable and bounded. `ml-platform` adds
the rule that matters most to me — *a document asserting something false is
itself a defect, even when the code is correct* — enforced by gates that derive
status from the filesystem instead of trusting prose. Architecture, trade-off
analysis, incident diagnosis, and final technical decisions are my
responsibility; the tooling accelerates the rest.

I consider this a core engineering skill for 2026, not a disclaimer.

---

<div align="center">

**Open to MLOps, Production ML, Applied AI, and ML Platform roles — evaluated on evidence, not tenure.**<br>
Remote preferred - Mexico City (CST)

</div>
