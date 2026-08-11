```markdown
# Experimental Setup and Evaluation

## 1. Overview

This document describes the experimental setup used to evaluate the prototype LLM watermarking and adversarial attack detection framework.

The experiments investigate:

- Watermark embedding
- Watermark extraction
- Model-level perturbations
- Attack detection
- Attack classification
- Countermeasures
- Model utility

The current results are considered preliminary.

---

## 2. Model

The current experimental pipeline uses:

**Model:** DistilGPT-2

The model is implemented using:

- PyTorch
- Hugging Face Transformers

DistilGPT-2 is used as a manageable transformer-based language model for developing and testing the security framework.

---

## 3. Watermark Configuration

The current experimental implementation uses a projection-based binary watermark.

The watermark configuration includes:

- 64 watermark bits
- Random projection matrix
- Binary ownership message
- Projection-based watermark loss

The watermark is embedded into a selected transformer layer.

The current implementation focuses on a model weight tensor from the final transformer block.

---

## 4. Training Objective

The training objective combines:

```text
Language Modeling Loss
+
Watermark Loss
