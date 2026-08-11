# LLM Watermarking and Adversarial Attack Detection

A research project investigating ownership protection, model integrity,
and robustness of transformer-based language models against model-level
perturbations.

## Overview

This project explores a unified framework for protecting large language
models through:

- White-box watermarking
- Black-box fingerprinting
- Adversarial robustness
- Intrusion detection
- Automated countermeasures

The framework investigates whether ownership information can remain
reliable when a model undergoes common model transformations such as
pruning, noise injection, quantization, and parameter sign flipping.

## Current Implementation

The current experimental pipeline uses:

- DistilGPT-2
- PyTorch
- Hugging Face Transformers
- Projection-based weight watermarking
- Multi-signal attack detection
- Attack-specific countermeasure prototypes

The implemented model-level perturbations include:

1. Weight pruning
2. Gaussian noise injection
3. Quantization
4. Sign flipping

## Detection

The prototype intrusion detection system analyzes multiple model-level
signals, including:

- Watermark bit accuracy
- Weight norm
- Weight statistics
- Sparsity
- Sign changes
- Distribution changes
- Gradient-related information

Attack classification is evaluated using accuracy, precision, recall,
F1-score, and a confusion matrix.

## Research Objectives

The broader research framework aims to combine:

- White-box ownership verification
- Black-box behavioral fingerprinting
- Adversarial robustness training
- Model integrity monitoring
- Automated recovery mechanisms

## Evaluation

The experimental framework evaluates:

- Watermark bit accuracy
- Watermark loss
- Language-model loss
- Attack detection performance
- Attack classification
- Precision, recall, and F1-score
- Confusion matrix
- Detection latency
- Model recovery after perturbations

Current results are considered preliminary and are used to identify
limitations and guide further experimentation.

## Repository Structure

```text
llm-watermark-attack-detection/
│
├── .gitignore             
├── README.md
├── requirements.txt
│
├── notebooks/
│   ├── 01_watermark_pipeline.ipynb
│   └── 02_results_analysis.ipynb
│
└── docs/
    ├── methodology.md
    ├── research_background.md
    ├── threat_model.md
    └── experiments.md
