<div align="center">

# Duque Ortega Mutis

### MLOps & Production ML · Mexico City

**I build ML systems that survive production.**<br>
Three services deployed on GKE and EKS, three incidents measured and root-caused,
and two open-source templates built from what they taught — one for classical ML,
one for deep learning, LLM and agents.<br>
Fourteen years of operations leadership before the first model.

[![Portfolio](https://img.shields.io/badge/Full_Portfolio-Live_Site-22D3EE?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![Recruiter Brief](https://img.shields.io/badge/Recruiter-2_min_brief-34D399?style=for-the-badge&logo=readme&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/recruiter-brief/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![YouTube](https://img.shields.io/badge/Demo-3_min-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

---

<div align="center">

## Three production incidents, diagnosed from first principles

</div>

```
 81% error rate under load  →  uvicorn --workers is an anti-pattern under K8s
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

<div align="center">

Each one is written up with the measurement that found it and the alternatives rejected.<br>
**[Read the incident write-ups →](https://duqueom.github.io/ML-MLOps-Portfolio/technical-evidence/)**

</div>

---

<div align="center">

## The evidence — [ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)

*Three end-to-end ML services: trained, served, containerised, deployed, monitored.*

<img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Portfolio demo" width="580">

</div>

| Project | What it demonstrates | Result |
|---------|----------------------|--------|
| **[BankChurn Predictor](https://duqueom.github.io/ML-MLOps-Portfolio/projects/bankchurn/)** | Classification API, SHAP explanations, threshold tuning | AUC 0.87 · 90% coverage |
| **[NLPInsight Analyzer](https://duqueom.github.io/ML-MLOps-Portfolio/projects/nlpinsight/)** | Financial sentiment API, honest dataset selection, CPU-friendly serving | 80.6% accuracy · 98% coverage |
| **[ChicagoTaxi Pipeline](https://duqueom.github.io/ML-MLOps-Portfolio/projects/chicagotaxi/)** | PySpark ETL, demand forecasting, data-leakage correction | R² 0.96 · 6.3M rows |

<div align="center">

GKE + EKS · 395+ tests · 18 ADRs · load tests, drift detection and runbooks

**[Project deep-dives →](https://duqueom.github.io/ML-MLOps-Portfolio/projects/)** &nbsp;·&nbsp;
**[Deployment evidence →](https://duqueom.github.io/ML-MLOps-Portfolio/DEPLOYMENT_EVIDENCE/)** &nbsp;·&nbsp;
**[18 ADRs →](https://duqueom.github.io/ML-MLOps-Portfolio/architecture/decisions/)**

</div>

---

<div align="center">

## Two templates, and the boundary between them

*The portfolio taught the lessons. These encode them — and the interesting part is that there are two.*

</div>

**[`ml-service-template`](https://github.com/DuqueOM/ml-service-template)** governs **classical ML** — scikit-learn,
XGBoost, LightGBM, single team, 1–5 models — and then refuses to grow. That limit is an ADR, not an omission: LLM/GenAI,
feature stores and data contracts are each deferred there *with a revisit trigger*, because widening it would destroy
the property that makes it recommendable — it is small enough to read in an afternoon.

**[`ml-platform`](https://github.com/DuqueOM/ml-platform)** is what those deferrals made necessary: the enterprise
substrate for the problem shapes the first one declines — deep learning, LLM/RAG and agents, alongside tabular. It
**consumes** the first through `copier` rather than replacing it.

| | `ml-service-template` | `ml-platform` |
|---|---|---|
| **Answers** | "I need governed classical ML in production" | "I need a substrate spanning tabular, DL, LLM and agents" |
| **Model kinds** | scikit-learn · XGBoost · LightGBM — a stated limit, 1–5 models | + time series, deep learning, LLM/RAG, agents |
| **Data** | In-memory DataFrames, Pandera | Iceberg lakehouse, point-in-time joins with leakage detection, dbt |
| **Ship it** | CronJob + GitHub Actions, governed `kubectl apply` | Airflow 3 + KFP → Vertex AI / SageMaker, ArgoCD GitOps |
| **Governance** | 38 anti-patterns (D-01→D-38) + 8 audit-standard · 52 ADRs | Tooling triage: core / demonstrated / studied / **rejected** · 10 ADRs |
| **Honesty gate** | Self-auditing docs-coherence CI gate | Status derived from the filesystem · **L4 printed at zero** |
| **Read it in** | An afternoon | Not in an afternoon, and that is the trade |

> **If your models are classical ML, the first is the right answer and the second is over-engineering.**
> Knowing which problems a tool should *not* absorb is the judgment this pair is evidence for.

<div align="center">

**[Template · classical ML →](https://duqueom.github.io/ML-MLOps-Portfolio/template/)** &nbsp;·&nbsp;
**[Platform · DL, LLM & agents →](https://duqueom.github.io/ML-MLOps-Portfolio/ml-platform/)** &nbsp;·&nbsp;
**[Side by side →](https://duqueom.github.io/ML-MLOps-Portfolio/related-projects/#the-two-templates-side-by-side)**

<sub>The platform's LLM plane comes from <a href="https://github.com/DuqueOM/agent-local"><code>agent-local</code></a> —
a business-agnostic agent core with a deterministic policy gate, vendored in with its full history and still standalone.
<a href="https://duqueom.github.io/ML-MLOps-Portfolio/agent-local/">Write-up →</a></sub>

</div>

---

<div align="center">

## Stack

</div>

```
ML & data      Python · scikit-learn · XGBoost · LightGBM · PySpark · Polars · DuckDB · Iceberg · dbt · SHAP
Serving        FastAPI · Docker · Kubernetes (GKE + EKS) · Terraform · ArgoCD · Argo Rollouts · Kyverno
Lifecycle      MLflow · DVC · Airflow 3 · Kubeflow / Vertex AI / SageMaker Pipelines · GitHub Actions · Copier
Observability  Prometheus · Grafana · OpenTelemetry · Loki · Tempo · Mimir · Evidently
GenAI          LiteLLM · pgvector · RAG · Langfuse · promptfoo · LoRA / PEFT · AUTO·CONSULT·STOP governance
```

---

<div align="center">

## Who I am

</div>

I spent 14 years running business operations — teams, vendors, budgets and customer-facing processes — before moving
into ML engineering. That background is why my work looks the way it does: a model is useful only once it can be
deployed, monitored, explained, improved and operated with cost discipline. I document root causes instead of only
showing final demos, and I connect engineering decisions to cost, risk and maintainability.

Seeking my first formal ML/MLOps role — experienced in ownership, pressure, and making systems easier for the next
person to operate.

**On AI-assisted development:** I use it, and I engineer the workflow instead of hiding it. Both templates encode the
governance layer — behavior protocols, path-scoped rules, an append-only audit trail, eval gates. `ml-platform` adds
the rule I care most about: *a document asserting something false is itself a defect, even when the code is correct*,
enforced by gates that derive status from the filesystem rather than trusting prose. Architecture, trade-off analysis
and incident diagnosis are mine; the tooling accelerates the rest.

<div align="center">

**[More about me →](https://duqueom.github.io/ML-MLOps-Portfolio/about/)** &nbsp;·&nbsp;
**[Get in touch →](https://duqueom.github.io/ML-MLOps-Portfolio/contact/)**

</div>

---

<div align="center">

**Open to MLOps, Production ML, Applied AI and ML Platform roles — evaluated on evidence, not tenure.**<br>
<sub>Remote preferred · Mexico City (CST) · TripleTen Data Science · GCP ACE and AWS ML Associate in progress</sub>

</div>
