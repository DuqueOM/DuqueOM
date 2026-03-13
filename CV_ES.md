# Duque Ortega Mutis

**Ingeniero ML** | MLOps e Infraestructura Cloud

Ciudad de México | +52 56 1688 2440 | DuqueOrtegaMutis@gmail.com
LinkedIn: linkedin.com/in/DuqueOM | GitHub: github.com/DuqueOM | Portafolio: duqueom.github.io/ML-MLOps-Portfolio/
Idiomas: Español (Nativo), Inglés (B2) | Residencia: Residente Temporal (México) | Remoto: Disponibilidad inmediata

---

## PERFIL PROFESIONAL

Ingeniero ML que diseñó y desplegó desde cero una plataforma MLOps multi-nube en producción (GCP GKE + AWS EKS) — 6 servicios en Kubernetes (3 APIs ML + MLflow + Prometheus + Grafana), detección automática de drift, CI/CD con escaneo de seguridad y cobertura de pruebas del 90–98% (294+ pruebas, verificadas con Codecov). Historial como emprendedor serial: fundé 5 negocios en servicios tecnológicos, marketing digital, restaurantes y eventos, gestionando equipos, presupuestos, metas de ventas y operaciones multi-proveedor durante más de una década. Formación técnica autofinanciada tras relocalización de Colombia a México.

---

## HABILIDADES TÉCNICAS

- **MLOps & DevOps**: Docker (builds multi-etapa), Kubernetes (GKE, EKS, HPA, Ingress), Terraform (IaC multi-nube), GitHub Actions (CI/CD), MLflow, DVC
- **Cloud**: GCP (GKE, Cloud Storage, Artifact Registry, Cloud SQL), AWS (EKS, S3, RDS, ECR, VPC, ALB)
- **Monitoreo**: Prometheus, Grafana (auto-alojado en K8s), OpenTelemetry, explicabilidad SHAP, detección automática de drift (KS + PSI + Evidently)
- **ML/Backend**: Python 3.11+, FastAPI, Scikit-learn, LightGBM, HuggingFace Transformers, PySpark, Dask, Pandas, Pydantic
- **IA Responsable**: Auditorías de equidad (impacto dispar, paridad F1), validación de datos con Pandera, detección de drift
- **Testing & Seguridad**: Pytest (cobertura 90–98%, 294+ pruebas), Codecov, Trivy, Bandit, Gitleaks, pip-audit

---

## PROYECTOS

### Portafolio ML-MLOps | github.com/DuqueOM/ML-MLOps-Portfolio

Monorepo de producción: 3 servicios ML desplegados en GCP (GKE, 4 nodos) y AWS (EKS, 3 nodos), ciclo completo de MLOps.

- **Infraestructura Multi-Nube**: GKE (4× e2-medium) + EKS (3× t3.small), IaC con Terraform para ambas nubes, overlays Kustomize (base + gcp + aws), Init Containers para entrega de modelos desde GCS/S3, autoescalado HPA basado en CPU (escalado verificado 1→3→1 pods)
- **CI/CD**: GitHub Actions (2 workflows): `ci-mlops.yml` (10 jobs: pruebas en matriz Python 3.11/3.12, escaneo de seguridad bloqueante en severidad ALTA), `deploy-gcp.yml` + `deploy-aws.yml` (build → push → deploy)
- **Automatización MLOps**: CronJob diario de detección de drift en ambas nubes (health checks + estabilidad de predicciones vía PSI), tracking de experimentos con MLflow (3 experimentos, 14 runs), monitoreo Prometheus + Grafana (dashboard de 26 paneles)
- **Ingeniería de Datos**: ETL con PySpark procesando 6.3M viajes de taxi (2.8 GB → 95 MB Parquet), predicción batch con Dask (19K filas/seg), identificación y corrección de fuga de datos en features de ChicagoTaxi
- **IA Responsable**: Auditorías de equidad (impacto dispar, igualdad de oportunidad), detección automática de drift (KS + PSI + Evidently), esquemas de validación de datos con Pandera
- **Documentación**: 13 Registros de Decisiones de Arquitectura (ADRs), model cards con análisis de umbrales, evidencia de despliegue con métricas del clúster en producción

| Proyecto | Tipo | Métrica Principal | Pruebas |
|---------|------|------------|-------|
| **BankChurn Predictor** | Clasificación binaria | AUC 0.87, F1 0.62 | 199 pruebas, 90% cobertura |
| **NLPInsight Analyzer** | Análisis de Sentimiento NLP | Acc 80.6%, F1-macro 0.75 | 74 pruebas, 98% cobertura |
| **ChicagoTaxi Pipeline** | Pronóstico de Demanda | R² 0.96, RMSE 7.87 | 22 pruebas |

### RestoPilotAI | github.com/DuqueOM/RestoPilotAI

Aplicación IA full-stack (FastAPI + Next.js 15 + Google Gemini): pipeline agéntico de 17 etapas, 80+ endpoints, inteligencia competitiva para restaurantes con IA multimodal. Desarrollado para el Hackathon de Gemini.

### Proyectos ML Aplicados | github.com/DuqueOM/Applied-ML-Projects

4 proyectos ML orientados a producción (optimización de pozos petroleros, recuperación de oro, análisis de movilidad, mercado de gaming) con pipelines CLI, serving con FastAPI, Docker y detección de drift.

---

## CERTIFICACIONES Y EDUCACIÓN

**AWS Certified Machine Learning — Specialty** | Amazon Web Services | *(En proceso — 2026)*

**Programa Profesional de Ciencia de Datos** | TripleTen | Marzo 2026
Programa intensivo de 9 meses: Python, Machine Learning, Estadística, SQL, Ingeniería de Software. 10+ proyectos evaluados.

**Estudios Universitarios** *(interrumpidos para sostener a la familia)*:
- Ingeniería Electrónica — Universidad Distrital Francisco José de Caldas, Bogotá
- Administración de Empresas — Universidad Nacional de Colombia, Bogotá
- Marketing y Publicidad — Universidad Mariana, Pasto

---

## EXPERIENCIA PROFESIONAL

### Fundador y Operador | 5 Emprendimientos (Servicios Tech, Eventos, Restaurante, Marketing, Retail) | Colombia | 2012–2023

Fundé y operé 5 negocios durante 11 años — cada uno requirió gestión de equipos (5–10 personas), control de P&L, coordinación de proveedores y diseño de sistemas operativos. Habilidades transferibles a ingeniería:

- **Pensamiento sistémico en operaciones**: Construí flujos de trabajo repetibles para inventario, logística de proveedores y entrega a clientes — directamente aplicable al diseño de pipelines CI/CD y automatización de infraestructura
- **Servicios tecnológicos (2015–2017)**: Gestioné desarrolladores freelance que entregaban proyectos web; manejé alcance, cronogramas, QA y entrega al cliente
- **Decisiones basadas en métricas**: Administré campañas de Google Ads/Facebook Ads rastreando CPC, CTR, ROAS; apliqué la misma disciplina a métricas de modelos ML (AUC, F1, R²) y monitoreo de infraestructura (Prometheus/Grafana)

### Ventas y Operaciones | Varios Roles | Colombia | 2009–2012

Progresé de atención al cliente a líder de equipo en entornos de alto volumen. Gestioné metas de ventas, capacitación de personal y operaciones diarias.
