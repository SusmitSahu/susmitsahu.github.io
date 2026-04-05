---
layout: page
title: Physics-Informed Neural Networks for Battery Pack Modeling
description: PINNs, DeepONet, and FNO-based framework for multi-physics battery simulation
img: assets/img/projects/pinns_battery.jpg
importance: 1
category: Scientific ML & Digital Twin
---

## Overview

This project develops a **physics-informed and operator-learning framework** to model the coupled
electrochemical, thermal, and mechanical behavior of battery cells — enabling seamless integration
with pack-level simulations and BMS deployment.

## Methods

### Physics-Informed Neural Networks (PINNs)
Embeds governing PDEs (electrochemical, thermal, mechanical) directly into the neural network
loss function, ensuring physical consistency without requiring large labeled datasets.

### DeepONet & Fourier Neural Operators (FNO)
Operator-learning approaches that learn mappings between function spaces, enabling rapid
surrogate evaluation across different operating conditions, chemistries, and geometries.

### Multi-Scale Framework
- **Cell-level:** Coupled P2D electrochemical + mechanical models
- **Pack-level:** Translated cell physics into pack-level thermal and degradation insights

## Key Results

- 📈 **20–30% improvement** in SOH and performance prediction accuracy vs. reduced-order and
  purely data-driven models
- ⚡ **>10× faster** surrogate modeling vs. full FEM simulations, enabling real-time BMS integration
- 🔋 **Multi-chemistry support** (Li-ion, Na-ion, composite electrodes) for next-generation energy storage

## Technologies

`Python` · `PyTorch` · `FEniCSx` · `HPC (OpenMPI)` · `MATLAB` · `Scikit-learn`

## Impact

Enables real-time digital twin deployment in Battery Management Systems and provides a
pathway to physics-grounded AI for EV and grid storage applications.
Targeting battery and EV companies (e.g., Agratas) — currently in ideation phase.
