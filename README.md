<div align="center">

# Junior AI Engineer · LLM apps and agents · ML in production · Mexico City

## Duque Ortega Mutis

I design and build AI and ML systems end to end: data, model, API, container and cloud.
Before tech, I ran my own businesses and operations for 14 years, so I build for real users and measurable results.
I work with AI coding agents (Claude Code) for speed. The design, the decisions and the review are mine.

[![Portfolio](https://img.shields.io/badge/Portfolio-Live_Site-22D3EE?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![YouTube](https://img.shields.io/badge/Demo-3_min-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![Email](https://img.shields.io/badge/Email-Contact-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

## Featured projects

**[agent-whatsapp-php](https://github.com/DuqueOM/agent-whatsapp-php)** · WhatsApp customer-service agent (in progress)<br>
PHP 8.3, MySQL, Meta Cloud API webhooks, LLM tool calling, human handoff and evals.
I wrote the spec and the plan, and I write the core logic. AI agents generate the scaffolding, which I review personally.
First release planned for January 2027.

**[ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)** · three ML services, deployed to GKE and EKS<br>
Churn prediction, financial sentiment and taxi-demand forecasting, served with FastAPI, Docker and Kubernetes,
with Terraform, CI/CD, MLflow and monitoring. Deployed to GKE and EKS in March 2026, then shut down to save costs.
I designed the architecture and made the decisions (18 ADRs); AI coding agents helped me build it faster.


<p align="center"><img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Portfolio demo: the three ML services, their dashboards and predictions" width="580"></p>

Three problems I found and fixed under load tests on my own GKE and EKS clusters:

```
81% error rate under load  →  uvicorn --workers under Kubernetes. Fixed with asyncio + a thread pool: 81% → 0%
SHAP returning all zeros   →  TreeExplainer does not work with StackingClassifier. Fixed with KernelExplainer
HPA never scales down      →  memory-based HPA with a fixed ML memory footprint. Fixed with CPU-only HPA: 3 → 1 pods
```

[Read how I found and fixed them →](https://duqueom.github.io/ML-MLOps-Portfolio/technical-evidence/)

**[read_aloud](https://github.com/DuqueOM/read_aloud)** · a text-to-speech app I use every day<br>
Reads selected text aloud on Windows with local neural voices, in Spanish and English in the same text, offline.
I fine-tuned a Qwen3-TTS voice with LoRA on my own GPU (RTX 5070, 8 GB), chose the training setup and the final
epoch, and used WavLM to compare voices. 15 ADRs record the decisions. Built with AI coding agents.

<p align="center"><img src="https://raw.githubusercontent.com/DuqueOM/read_aloud/main/docs/media/demo.gif" alt="read_aloud demo: selected text is read aloud and each sentence is highlighted" width="580"></p>

## How I work

- I start from the problem: I write the spec, the limits and the decisions (ADRs).
- I build with AI coding agents inside rules I set: tests first, small reviewed changes, CI gates.
- I measure: load tests, evals, and incident reports with numbers.

## Next step

MS in Artificial Intelligence at the University of Colorado Boulder (online, Coursera), planned for 2027.

## Architecture studies

Larger systems I designed and directed. AI coding agents wrote most of the code. Not deployed to a cloud.<br>
[ml-service-template](https://github.com/DuqueOM/ml-service-template) (classical ML on Kubernetes) ·
[ml-platform](https://github.com/DuqueOM/ml-platform) (tabular, deep learning, LLM and agents) ·
[agent-local](https://github.com/DuqueOM/agent-local) (local LLM agent core)

---

Open to junior AI Engineer, ML Engineer and MLOps roles · Remote or Mexico City · Spanish (native), English (B1) · TripleTen Data Science
