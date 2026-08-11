```markdown
# Methodology

## 1. Overview

This project proposes a unified security framework for transformer-based language models.

The framework combines:

1. White-box watermarking
2. Black-box fingerprinting
3. Adversarial robustness
4. Intrusion detection
5. Automated countermeasures

The current experimental implementation primarily focuses on parameter-level watermarking, model-level perturbations, attack detection, and prototype countermeasures.

---

## 2. Base Model

The experimental pipeline uses **DistilGPT-2** as the transformer-based language model.

The model is implemented using:

- PyTorch
- Hugging Face Transformers

The model processes text using the standard transformer pipeline:

```text
Input Text
    |
    v
Tokenizer
    |
    v
Token IDs
    |
    v
Token Embeddings
    +
Positional Information
    |
    v
Transformer Blocks
    |
    v
Language Model Output
