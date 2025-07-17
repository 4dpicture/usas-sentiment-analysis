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

### 📝 Example Input

```text
Hello everyone, I want to share my journey after surgery and my battle with cancer. I was diagnosed with colon cancer in May 2020 and had to undergo emergency surgery. The recovery was tough, but I stayed strong for my family. After months of treatment, I was declared cancer-free. Unfortunately, the cancer returned and spread to my liver. Despite the setbacks, I continued treatment and remained hopeful. I am now in remission again and grateful for each day.
````

### ✅ Expected Output

* **USAS tags for each token**
  Each word or token is semantically tagged with USAS categories.
  Example:

  * `Hello` → `Z1` (Personal Names)
  * `battle` → `X8+` (Hostility/Violence)
  * `hopeful` → `E6+` (Confidence)

* **Emotion-tagged words using USAS emotion categories**
  Words expressing emotion are tagged with categories like:

  * `E4.1+` → Happiness
  * `E4.1-` → Sadness
  * `E5+` → Bravery
  * `E5-` → Fear
    Example:
  * `hopeful` → `E6+`
  * `grateful` → `E4.2+`

* **Sentiment classification per sentence**
  Each sentence is classified based on the dominant emotional tone:

  * Sentence 1 → Neutral
  * Sentence 2 → Negative
  * Sentence 3 → Positive
  * Sentence 4 → Positive

* **Sentence-level sentiment probabilities**
  Probability scores for each class (positive, negative, neutral) per sentence.
  Example:

  * Sentence 3: `positive = 0.67, negative = 0.0, neutral = 0.33`

* **Text-level sentiment distribution**
  Overall sentiment summary for the entire text based on aggregated sentence scores.
  Example:

  * `positive = 0.50, negative = 0.25, neutral = 0.25`


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
