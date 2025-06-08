# Sentiment-analysis-with-hyper-parameter-tunning-and-model-evaluation-with-Xai

This project performs **Sentiment Analysis** on movie reviews using IMDb's large-scale dataset. It applies machine learning and NLP techniques to classify reviews as **positive** or **negative**, along with explainability (XAI) tools to interpret model decisions.

---

## 📌 Objective

- Convert IMDb ratings (1–10 scale) into binary sentiment classes:
  - **1–4** → Negative
  - **7–10** → Positive
- Build models to classify text-based reviews into **positive** or **negative**
- Address challenges like **sarcasm**, **negation**, and **mixed sentiments**
- Use Explainable AI (XAI) to understand and interpret the model’s predictions

---

## 📊 Dataset Overview

- 📁 Source: [Kaggle IMDb Dataset](https://www.kaggle.com/datasets/crisbam/imdb-dataset-of-65k-movie-reviews-and-translation)
- 🔢 Size: 149,780 reviews
- 🎬 Columns:
  - `Review`: Text review
  - `Rating`: Numerical score (1–10)
  - `Movie`: Name of the movie
  - `Resenhas`: Portuguese review (dropped)

---

## 🧹 Data Preprocessing

- **Expanded contractions** (e.g., can't → cannot)
- **Removed URLs**, **special characters**, and **irrelevant stopwords**
- **Retained negation words** like “not” to preserve sentiment context
- Created a `Review_clean` column for processed text

---

## 📈 Exploratory Data Analysis (EDA)

- Verified class balance (equal reviews per rating)
- Plotted word clouds by sentiment
- Analyzed review length, word density, and average word length
- N-gram analysis (uni-, bi-, and trigrams) showed key sentiment patterns

---

## 🛠️ Feature Engineering

- Used `CountVectorizer` and `TF-IDF` for text-to-vector conversion
- Focused on **unigrams**, **bigrams**, and **trigrams**
- Applied **chi-squared** test for feature selection
- Found TF-IDF more effective in separating sentiment

---

## 🤖 Model Building & Evaluation

### Models Used:
- Logistic Regression ✅ (Best performer)
- Decision Tree (Overfit)
- Random Forest (Some overfitting)

### Metrics:
- Precision
- F1-score
- AUC-ROC

### Best Model (Logistic Regression):
- **Precision:** 0.8955 (test)
- **F1 Score:** 0.8955
- **AUC:** 0.9606
- Fine-tuned using `GridSearchCV`

---

## 🌐 Explainable AI (XAI)

> *(From `Phase 4.ipynb`)*

- Used **LIME (Local Interpretable Model-Agnostic Explanations)** to interpret why the model predicted a particular sentiment.
- Visualized top influential words in prediction decisions.
- Example: A negative review where “boring”, “waste”, and “predictable” were flagged as key contributors.

---

## 🚧 Challenges Faced

- **Sarcasm:** e.g., “Sure, best movie ever... I slept halfway.”
- **Mixed polarity:** Some reviews contained both praise and criticism.
- **Negation Handling:** “Not bad” ≠ “bad”

---

## 📌 Future Work

- Introduce **deep learning models** like LSTM or BERT
- Implement **sarcasm detection modules**
- Apply **domain adaptation** for different datasets (e.g., product reviews)

---

## 👥 Contributors

- Nikhil Gupta
  
---

## 📄 License

This project is academic in nature, submitted as part of the Data Mining course at CSBS, under the guidance of Dr. Jatin Bedi.

---


