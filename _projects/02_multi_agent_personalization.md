---
layout: page
title: Multi-Agent GenAI Personalization System
description: Azure-based multi-agent GenAI system for intelligent, context-aware personalization
img: assets/img/projects/multi_agent_genai.jpg
importance: 2
category: GenAI & Agentic AI
---

## Overview

A production-grade **multi-agent GenAI system** built on Azure Foundry for intelligent personalization,
combining LLM reasoning with semantic retrieval and Responsible AI practices.

## Architecture

The system orchestrates specialized agents via a **FastAPI backend**:

- **Routing Agent:** Classifies incoming user queries and directs them to the appropriate downstream agent.
- **Recommendation Agent:** Generates personalized content recommendations using LLM reasoning over user context.
- **Sentiment Analysis Agent:** Analyzes user sentiment to dynamically adapt tone and recommendations.
- **Memory Agent:** Maintains short-term and long-term user context across sessions using vector stores.

## Key Features

- **Azure OpenAI + Vector Search:** Semantic retrieval over user profiles and content databases
  using Azure Cognitive Search with embedding-based indexing.
- **Responsible AI Integration:** Prompt safety filters, output validation layers, and
  role-based access control ensuring safe and compliant AI behavior.
- **Containerized Deployment:** Full Docker-based deployment on Azure Container Apps for scalability.

## Technologies

`Azure Foundry` · `Azure OpenAI` · `FastAPI` · `LangChain` · `VectorDB` · `Docker` · `Python`

## Impact

Demonstrated end-to-end multi-agent orchestration with production-ready Responsible AI guardrails,
applicable to enterprise personalization, intelligent assistants, and customer-facing AI products.
