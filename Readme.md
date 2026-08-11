# LLM Watermarking and Adversarial Attack Detection

A research project investigating ownership protection and robustness of
transformer-based language models against model-level attacks.

## Overview

This project explores a unified framework for protecting large language
models through:

- White-box watermarking
- Black-box fingerprinting
- Adversarial robustness
- Intrusion detection
- Automated countermeasures

The framework investigates whether ownership information can remain
reliable when a model undergoes common transformations such as pruning,
noise injection, quantization, and parameter sign flipping.

## Current Implementation

The current experimental pipeline uses:

- DistilGPT-2
- PyTorch
- Hugging Face Transformers
- Projection-based weight watermarking
- Multi-signal attack detection
- Attack-specific countermeasures

The implemented attack scenarios include:

1. Weight pruning
2. Gaussian noise injection
3. Quantization
4. Sign flipping

## Detection

The prototype detection system analyzes multiple signals, including:

- Watermark bit accuracy
- Weight norm
- Weight statistics
- Sparsity
- Sign changes
- Distribution changes
- Gradient information

## Research Objectives

The broader research framework aims to combine:

- White-box ownership verification
- Black-box behavioral fingerprinting
- Adversarial robustness training
- Model integrity monitoring
- Automated recovery mechanisms

## Evaluation

The experimental framework tracks:

- Watermark bit accuracy
- Attack detection performance
- Attack classification
- Detection latency
- Prevention/recovery events
- Language-model loss

## Repository Structure

```text
llm-watermark-attack-detection/
│
├── notebooks/
│   ├── 01_watermark_pipeline.ipynb
│   └── 02_results_analysis.ipynb
│
├── docs/
│   ├── methodology.md
│   └── research_background.md
│
├── results/
│   ├── figures/
│   └── metrics/
│
├── requirements.txt
└── README.md
