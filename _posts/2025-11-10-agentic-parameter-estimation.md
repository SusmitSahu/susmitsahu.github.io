---
layout: post
title: "Building Agentic AI Workflows for Scientific Parameter Estimation"
date: 2025-11-10 10:00:00 +0530
description: How LLM-powered multi-agent systems can automate the tedious process of physics-based model calibration.
tags: [agentic-ai, LLM, RAG, battery-modeling, langchain]
categories: genai
related_posts: true
---

Parameter estimation — fitting a physics-based model's parameters to match experimental data —
is one of the most time-consuming steps in scientific modeling. Typically, it requires an expert
who understands both the model equations and the experimental artifacts. What if we could automate
this with LLMs?

## The Problem

In battery modeling, a full **P2D electrochemical model** can have 30–50 parameters:
diffusion coefficients, reaction rate constants, transport numbers, electrode geometry, and more.
Many of these cannot be measured directly; they must be inferred by fitting model outputs to
charge-discharge curves.

This is:
- **Computationally expensive** (each FEM evaluation takes minutes)
- **Expert-dependent** (knowing which parameters are sensitive requires domain knowledge)
- **Iterative** (global search followed by local refinement)

## The Agentic AI Approach

We designed a **multi-agent LLM system** using LangChain and Claude/GPT as the backbone LLM,
with the following agent roles:

```
┌─────────────────────────────────────────────────────┐
│                  Orchestrator Agent                  │
│   (plans estimation strategy, monitors progress)     │
└────────────┬──────────────────────┬─────────────────┘
             │                      │
    ┌────────▼──────┐     ┌─────────▼──────────┐
    │  RAG Agent    │     │  Optimizer Agent    │
    │ (retrieves    │     │ (runs global search │
    │  literature   │     │  + gradient refine) │
    │  knowledge)   │     └─────────────────────┘
    └───────────────┘
```

### RAG Agent
Queries a **ChromaDB vector store** populated with:
- Battery parameter databases from literature
- Experimental characterization papers
- Internal calibration reports

When the optimizer needs a starting point or bounds for a parameter, the RAG agent retrieves
the most relevant literature values.

### Optimizer Agent
Implements a **two-stage optimization**:
1. **Global search** using Differential Evolution or CMA-ES to explore the parameter space
2. **Local refinement** using L-BFGS-B for gradient-based convergence

The agent dynamically selects the strategy based on the LLM's assessment of the optimization
landscape (noisy data → global first; smooth data → direct gradient).

### Orchestrator Agent
The LLM orchestrator:
- Decomposes the calibration task into sub-goals
- Monitors convergence metrics
- Decides when to switch between global and local phases
- Writes a structured calibration report on completion

## Key Results

- **Reduced manual effort** by >60% on routine calibration tasks
- **Robust to noisy data** — two-stage approach consistently outperforms single-method optimization
- **Explainable** — the RAG-grounded LLM produces natural language reasoning alongside the numerical output

## Reflections

The most surprising finding was how well the LLM handled **uncertainty quantification decisions** —
reasoning about when a parameter was truly identifiable from the data vs. when the problem was
underdetermined. This kind of meta-reasoning is something rule-based systems struggle with.

The combination of **domain knowledge retrieval (RAG) + optimization execution + LLM reasoning**
creates a genuinely powerful loop for scientific automation. I believe this paradigm — agentic AI
for scientific workflows — will be a major research direction in the coming years.
