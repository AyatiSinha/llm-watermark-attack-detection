# Research Background

## 1. Introduction

The rapid evolution of artificial intelligence, particularly in the domain of natural language processing (NLP), has been significantly driven by transformer-based large language models (LLMs). Transformer-based models have demonstrated strong capabilities in tasks such as text generation, machine translation, summarization, and conversational AI.

The increasing deployment of these models in real-world applications has created new challenges related to model ownership, intellectual property protection, security, and robustness.

Training large language models requires substantial computational resources, large-scale datasets, and significant expertise. As a result, trained models represent valuable intellectual assets. However, once models are distributed, fine-tuned, compressed, or deployed across different environments, their parameters and behaviour can potentially be modified or reproduced without authorization.

This creates a need for mechanisms that can establish model ownership and verify the integrity of models after deployment.

---

## 2. Model Ownership Protection

Two important approaches to model ownership protection are watermarking and fingerprinting.

### 2.1 White-Box Watermarking

Watermarking embeds ownership information directly into model parameters.

The verification process requires access to the internal parameters of the model and is therefore considered a white-box approach.

A parameter-level watermark can be represented using a binary ownership message embedded through a projection-based constraint on selected model weights.

The goal is to ensure that the watermark can later be extracted from the model parameters while maintaining the model's primary functionality.

### 2.2 Black-Box Fingerprinting

Fingerprinting relies on the behavioural characteristics of a model rather than directly inspecting its parameters.

A fingerprint can be constructed using specific input-output relationships. Ownership can then be verified by sending selected inputs to the model and observing whether the expected behavioural signature is produced.

This makes fingerprinting useful in black-box settings where the model's internal parameters are not accessible.

---

## 3. Limitations of Existing Approaches

Although watermarking and fingerprinting provide useful mechanisms for ownership verification, several limitations remain.

### 3.1 Isolated Ownership Techniques

Many approaches focus on either watermarking or fingerprinting independently.

Watermarking provides parameter-level ownership verification but requires internal model access, while fingerprinting provides behavioural verification but may depend on the persistence of specific model behaviours.

A unified approach combining both settings can provide broader ownership verification capabilities.

### 3.2 Robustness Against Model Transformations

Models are frequently modified after training.

Common transformations include:

- Pruning
- Quantization
- Noise injection
- Fine-tuning
- Parameter modifications

Such transformations can unintentionally modify or remove embedded ownership information.

From a security perspective, these transformations can also be treated as attack vectors because they may degrade the reliability of ownership verification.

### 3.3 Static Ownership Protection

Traditional ownership protection approaches often focus primarily on embedding information.

There is comparatively less emphasis on continuously monitoring model integrity, detecting modifications, and responding to detected attacks.

This motivates the integration of ownership verification with attack detection and recovery mechanisms.

### 3.4 Transformer-Based Models

Many earlier model-watermarking techniques were developed for smaller neural-network architectures.

Modern transformer-based language models have substantially more complex parameter interactions and representations. This creates additional challenges when adapting ownership protection mechanisms to transformer architectures.

---

## 4. Research Gap

The project focuses on the following research gaps:

1. Limited integration between white-box watermarking and black-box fingerprinting.
2. Limited robustness evaluation across multiple model-level perturbations.
3. Limited integration of ownership verification with continuous model integrity monitoring.
4. Limited evaluation of attack-specific recovery mechanisms.
5. Need for ownership protection mechanisms suitable for transformer-based language models.

---

## 5. Motivation

The motivation of this work is to move model ownership protection beyond a static embedding process toward a more comprehensive security framework.

The proposed direction combines:

- White-box watermarking
- Black-box fingerprinting
- Adversarial robustness
- Intrusion detection
- Automated countermeasures

The framework is intended to investigate whether ownership information can remain reliable when a transformer-based language model undergoes common model-level transformations.

---

## 6. Research Direction

The proposed framework uses a transformer-based language model as the base architecture and evaluates ownership protection under different model transformations.

The overall research direction is:

```text
Transformer Language Model
          |
          +----------------------+
          |                      |
          v                      v
   White-Box Watermark     Black-Box Fingerprint
          |                      |
          +----------+-----------+
                     |
                     v
            Robustness Testing
                     |
       +-------------+-------------+
       |             |             |
       v             v             v
    Pruning        Noise      Quantization
                     |
                 Sign Flip
                     |
                     v
              Intrusion Detection
                     |
                     v
              Countermeasures
