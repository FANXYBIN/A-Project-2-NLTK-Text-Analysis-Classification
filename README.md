### A-Project 2: NLTK Text Analysis & Classification — *Alice in Wonderland*
<details>
<summary>🧠 Click to view project details</summary>

This project used **Natural Language Toolkit (NLTK)** to perform comprehensive text analysis and a classification experiment based on *Alice’s Adventures in Wonderland* by Lewis Carroll.  
The objective was to reproduce the official NLTK tutorial steps on tokenization, lemmatization, and part-of-speech tagging — and extend it with a **custom text classification** task using sections of the novel as data.

* **Dataset:** *Alice’s Adventures in Wonderland* (from Project Gutenberg).  
* **Tools:** Python, NLTK, scikit-learn, matplotlib, wordcloud.  
* **Techniques:** Tokenization, stopword removal, lemmatization, POS tagging, TF–IDF vectorization, text classification.  
* **Goal:** Explore linguistic structure and build a classifier to distinguish between different sections/chapters of the novel.

---

### ⚙️ Text Preprocessing
1. **Load text:** Imported directly from NLTK’s Gutenberg corpus (`nltk.corpus.gutenberg.raw('carroll-alice.txt')`).  
2. **Tokenization:** `nltk.word_tokenize()` split the text into ~27k tokens.  
3. **Stopword removal:** Filtered using `nltk.corpus.stopwords.words('english')`.  
4. **Lemmatization:** Used `WordNetLemmatizer()` to unify word forms.  
5. **POS Tagging:** Tagged tokens to examine patterns (e.g., high frequency of nouns, proper nouns, and verbs of speech).  

<div align="center">
  <img src="images/alice_wordcloud.png" alt="Word Cloud of Alice in Wonderland" width="500"/>
  <p><em>Word cloud showing dominant terms and character mentions.</em></p>
</div>

---

### 🧪 Classification Experiment
The classification task divided the novel into **10 equal sections** and trained a model to identify which section a given text snippet came from.

**Steps:**
- Converted each text section into TF–IDF features using `TfidfVectorizer()`.  
- Split data into train/test sets using `train_test_split(test_size=0.2)`.  
- Trained multiple models:
  - Multinomial Naive Bayes  
  - Logistic Regression  
  - Linear SVM  

**Best model:** Linear SVM (C=1.0, linear kernel)  
**Accuracy:** ~89% on held-out test data  
**Key features:** Section-level differences in dialogue frequency, character mentions (“Alice,” “Queen,” “Hatter”), and emotional verbs.

<div align="center">
  <img src="images/alice_confusion_matrix.png" alt="Confusion Matrix for Section Classification" width="550"/>
  <p><em>Confusion matrix showing strong classification accuracy across sections.</em></p>
</div>

---

### 📊 Text Insights
- The most common nouns include “Alice,” “Queen,” “time,” and “King.”  
- Verbs of motion (“run,” “go,” “come”) and speech (“said,” “replied”) dominate the narrative.  
- Distinct vocabulary patterns distinguish dialogue-heavy and descriptive chapters.  
- Classification demonstrates measurable stylistic variation across the story’s structure.

<div align="center">
  <img src="images/alice_pos_distribution.png" alt="POS Distribution in Alice in Wonderland" width="550"/>
  <p><em>Distribution of parts of speech across the text, highlighting heavy noun–verb usage.</em></p>
</div>

---

### 🧠 Skills Demonstrated
- NLTK-based text preprocessing and POS analysis  
- TF–IDF vectorization and feature engineering  
- Text classification and model evaluation  
- Visualization of linguistic patterns (word clouds, POS histograms)

📓 [View Jupyter Notebook](notebooks/EAI6000_Module_6.ipynb)

</details>
