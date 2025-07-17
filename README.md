# USAS-based Sentiment Analysis

This repository contains code and resources for performing **sentiment analysis using USAS semantic tags** across multiple languages, including **Chinese, Dutch, French, English, Spanish**, and more. The methodology leverages the **PyMUSAS rule-based taggers** and **spaCy pipelines** for multilingual semantic analysis and emotional tagging.


## 🔍 Overview

USAS (UCREL Semantic Analysis System) provides semantic tagging which can be extended for sentiment analysis by focusing on **emotion-related tags** (e.g., happiness, anger, bravery, fear). This repository shows how to:

- Tag text using the PyMUSAS rule-based taggers
- Extract emotion-related semantic tags
- Classify sentence- and text-level sentiment (positive, negative, neutral)
- Compute sentence-level and overall sentiment probabilities


## 📁 Languages Supported / 📄 Files

| Language     | Status | Notebook File       | Description                                                       |
|--------------|--------|---------------------|-------------------------------------------------------------------|
| Chinese      | ✅     | `Chinese.ipynb`     | Sentiment analysis in **Chinese** using PyMUSAS and spaCy         |
| Dutch        | ✅     | `Dutch.ipynb`       | Sentiment analysis in **Dutch** using PyMUSAS and spaCy           |
| French       | ✅     | `French.ipynb`      | Sentiment analysis in **French** using PyMUSAS and spaCy          |
| English      | ✅     | `English.ipynb`     | Sentiment analysis in **English** using PyMUSAS and spaCy         |
| Spanish      | ✅     | `Spanish.ipynb`     | Sentiment analysis in **Spanish** using PyMUSAS and spaCy         |
| Indonesian   | ⏳     | _coming soon_       | Sentiment analysis in **Indonesian** (in progress)                |
| Italian      | ⏳     | _coming soon_       | Sentiment analysis in **Italian** (in progress)                   |
| Portuguese   | ⏳     | _coming soon_       | Sentiment analysis in **Portuguese** (in progress)                |
| Welsh        | ⏳     | _coming soon_       | Sentiment analysis in **Welsh** (in progress)                     |


## 📦 Installation

Install the required dependencies using pip:

```bash
pip install https://github.com/UCREL/pymusas-models/releases/download/cmn_dual_upos2usas_contextual-0.3.3/cmn_dual_upos2usas_contextual-0.3.3-py3-none-any.whl
pip install colorama
python -m spacy download zh_core_web_sm
````


## 🚀 Getting Started

1. Clone the repository:

```bash
git clone https://github.com/4dpicture/usas-sentiment-analysis.git
cd usas-sentiment-analysis
```

2. Run the `Chinese.py` script in your preferred Python environment (Jupyter, Google Colab, or the terminal).

## 🔧 Main Functions

* `tag_text(text)`: Tags a Chinese input text with USAS semantic categories.
* `usas_emotion_tags(text)`: Extracts emotion-related USAS tags.
* `usas_sentiment_classifier(usas_emotion_tags)`: Classifies sentiment as positive, negative, or neutral at the sentence level.
* `sentence_sentiment_prob(usas_emotion_tags)`: Computes sentence-level sentiment probabilities.
* `text_sentiment_prob(text, pos, neg, neu)`: Computes text-level sentiment distribution.


## 🧪 Sample Use

Example input:

```text
你好，同志们，我想和你们分享我在手术后对抗癌症的经历……
```

Expected output:

* USAS tags for each token
* Emotion-tagged words
* Sentiment classification per sentence
* Probabilities for each sentiment class


## 📊 Sentiment Classes

The emotion tags used are based on the following USAS categories:

* E4.1+: Happy
* E4.1-: Sad
* E5+: Bravery
* E5-: Fear
* E6+: Confidence
* E6-: Worry
* …and others

![usas](images/usas_emotion_tags.png)


These are mapped to sentiment categories as follows:

| USAS Tag | Sentiment |
| -------- | --------- |
| `E*+`    | Positive  |
| `E*-`    | Negative  |
| `E*`     | Neutral   |


## 📚 References

* [UCREL Semantic Analysis System (USAS)](http://ucrel.lancs.ac.uk/usas/)
* [PyMUSAS](https://github.com/UCREL/pymusas)
* [spaCy](https://spacy.io)


## 🤝 Contributions

We welcome contributions for new languages, enhancements, or bug fixes! Feel free to submit a pull request or open an issue.
