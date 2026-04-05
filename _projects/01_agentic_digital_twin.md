---
layout: page
title: GenAI Agentic Digital Twin
description: LLM-powered agentic system for battery digital twin automation and parameter estimation
img: assets/img/projects/agentic_digital_twin.jpg
importance: 1
category: GenAI & Agentic AI
---

## Overview

This project develops a fully **agentic AI workflow** for automating the calibration and parameter estimation
of physics-based battery models — a task traditionally requiring significant expert manual effort.

## Key Contributions

- **Agentic LLM Workflow:** Built a multi-agent system using LLMs (via LangChain) to autonomously reason
  about battery model parameters, select estimation strategies, and iteratively refine model calibration
  without human intervention.

- **RAG-Based Knowledge System:** Developed a Retrieval-Augmented Generation pipeline integrating
  battery experimental datasets and scientific literature (via ChromaDB / Weaviate vector stores),
  enabling context-aware decision-making grounded in domain knowledge.

- **Two-Stage Optimization Pipeline:** Implemented a global search (differential evolution / CMA-ES)
  followed by gradient-based refinement (L-BFGS-B), achieving robust parameter identification even
  under noisy experimental data.

- **HPC Integration:** Deployed the full pipeline on HPC clusters for handling computationally
  intensive physics-based simulations in parallel.

## Technologies

`Python` · `LangChain` · `LLMs (Claude, GPT, Ollama)` · `ChromaDB` · `Weaviate` · `PyTorch` · `HPC` · `Docker`

## Impact

Significantly reduced manual expert effort in battery model calibration, enabling faster model
turnaround for digital twin integration and BMS deployment.
