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
| **Accuracy** | 86.75% |
| **Macro F1-Score** | 0.85 |
| **Precision (Weighted)** | 0.87 |
| **Recall (Weighted)** | 0.87 |

### Per-Class Performance

| Sentiment | Precision | Recall | F1-Score |
|-----------|-----------|--------|----------|
| Negatif | 0.86 | 0.91 | 0.89 |
| Netral | 0.82 | 0.74 | 0.78 |
| Positif | 0.90 | 0.90 | 0.90 |

## 🎯 Features

- ✅ **Fine-tuned IndoBERT Base** - Leverages pre-trained Indonesian language model
- ✅ **Automated Labeling** - Uses zero-shot labeling pipeline for efficient annotation
- ✅ **Class Imbalance Handling** - Weighted loss function for balanced learning
- ✅ **CNBC Indonesia Dataset** - Real-world financial news articles about IHSG
- ✅ **Hugging Face Integration** - Built with Transformers library for easy deployment

## 📁 Dataset

- **Source**: CNBC Indonesia news articles about IHSG
- **Kaggle**: [Dataset Berita IHSG CNBC untuk Text Mining](https://www.kaggle.com/datasets/imuhbayu/dataset-berita-ihsg-cnbc-untuk-text-mining)
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
git clone https://github.com/Muktiprab007/ihsg-news-sentiment-indobert.git
cd ihsg-news-sentiment-indobert

# Install dependencies
pip install -r requirements.txt
```

### Usage

```python
from transformers import pipeline

# Load fine-tuned model
model_path = "./indobert_finetuned_ihsg"
sentiment_pipeline = pipeline("sentiment-analysis", model=model_path)

# Predict sentiment
news_title = "IHSG ambruk 8% karena investor asing cabut"
result = sentiment_pipeline(news_title)[0]

print(f"Text: {news_title}")
print(f"Sentiment: {result['label']}")
print(f"Confidence: {result['score']:.4f}")
```

### Training

```bash
# Run the Jupyter notebook
jupyter notebook ihsg-news-sentiment-indobert.ipynb
```

## 🏗️ Model Architecture

```
IndoBERT Base (110M parameters)
├── Embedding Layer (128-dim)
├── 12 Transformer Layers
├── 12 Attention Heads
├── Dropout (0.1)
└── Classification Head (3 classes)
```

## 📈 Training Details

| Hyperparameter | Value |
|----------------|-------|
| Base Model | indobenchmark/indobert-base-p1 |
| Learning Rate | 2e-5 |
| Batch Size | 8 |
| Epochs | 10 (with early stopping) |
| Optimizer | AdamW |
| Loss Function | Weighted CrossEntropy |
| Max Sequence Length | 128 |
| Warmup Steps | 50 |
| Weight Decay | 0.01 |

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat&logo=huggingface&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)

## 📂 Project Structure

```
ihsg-news-sentiment-indobert/
├── .gitattributes
├── README.md
├── requirements.txt
├── cnbc_ihsg_articles_clean.csv          # Dataset
├── ihsg-news-sentiment-indobert.ipynb    # Main notebook
└── indobert_finetuned_ihsg/              # Saved model
    ├── config.json
    ├── pytorch_model.bin
    ├── tokenizer_config.json
    ├── vocab.txt
    └── label_encoder.pkl
```

## 📊 Results Visualization

### Confusion Matrix

```
[[32  2  1]   # Negatif
 [ 3 14  2]   # Netral
 [ 2  1 26]]  # Positif
```

## 🔄 Future Improvements

- [ ] Collect more data (target 2000+ samples)
- [ ] Experiment with IndoBERT Large (335M parameters)
- [ ] Add aspect-based sentiment analysis
- [ ] Deploy as REST API with FastAPI
- [ ] Real-time news monitoring pipeline
- [ ] Integration with IHSG price movement prediction

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.

## 🙏 Acknowledgments

- [IndoBERT](https://github.com/indobenchmark/indobert) - Pre-trained model
- [Hugging Face](https://huggingface.co/) - Transformers library
- [CNBC Indonesia](https://www.cnbcindonesia.com/) - News source
- [Kaggle Dataset](https://www.kaggle.com/datasets/imuhbayu/dataset-berita-ihsg-cnbc-untuk-text-mining) - Dataset source

## 📧 Contact

Project Link: [https://github.com/Muktiprab007/ihsg-news-sentiment-indobert](https://github.com/Muktiprab007/ihsg-news-sentiment-indobert)

---

## requirements.txt

```txt
torch>=2.0.0
transformers>=4.30.0
datasets>=2.12.0
accelerate>=0.20.0
pandas>=1.5.0
numpy>=1.24.0
scikit-learn>=1.2.0
matplotlib>=3.7.0
seaborn>=0.12.0
jupyter>=1.0.0
ipykernel>=6.0.0
```
