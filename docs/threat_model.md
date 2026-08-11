```markdown
# Threat Model

## 1. Overview

This document defines the threat scenarios considered by the LLM watermarking and adversarial attack detection project.

The primary security objective is to preserve model ownership information and detect model-level modifications.

The framework considers both malicious modifications and transformations that may occur during normal model deployment.

---

## 2. Protected Asset

The primary protected asset is the trained transformer-based language model and its associated ownership information.

The ownership information includes:

- Parameter-level watermark
- Behavioural fingerprint
- Model integrity characteristics

The watermark is treated as a secret ownership signal that should remain recoverable after model transformations.

---

## 3. Attacker Goals

An attacker may attempt to:

1. Modify model parameters.
2. Degrade or remove the embedded watermark.
3. Modify model behaviour.
4. Avoid detection.
5. Reduce the reliability of ownership verification.
6. Transform the model for efficiency while unintentionally damaging ownership information.

The project focuses primarily on model-level perturbations.

---

## 4. Attack Types

### 4.1 Pruning

The attacker removes selected model parameters, typically based on their magnitude.

Potential impact:

- Changes model parameters
- Reduces model capacity
- May remove watermark-related information
- May alter model behaviour

---

### 4.2 Gaussian Noise Injection

The attacker adds noise to model parameters.

Conceptually:

```text
w' = w + ε
