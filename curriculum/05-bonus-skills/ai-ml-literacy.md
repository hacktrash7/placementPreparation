# AI / ML Literacy (Not Deep ML)

In 2025-26, "AI/ML aware" is a buzz-phrase recruiters explicitly look for. You **don't** need to be an ML engineer. You need to:

1. Know the vocabulary (supervised vs unsupervised, classification vs regression, overfitting, etc.).
2. Have built **one tiny ML project** (e.g., predict house prices with scikit-learn — 80 lines of Python).
3. Be able to talk about LLMs / generative AI at a conceptual level for HR rounds.

3-4 weeks of evenings.

## Concepts to know (interview vocabulary)

### Core AI/ML

- **AI** — broader, any "smart" behaviour by machines.
- **Machine Learning (ML)** — algorithms that learn from data.
- **Deep Learning (DL)** — ML using neural networks with many layers.
- **Supervised learning** — model learns from labelled examples (input → output). Examples: regression, classification.
- **Unsupervised learning** — finds structure in unlabelled data. Examples: clustering, dimensionality reduction.
- **Reinforcement learning** — agent learns by trial + reward.

### Tasks

- **Regression** — predict a continuous number (house price).
- **Classification** — predict a category (spam / not spam).
- **Clustering** — group similar items (k-means).
- **Recommendation** — suggest items (collaborative filtering).
- **NLP** — text understanding (sentiment, translation, summarisation).
- **Computer Vision** — image tasks (classification, detection, segmentation).

### Pipeline (memorise this!)

```
Problem → Data collection → Cleaning → Feature engineering →
Train/Test split → Model selection → Training → Evaluation →
Tuning → Deployment → Monitoring
```

### Algorithms (1-line each)

- **Linear Regression** — fit straight line minimising squared error.
- **Logistic Regression** — classification via sigmoid output.
- **Decision Tree** — series of if/else splits.
- **Random Forest** — ensemble of many trees.
- **SVM** — find the hyperplane maximising margin between classes.
- **K-Nearest Neighbours** — classify by majority of k closest training points.
- **K-Means** — group data into k clusters by closest centroid.
- **Naive Bayes** — Bayes' theorem with feature-independence assumption.
- **Gradient Boosting / XGBoost** — boosted trees, very strong on tabular data.
- **Neural Network** — layers of nodes with weights; learned via backprop.

### Pitfalls

- **Overfitting** — model memorises training data, fails on new data. Fix: more data, regularisation, cross-validation, simpler model.
- **Underfitting** — model too simple to capture patterns.
- **Bias-variance tradeoff** — simpler models = high bias / low variance; complex = low bias / high variance.
- **Data leakage** — info from test set sneaks into training (causes inflated metrics).

### Metrics

- Regression: MAE, MSE, RMSE, R².
- Classification: Accuracy, Precision, Recall, F1, ROC-AUC.
- **Confusion matrix**: TP, TN, FP, FN — know what each means.

### Generative AI / LLM vocabulary

- **LLM** (Large Language Model) — neural net trained on huge text to predict next token.
- **Transformer** — the architecture (attention mechanism).
- **Prompt** — input given to an LLM.
- **Tokenisation** — splitting text into tokens (sub-words).
- **Fine-tuning** — training a base LLM further on your data.
- **RAG** (Retrieval-Augmented Generation) — fetch relevant docs and pass them with the prompt.
- **Embeddings** — vector representation of text/data.
- **Hallucination** — when an LLM confidently outputs incorrect info.

## Hands-on mini-projects (pick one)

### Project A — Titanic Survival (classification)

- Dataset: Kaggle's free Titanic CSV (already known to interviewers).
- Tools: Python, pandas, scikit-learn.
- Steps:
  1. Load CSV, explore with `df.head()`, `df.info()`.
  2. Clean: fill missing Age, drop Cabin, encode Sex/Embarked.
  3. Split into train/test (`train_test_split`).
  4. Try Logistic Regression and Random Forest.
  5. Print accuracy + confusion matrix.

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, confusion_matrix

df = pd.read_csv("train.csv")
df["Age"] = df["Age"].fillna(df["Age"].median())
df["Sex"] = df["Sex"].map({"male": 0, "female": 1})
df = df.dropna(subset=["Embarked"])
df["Embarked"] = df["Embarked"].map({"C": 0, "Q": 1, "S": 2})

X = df[["Pclass", "Sex", "Age", "SibSp", "Parch", "Fare", "Embarked"]]
y = df["Survived"]

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = RandomForestClassifier(n_estimators=100, random_state=42)
model.fit(X_train, y_train)
pred = model.predict(X_test)

print("Accuracy:", accuracy_score(y_test, pred))
print(confusion_matrix(y_test, pred))
```

### Project B — House Price Prediction (regression)

Use Kaggle's "House Prices" or sklearn's California housing dataset. Same pipeline, regression metrics.

### Project C — Sentiment Analyser (NLP)

- Dataset: IMDB reviews / Twitter sentiment.
- Pipeline: TF-IDF → Logistic Regression OR use Hugging Face Transformers (`pipeline("sentiment-analysis")`).

### Project D — Chat-with-PDF (Generative AI / RAG)

For students excited about LLMs:
- Use `langchain` or `llama-index` + a free embedding model (e.g., `sentence-transformers/all-MiniLM-L6-v2`).
- Index a PDF, allow Q&A via an LLM (Ollama running locally, or HuggingFace Inference API free tier, or OpenAI free credits).
- Wrap with a simple Streamlit UI.

Resume bullet:
```
PDF-Chat Bot — Local LLM-powered Q&A app over user PDFs using
LangChain + sentence-transformers embeddings + ChromaDB.
Built with Streamlit. github.com/<you>/pdf-chat
```

## Resources (free)

- **Andrew Ng's "Machine Learning Specialization"** (Coursera, audit free).
- **freeCodeCamp** — "Machine Learning with Python" + "Scikit-learn full course" on YouTube.
- **Kaggle Learn** — short, hands-on micro-courses.
- **3Blue1Brown** YouTube — *Neural Networks* visual series.
- **Hugging Face Course** — for transformers/LLM understanding.

## Resume bullet examples

```
Machine Learning  — Built classification model on Titanic dataset
                    (scikit-learn Logistic Regression + Random Forest;
                    81% accuracy). Comfortable with pandas, train/test
                    split, confusion matrix, basic ML metrics.

Generative AI     — Built a PDF Q&A bot using LangChain + a local LLM
                    (Llama 3 via Ollama) and ChromaDB embeddings.
```

## What HR questions on AI to expect

- "Tell me one thing you find exciting about AI/ML."
- "What's the difference between AI, ML, and Deep Learning?"
- "Have you used ChatGPT or any LLM? For what?"
- "Do you think AI will replace jobs in IT services?"
  *(Suggested answer: AI changes the nature of work; service IT will use it to deliver faster — engineers who can use AI tools will gain, not lose, jobs.)*

Keep your answers practical and grounded — don't oversell yourself as an "AI engineer".
