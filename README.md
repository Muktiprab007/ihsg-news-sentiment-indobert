# IHSG News Sentiment Analysis with IndoBERT

[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Transformers](https://img.shields.io/badge/🤗-Transformers-yellow.svg)](https://huggingface.co/docs/transformers/index)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)](https://pytorch.org/)
[![HuggingFace](https://img.shields.io/badge/🤗-HuggingFace-FFD21E.svg)](https://huggingface.co/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Code style](https://img.shields.io/badge/Code%20style-black-000000.svg)](https://github.com/psf/black)
[![Made with Jupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=flat&logo=Jupyter)](https://jupyter.org/try)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)

Fine-tuning **IndoBERT** for sentiment classification of Indonesian stock market (IHSG) news articles from CNBC Indonesia.

## 📊 Model Performance

| Metric | Score |
|--------|-------|
| **Accuracy** | 84% |
| **Macro F1-Score** | 0.83 |
| **Precision (Weighted)** | 0.84 |
| **Recall (Weighted)** | 0.84 |

### Per-Class Performance

| Sentiment | Precision | Recall | F1-Score |
|-----------|-----------|--------|----------|
| Negatif | 0.85 | 0.88 | 0.86 |
| Netral | 0.78 | 0.72 | 0.75 |
| Positif | 0.86 | 0.87 | 0.86 |

## 🎯 Features

- ✅ **Fine-tuned IndoBERT Base** - Leverages pre-trained Indonesian language model
- ✅ **Automated Labeling** - Uses zero-shot labeling pipeline for efficient annotation
- ✅ **Class Imbalance Handling** - Weighted loss function for balanced learning
- ✅ **CNBC Indonesia Dataset** - Real-world financial news articles about IHSG
- ✅ **Hugging Face Integration** - Built with Transformers library for easy deployment

## 📁 Dataset

- **Source**: CNBC Indonesia news articles about IHSG
- **Samples**: 550 labeled articles
- **Classes**: 3 (Negatif, Netral, Positif)
- **Distribution**:
  - Negatif: 41.6%
  - Positif: 34.5%
  - Netral: 23.8%

## 🚀 Quick Start

### Installation

```bash
# Clone repository
git clone https://github.com/yourusername/ihsg-news-sentiment-indobert.git
cd ihsg-news-sentiment-indobert

# Install dependencies
pip install -r requirements.txt
