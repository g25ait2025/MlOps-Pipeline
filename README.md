# Project Execution Guide

## 1. Introduction

This repository documents the complete implementation workflow, deployment structure, and evaluation process for **MLOps Assignment 2**. The project pipeline was derived from a reference implementation and further customized for efficient execution within a cloud-based Kaggle environment.

The workflow combines:

* Transformer architectures hosted on [Hugging Face](https://huggingface.co)
* Experiment monitoring through [Weights & Biases (W&B)](https://wandb.ai)

The integrated setup enables:

* Real-time experiment tracking
* Automatic checkpoint logging
* Loss and accuracy monitoring
* Centralized artifact management across training epochs

---

# 2. Installation & Environment Setup

To reproduce the training pipeline successfully, follow the setup sequence below.

## Step 1 — Install Dependencies

Initialize the runtime environment by installing all required libraries from the project manifest file:

```bash
pip install -r requirements.txt
```

This command installs:

* Transformer libraries
* Dataset utilities
* Experiment tracking packages
* Model optimization dependencies

---

## Step 2 — Configure Authentication Tokens

Before executing the notebook or training script, configure the following API credentials.

### Hugging Face Access Token

Used for:

* Downloading pretrained models
* Accessing hosted repositories
* Uploading trained checkpoints

Generate token from:
[Hugging Face Tokens](https://huggingface.co/settings/tokens)

### W&B API Key

Required for:

* Logging experiments
* Monitoring metrics
* Synchronizing training runs

Generate token from:
[Weights & Biases Settings](https://wandb.ai/settings)

Store both credentials securely inside:

* Kaggle Secrets
* Environment variables
* Notebook secret manager

---

# 3. Pipeline Execution Process

The execution lifecycle follows a sequential end-to-end workflow:

### 1. Baseline Import

Initial model components and notebook structures were imported from the original reference implementation.

### 2. Kaggle Migration

The pipeline was adapted into a Kaggle notebook runtime to leverage cloud GPU execution and persistent storage support.

### 3. Environment Adaptation

Several modifications were introduced during migration:

* Updated file paths
* Adjusted storage references
* Optimized runtime compatibility
* Added dynamic token integration for external services

### 4. Unified Runtime Execution

After dependency installation and credential injection, the complete workflow executes continuously in a single runtime session, including:

* Dataset preparation
* Model loading
* Fine-tuning
* Validation
* Metric logging
* Artifact synchronization

---

# 4. Experimental Results

The final trained model was evaluated against the validation benchmark after completion of fine-tuning.

| Evaluation Metric | Final Score |
| ----------------- | ----------- |
| Accuracy          | 57.31%      |
| F1 Score          | 0.58360     |
| Validation Loss   | 2.71064     |

---

# 5. Project Resources & Deployment Links

## Kaggle Notebook

[Kaggle Execution Notebook](https://www.kaggle.com/code/bhoopendrakumarg25/ml-ops)

## Hugging Face Model Repository

[DistilBERT Goodreads Genre Classifier](https://huggingface.co/Bhoop-g25ait2025/distilbert-goodreads-genres)

## W&B Experiment Dashboard

[Weights & Biases Tracking Dashboard](https://wandb.ai/g25ait2025-prom-iit-rajasthan/huggingface?nw=nwuserg25ait2025)

---

# 6. Execution Notes

* The pipeline is optimized for cloud notebook execution.
* GPU acceleration is recommended for stable training performance.
* Continuous execution is preferred to avoid runtime interruption or checkpoint desynchronization.
* All experiment logs and trained artifacts are automatically synchronized with external registries once authentication is configured properly.
