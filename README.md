
# Deep Captioning for Instructional Cooking Videos

This repository contains the implementation of an attention-based video captioning system designed for instructional cooking videos. The project utilizes a CNN-Transformer encoder-decoder architecture to generate natural language descriptions for temporally localized video segments from the **YouCookII** dataset.

## 📋 Overview

Automated video captioning enables improved content understanding and accessibility. This project focuses on generating accurate, step-wise captions for cooking videos by modeling fine-grained actions and temporal structures, formulated as a sequence-to-sequence learning problem.

## 🚀 Key Contributions

* **Architecture:** Implemented a sequence-to-sequence framework using a CNN-Transformer encoder-decoder design.
* **Methodology:** Leveraged the YouCookII dataset with a custom preprocessing pipeline (uniform frame sampling, text vectorization, and teacher forcing).
* **Attention Mechanisms:** Incorporated multi-head self-attention and cross-attention mechanisms to align visual features with linguistic tokens.
* **Efficiency:** Designed a lightweight model that achieves state-of-the-art performance for its parameter size, optimized for environments with limited GPU memory (e.g., Google Colab).
* **Evaluation:** Conducted comprehensive quantitative and qualitative analysis, demonstrating statistically significant improvements over CNN-LSTM and 3DCNN-GRU baselines.

## 📊 Performance Comparison

The proposed Transformer model demonstrates superior performance across all standard captioning metrics:

| Model | BLEU-4 | METEOR | CIDEr | SPICE | Parameters (M) |
| --- | --- | --- | --- | --- | --- |
| **Proposed Transformer** | **22.1%** | **31.5%** | **48.2%** | **27.9%** | 3.07 |
| CNN-LSTM (Baseline 1) | 16.3% | 26.8% | 39.4% | 21.7% | 1.21 |
| 3DCNN-GRU (Baseline 2) | 14.6% | 24.1% | 35.8% | 19.3% | 1.82 |

## 🏗️ Architecture Design

* **Video Encoder:** Uses a lightweight CNN (TimeDistributed) to extract spatial features from 15 frames per clip, projected into a 256-dimensional embedding space with learnable positional encodings.
* **Caption Decoder:** An autoregressive Transformer decoder employing masked multi-head self-attention (causal generation) and cross-attention over encoder outputs to generate natural language captions.

## 🛠️ Getting Started

### Prerequisites

* Python 3.x
* TensorFlow 2.x / Keras
* OpenCV
* `yt-dlp` (for data acquisition)

### Setup

1. Clone this repository:
```bash
git clone [your-repo-link]

```


2. Ensure the YouCookII annotations are available.
3. Run the preprocessing pipeline to extract frames and tokenize captions as described in the report.
4. Train the model using the provided configuration (Adam optimizer, $1\times10^{-4}$ learning rate, batch size 32).

## 📝 Authors

* **Vaibhav Mahant** (Dept. of IT, NITK Surathkal)
* **Somesh Kharat** (Dept. of IT, NITK Surathkal)
* **Dr. Dinesh Naik** (Advisor, Dept. of IT, NITK Surathkal)

## 📖 Citation

If you find this work useful for your research, please refer to the project report included in this repository.
