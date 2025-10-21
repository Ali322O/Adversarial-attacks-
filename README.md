    
# Adversarial-attacks-


Adversarial-Attacks-Comparison

Experimental comparison of FGSM, PGD, and DeepFool — trade-offs between performance, perceptibility, and transferability

Summary

This project focuses on implementing and comparing three classical adversarial attack methods (FGSM, PGD, and DeepFool) using PyTorch, evaluated on MNIST and CIFAR-10 datasets.

The goal is to provide a clear, reproducible, and interpretable experimental comparison of the trade-offs between attack effectiveness, perturbation visibility, computational cost, and transferability across models.

Deliverables include: clean and reproducible code, well-documented notebooks, experiment results (accuracy vs ε, norm distributions, transferability matrix), a concise technical report, and presentation slides.
This project demonstrates practical ML and research skills: PyTorch implementation, experimental design, quantitative analysis, visualization, and robustness evaluation.

Table of Contents

Background & Motivation

Project Objectives

What We Will Implement (A–Z)

Expected Results & Analysis

Background & Motivation

Deep learning models are vulnerable to small, human-imperceptible perturbations known as adversarial examples, which can cause misclassifications with minimal visual change. These vulnerabilities raise critical concerns regarding the security and reliability of machine learning systems.

Instead of building a noise generator (as another team is doing), our project aims to perform a systematic and reproducible experimental study of standard attack methods.
We focus on understanding the practical trade-offs between:

Attack strength (impact on accuracy)

Perturbation magnitude and perceptibility (L∞, L2 norms)

Computation cost (time per image)

Transferability (how well perturbations fool other models)

This approach emphasizes experimental rigor, reproducibility, and interpretability — qualities that are valuable for both research and professional ML settings.

Project Objectives

Implement three well-known adversarial attacks using PyTorch:

FGSM (Fast Gradient Sign Method)

PGD (Projected Gradient Descent)

DeepFool

Evaluate each attack with respect to:

Accuracy degradation (clean vs attacked)

Perturbation norms (L∞ and L2)

Average generation time per image

Transferability across architectures

Conduct experiments on MNIST (simple and visual) and CIFAR-10 (more realistic).

Deliver professional, reproducible materials: modular code, notebooks, visualizations, report, and presentation slides.

Optional extension: implement adversarial training (e.g., FGSM-based training) to measure its impact on robustness vs training cost.

What We Will Implement (A–Z)
Environment Setup

Create a Python environment (conda or venv) with the following dependencies:
PyTorch, torchvision, numpy, pandas, matplotlib, tqdm, scikit-image.

Include a requirements.txt file and clear instructions for reproducing results on local or cloud GPU setups.

Dataset Preparation

Load and preprocess MNIST and CIFAR-10 datasets.

Apply standard normalization and define training, validation, and test splits.

Implement DataLoaders for both datasets.

Models

MNIST: small CNN (LeNet-style).

CIFAR-10: lightweight ResNet-18 or custom CNN.

Use two different architectures per dataset to evaluate transferability (e.g., LeNet vs CNN; ResNet18 vs VGG-like).

Attack Implementations (modular structure)

fgsm.py — Vectorized FGSM implementation, API: fgsm_attack(model, x, y, epsilon)

pgd.py — PGD / Iterative FGSM with L∞ projection (epsilon, alpha, n_iter).

deepfool.py — DeepFool attack (L2 minimal perturbation approach).

Each module will be unit-tested on small batches and documented with expected inputs and normalization details.

Experiment Scripts

train_model.py — trains baseline models and saves checkpoints.

generate_attacks.py — generates and saves adversarial examples for each attack and configuration.

run_experiment.py — automates evaluation across ε grids and exports metrics to CSV.

notebooks/analysis.ipynb — visualizations and figure generation.

Metrics & Outputs

Accuracy (clean vs attacked).

Perturbation norms (L∞ and L2 distributions).

Computation time (ms per image).

Visual examples: original vs adversarial vs perturbation difference.

Transferability matrix: measures how attacks generated on model A affect model B.

Reproducibility

Fixed random seeds (torch.manual_seed, np.random.seed).

Consistent input normalization (important for ε values).

Save experiment parameters and results (JSON/CSV).

Clear folder structure and documentation for all experiments.

Expected Results & Analysis

The project aims to produce clear, interpretable results that can be easily understood by both academic and industry audiences.

Accuracy vs ε curves: visualize model degradation under increasing perturbation strength for FGSM, PGD, and DeepFool on MNIST and CIFAR-10.

Norm distributions (boxplots or histograms): compare perturbation magnitudes (DeepFool typically yields smaller norms).

Computation cost table: report average generation time per image for each attack — useful for real-world feasibility discussions.

Transferability matrix: heatmap showing accuracy drop when adversarial samples generated on one model are applied to another.

Visual examples: side-by-side comparisons (original, adversarial, and difference images).

Analytical summary: discuss trade-offs (strength vs perceptibility vs cost), key insights, and practical implications for robust ML deployment.