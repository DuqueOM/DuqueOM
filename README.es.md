<div align="center">

# Junior AI Engineer · Apps con LLM y agentes · ML en producción · Ciudad de México

## Duque Ortega Mutis

[English](README.md) · Español

Soy AI Engineer junior (ingeniero de inteligencia artificial). Diseño y construyo sistemas de IA y de machine learning
de principio a fin: datos, modelo, API, contenedor y nube. Trabajo con LLM (modelos de lenguaje grandes) y agentes.
Antes de la tecnología dirigí mis propios negocios y operaciones durante 14 años, por eso construyo para usuarios reales
y resultados medibles.
Trabajo con agentes de programación con IA (Claude Code) para avanzar más rápido. El diseño, las decisiones y la
revisión son míos.

[![Portafolio](https://img.shields.io/badge/Portafolio-Sitio_web-22D3EE?style=for-the-badge&logo=github-pages&logoColor=white)](https://duqueom.github.io/ML-MLOps-Portfolio/)
[![YouTube](https://img.shields.io/badge/Demo-3_min-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtu.be/7dFFqq2ROPw)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Conectar-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/DuqueOM)
[![Correo](https://img.shields.io/badge/Correo-Contacto-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:DuqueOrtegaMutis@gmail.com)

</div>

## Proyectos destacados

**[agent-whatsapp-php](https://github.com/DuqueOM/agent-whatsapp-php)** · agente de atención al cliente para WhatsApp (en desarrollo)<br>
PHP 8.3, MySQL, webhooks de la Meta Cloud API, tool calling con LLM (el modelo llama a funciones para consultar datos
reales), traspaso a una persona (human handoff) y evaluaciones automáticas de las respuestas (evals).
Escribí la especificación y el plan, y escribo la lógica central. Los agentes de IA generan la base del código, que
reviso personalmente.
Primera versión planeada para enero de 2027.

**[ML-MLOps-Portfolio](https://github.com/DuqueOM/ML-MLOps-Portfolio)** · tres servicios de ML, desplegados en GKE y EKS<br>
Predicción de abandono de clientes, sentimiento financiero y pronóstico de demanda de taxis, servidos con FastAPI,
Docker y Kubernetes, con Terraform, CI/CD, MLflow y monitoreo. Desplegados en GKE (Google Cloud) y EKS (AWS) en marzo
de 2026 y luego apagados para ahorrar costos.
Diseñé la arquitectura y tomé las decisiones (19 ADRs, registros escritos de las decisiones de arquitectura); los
agentes de programación con IA me ayudaron a construirlo más rápido.


<p align="center"><img src="https://raw.githubusercontent.com/DuqueOM/ML-MLOps-Portfolio/main/docs/media/gifs/portfolio-demo.gif" alt="Demo del portafolio: los tres servicios de ML, sus tableros y sus predicciones" width="580"></p>

Tres problemas que encontré y resolví en pruebas de carga en mis propios clústeres de GKE y EKS:

```
81% de errores bajo carga  →  varios workers de uvicorn dentro de Kubernetes. Resuelto con asyncio + un pool de hilos: 81% → 0%
SHAP devolvía solo ceros   →  TreeExplainer no funciona con StackingClassifier. Resuelto con KernelExplainer
El HPA nunca reducía pods  →  HPA por memoria con un modelo que ocupa memoria fija. Resuelto escalando solo por CPU: 3 → 1 pods
```

[Leer cómo los encontré y los resolví (en inglés) →](https://duqueom.github.io/ML-MLOps-Portfolio/technical-evidence/)

**[read_aloud](https://github.com/DuqueOM/read_aloud)** · una app de texto a voz que uso todos los días<br>
Lee en voz alta el texto seleccionado en Windows con voces neuronales locales, en español e inglés en el mismo texto,
sin internet.
Ajusté una voz de Qwen3-TTS con LoRA (una técnica de fine-tuning, es decir, de ajuste fino de un modelo) en mi propia
GPU (RTX 5070 Laptop GPU, 8 GB), elegí la configuración de entrenamiento y la época final, y usé WavLM para comparar
voces. 15 ADRs registran las decisiones. Construida con agentes de programación con IA.

<p align="center"><img src="https://raw.githubusercontent.com/DuqueOM/read_aloud/main/docs/media/demo.gif" alt="Demo de read_aloud: el texto seleccionado se lee en voz alta y cada frase se resalta" width="580"></p>

## Cómo trabajo

- Empiezo por el problema: escribo la especificación, los límites y las decisiones (ADRs).
- Construyo con agentes de programación con IA dentro de reglas que yo defino: pruebas primero, cambios pequeños y
  revisados, y controles de CI.
- Mido: pruebas de carga y evaluaciones (evals). Cuando algo falla, busco la causa con datos, lo arreglo y registro la
  decisión en un ADR.

## Siguiente paso

Maestría en Inteligencia Artificial en la University of Colorado Boulder (en línea, Coursera), planeada para 2027.

## Estudios de arquitectura

Sistemas más grandes que diseñé y dirigí. Los agentes de programación con IA escribieron la mayor parte del código. No
están desplegados en la nube.<br>
[ml-service-template](https://github.com/DuqueOM/ml-service-template) (ML clásico en Kubernetes) ·
[ml-platform](https://github.com/DuqueOM/ml-platform) (datos tabulares, deep learning, LLM y agentes) ·
[agent-local](https://github.com/DuqueOM/agent-local) (núcleo de un agente LLM local)

---

Busco puestos junior de AI Engineer, ML Engineer o MLOps (llevar modelos de machine learning a producción y operarlos) ·
Remoto o Ciudad de México · Español (nativo), inglés (B1) · TripleTen Data Science
