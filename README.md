# Adversarial Attacks Comparison

> **Experimental comparison of FGSM, PGD, and DeepFool — analyzing trade-offs between performance, perceptibility, and transferability**

---

##  Overview

This project implements and compares three classical adversarial attack methods — **FGSM**, **PGD**, and **DeepFool** — using **PyTorch**.  
Experiments are conducted on the **MNIST** and **CIFAR-10** datasets.

Our goal is to provide a **clear, reproducible, and interpretable** experimental study of how different attack strategies impact model robustness, visual perturbation quality, and computational cost.

Deliverables include:
- Clean, modular, and reproducible code
- Well-documented Jupyter notebooks
- Visual and quantitative results (accuracy vs ε, perturbation norms, transferability matrix)
- A concise **technical report** and **presentation slides**


---

## Table of Contents

1. [Background & Motivation](#background--motivation)
2. [Project Objectives](#project-objectives)
3. [Implementation Plan (A–Z)](#implementation-plan-a–z)
4. [Expected Results & Analysis](#expected-results--analysis)

---

## Background & Motivation

Deep neural networks are vulnerable to small, human-imperceptible perturbations known as **adversarial examples** — tiny pixel changes that can cause large misclassifications.  
These vulnerabilities pose critical challenges for **security, reliability, and interpretability** in ML systems.

Rather than training a noise generator (as other teams might do), our project performs a **systematic and reproducible comparison** of standard white-box attacks to highlight practical **trade-offs** between:

- **Attack strength:** impact on model accuracy  
- **Perturbation visibility:** measured with L∞ and L2 norms  
- **Computation cost:** time per image / per batch  
- **Transferability:** how well adversarial samples fool other architectures  

This focus on reproducibility and interpretability makes the project useful for both **academic study** and **real-world ML reliability** analysis.

---

##  Project Objectives

### Core Goals
- **Implement** three well-known adversarial attacks using PyTorch:
  - `FGSM` (Fast Gradient Sign Method)
  - `PGD` (Projected Gradient Descent)
  - `DeepFool`
- **Evaluate** each attack in terms of:
  - Model accuracy (clean vs attacked)
  - Perturbation norms (L∞, L2)
  - Average generation time per image
  - Transferability between architectures
- **Test** on:
  - **MNIST** → lightweight, visual debugging
  - **CIFAR-10** → realistic, more complex setup
- **Deliver** professional and reproducible materials:
  - Modular code, organized notebooks, plots, report, and slides

### Optional Extensions
- Implement **Adversarial Training** (e.g., FGSM-based)  
  → Study how including adversarial samples during training affects robustness and cost.

---

##  Implementation Plan (A–Z)

### Environment Setup
- Create a Python environment (`conda` or `venv`)  
- Dependencies:
  ```bash
  torch
  torchvision
  numpy
  pandas
  matplotlib
  tqdm
  scikit-image
