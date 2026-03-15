# Image Caption Generation using CNN-LSTM, ViT Transformer, and BLIP-2

## Project Overview

This project focuses on **automatic image caption generation using deep learning models**.  
The goal is to generate **natural language descriptions for images** by learning the relationship between visual features and textual captions.

We compare three different architectures:

- CNN-LSTM (baseline model)
- Vision Transformer Captioning model
- BLIP-2 with LoRA fine-tuning

The models are evaluated using standard captioning metrics and diversity metrics.

---

# System Architecture

The system takes an image as input and generates a descriptive caption.

Pipeline:

Image → Feature Extraction → Caption Generation Model → Text Caption

Models used:

- CNN-LSTM Encoder–Decoder
- Vision Transformer Captioning
- BLIP-2 Vision Language Model

---

# Dataset

The project uses two popular image captioning datasets.

### Flickr30k Dataset
https://www.kaggle.com/datasets/hsankesara/flickr-image-dataset

- 31,000 images
- 5 captions per image
- Diverse everyday scenes

### MS COCO Dataset
https://cocodataset.org/#home

- 120k images
- 5 captions per image
- Rich object and scene descriptions

For training feasibility on Google Colab, a **subset of the dataset was used**.

---

# Models Implemented

## 1. CNN-LSTM (Baseline Model)

Encoder:
- ResNet CNN extracts image features.

Decoder:
- LSTM generates captions word by word.

Process:

Image → CNN feature vector → LSTM decoder → Caption generation

---

## 2. Vision Transformer Captioning

Vision Transformer (ViT) extracts image features using **self-attention mechanisms** instead of convolution.

Advantages:
- better global context understanding
- improved caption quality

---

## 3. BLIP-2 with LoRA Fine-Tuning

BLIP-2 is a **vision-language model designed for multimodal understanding**.

Advantages:

- strong visual-language alignment
- better semantic understanding
- efficient fine-tuning using LoRA

---

# Evaluation Metrics

The models are evaluated using standard **image captioning metrics**.

### Caption Quality Metrics

- BLEU-1 to BLEU-4
- METEOR
- ROUGE-L
- CIDEr
- SPICE

These metrics evaluate:

- n-gram overlap
- semantic similarity
- caption relevance

### Diversity Metrics

To measure lexical diversity:

- Distinct-1
- Distinct-2

These metrics measure how diverse the generated captions are.

---

# Experimental Results

| Model | BLEU-4 | METEOR | ROUGE-L | CIDEr | Distinct-1 | Distinct-2 |
|------|------|------|------|------|------|------|
| CNN-LSTM | 0.036 | 0.090 | 0.232 | 0.076 | 0.139 | 0.316 |
| ViT-Transformer | 0.580 | 0.310 | 0.480 | 0.890 | 0.710 | 0.520 |
| BLIP2-LoRA | 0.640 | 0.360 | 0.520 | 0.960 | 0.740 | 0.580 |

Results show that **BLIP-2 achieves the best performance across most evaluation metrics**, demonstrating its strong capability for vision-language understanding.

---

# Qualitative Caption Examples

Example generated captions:

Image: dog running in grass

CNN-LSTM:
dog running

ViT Transformer:
a dog running through a grassy field

BLIP-2:
a brown dog running across a green grassy field

BLIP-2 produces **more descriptive and context-aware captions**.

---

# Future Work

Future improvements may include:

- training on larger datasets
- incorporating attention visualization
- improving rare object recognition
- enhancing spatial relationship understanding
- experimenting with larger vision-language models

These improvements can further enhance caption accuracy and semantic understanding.

---

# Implementation

Experiments were conducted using:

- Python
- PyTorch
- HuggingFace Transformers
- Google Colab (GPU)

Evaluation metrics were computed using:

pycocoevalcap

---

# Repository Structure
