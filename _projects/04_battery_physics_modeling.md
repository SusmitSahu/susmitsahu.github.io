---
layout: page
title: Physics-Based Battery Modeling & System Integration
description: Multi-scale P2D electrochemical models for Li-ion and Na-ion batteries with BMS integration
img: assets/img/projects/battery_modeling.jpg
importance: 2
category: Scientific ML & Digital Twin
---

## Overview

A comprehensive **physics-based battery modeling framework** spanning cell-level electrochemical
simulation to pack-level system integration, validated against experimental data and designed for
BMS deployment.

## Key Work

### Multi-Scale P2D Electrochemical Modeling
- Developed a full **Pseudo-Two-Dimensional (P2D)** electrochemical model for sodium-ion batteries
  in FEniCSx, linking material-scale ion transport and mechanics with system-level performance.
- Extended models to **composite electrode architectures** (Li-ion, Na-ion, mixed chemistries).

### All-Solid-State Battery Interface Modeling
- Modeled **electrode-electrolyte interfaces** using **Cohesive Zone Modeling (CZM)**,
  capturing failure mechanisms and stress distributions during cycling.

### Equivalent Circuit Models (ECM)
- Developed and validated physics-based ECMs for system-level battery simulations,
  calibrated against charge-discharge cycling data for BMS control applications.

### Pack-Level Integration
- Translated cell-level physics into pack-level lifecycle predictions,
  improving **life prediction accuracy by ~25%** and enabling early-stage design decisions.

## Technologies

`FEniCSx` · `Python` · `PyBaMM` · `Scikit-optimize` · `Linux` · `MATLAB` · `OpenMPI`

## Impact

Provides a validated multi-chemistry battery simulation stack directly applicable to BMS
algorithm development, battery design optimization, and state estimation in electric vehicles
and grid storage.
