
# 📘 Social Media Depression Analysis  
Detecting depressive sentiments in social media posts using NLP and deep learning.

---

## 🧠 Overview  
This project leverages natural language processing and deep learning models to detect signs of **depression** in user-generated content from **Twitter** and **Facebook**. The objective is to classify posts as either **“normal”** or **“depressive”** based on sentiment and keyword patterns.

---

## 💡 Motivation  
With over 230 million active users, Twitter and Facebook serve as digital mirrors of human emotion. By analyzing public posts, we can identify potential indicators of mental health risks and contribute to scalable, data-driven mental health monitoring systems.

---

## 📂 Dataset  
Combined from three sources:  
- **Sentiment140**: 8,000 sampled tweets from a 1.6M dataset  
- **Twitter Scraping (Twint)**: 2,345 tweets with depression-related keywords  
- **Facebook Scraping**: ~15,000 posts scraped using `facebook_scraper`

👉 **Final Dataset Size**: 25,858 records  
👉 **Labels**:  
- `0` = Normal  
- `1` = Depressive

---

## ⚙️ Preprocessing  
- Removed noise: stopwords, punctuation, contractions  
- Tokenized text for model input  
- Generated **word clouds** for depressive vs. non-depressive posts  
- Dataset split: 80% training / 20% testing

---

## 🧪 Training Setup

| Hyperparameter       | Value         |
|----------------------|---------------|
| Vocabulary Size      | 18,611        |
| Max Sequence Length  | 33            |
| Embedding Dimension  | 66            |
| Training Set Size    | 5,000 samples |

---

## 🧠 Models Trained

### 🔹 LSTM Model  
- Architecture: Embedding → LSTM → Dense  
- Accuracy: **0.79**  
- Total Parameters: **1.29M**

---

### 🔹 Simple RNN  
- Architecture: Embedding → SimpleRNN → Dense  
- Accuracy: **0.78**  
- Total Parameters: **1.24M**

---

### 🔹 BiLSTM  
- Architecture: Embedding → Bidirectional LSTM → Dense  
- Accuracy: **0.78**  
- Total Parameters: **1.36M**

---

### 🔹 BERT (Transformer-Based)  
- Pre-trained: `distilbert-base-nli-mean-tokens` from Sentence Transformers  
- Architecture: BERT embeddings → Dense(256) → Dense(1)  
- Accuracy: **0.95** *(Best Performer)*

---

## 📊 Performance Summary

| Model  | Accuracy | F1 Score | Precision | Recall |
|--------|----------|----------|-----------|--------|
| LSTM   | 0.79     | 0.79     | 0.79      | 0.79   |
| RNN    | 0.78     | 0.78     | 0.78      | 0.78   |
| BiLSTM | 0.78     | 0.78     | 0.78      | 0.78   |
| BERT   | 0.95     | 0.95     | 0.95      | 0.95   |

---

## 🚀 Usage

To run this project locally:

### 1. Clone the repository
```bash
git clone https://github.com/your-username/social-media-depression-analysis.git
cd social-media-depression-analysis
````

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook
```

### 4. Required libraries

* `tensorflow`
* `sentence_transformers`
* `twint`
* `facebook_scraper`
* `nltk`, `sklearn`, `matplotlib`, `seaborn`

---

## 📄 License

This project is licensed under the **MIT License**.
Feel free to use, modify, and distribute with proper attribution.

---

## 🙌 Contributions

Contributions, feedback, and suggestions are welcome!
Please feel free to open an issue or submit a pull request.

---


