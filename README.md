# Customer Review Intelligence using Traditional NLP + LLMs

An end-to-end Natural Language Processing project that transforms unstructured customer reviews into actionable business insights using **Traditional NLP, Semantic Embeddings, Clustering, LLM-based Classification, and Feature-Based Sentiment Analysis**.

The project compares traditional NLP techniques with modern LLM approaches to understand what each method can and cannot do effectively.

---

## 📌 Project Overview

Customer reviews contain valuable information about product quality, usability, compatibility, software experience, and customer satisfaction.

However, manually analyzing thousands of reviews is time-consuming and difficult to scale.

This project builds a customer review intelligence pipeline that answers questions such as:

- What are customers talking about?
- Can reviews be grouped into meaningful themes?
- What are the major customer concerns?
- Can an LLM classify reviews into business-defined categories?
- Does few-shot prompting actually improve classification?
- What product features are customers positive or negative about?
- How can these insights support business decisions?

The project uses reviews for the:

**Logitech Harmony Ultimate One 15-Device Universal Infrared Remote**

The selected dataset contains **1,604 customer reviews**.

---

# 🎯 Objectives

The main objectives of this project are to:

1. Understand and clean customer review data.
2. Build a Traditional NLP baseline using TF-IDF.
3. Perform unsupervised clustering using KMeans.
4. Compare lexical similarity with semantic similarity.
5. Use sentence embeddings for semantic clustering.
6. Use an LLM to profile and describe discovered clusters.
7. Compare zero-shot and few-shot LLM classification.
8. Extract product features and associated sentiment.
9. Evaluate model performance using classification metrics.
10. Translate NLP outputs into actionable business insights.

---

# 🏗️ Project Pipeline

```text
Customer Reviews
       │
       ▼
Data Understanding
       │
       ▼
Text Preprocessing
       │
       ├─────────────────────┐
       ▼                     ▼
   TF-IDF              Sentence Embeddings
       │                     │
       ▼                     ▼
    KMeans              Semantic KMeans
       │                     │
       │                     ▼
       │              Semantic Clusters
       │                     │
       │                     ▼
       │               LLM Profiling
       │
       ▼
Traditional NLP Baseline

              ┌──────────────────────────┐
              │                          │
              ▼                          ▼
       Zero-Shot LLM              Few-Shot LLM
              │                          │
              └────────────┬─────────────┘
                           ▼
                    Classification
                      Evaluation

                           │
                           ▼
                 Feature-Based Sentiment
                           │
                           ▼
                   Business Insights

📊 Dataset
The project uses the Datafiniti Amazon & Best Buy Electronics dataset available through Kaggle.
Dataset source:
Datafiniti – Amazon and Best Buy Electronics
The analysis focuses on:
Logitech 915-000224 Harmony Ultimate One 15-Device Universal Infrared Remote with Customizable Touch Screen Control - Black

🧹 1. Data Understanding & Text Preprocessing
The original customer review text is preserved separately from the cleaned representation.
Preprocessing steps
- Convert text to lowercase
- Remove URLs
- Replace punctuation with spaces
- Normalize whitespace
- Preserve apostrophes
- Preserve original review text

🔎 2. Traditional NLP: TF-IDF
TF-IDF was used as the traditional NLP baseline.
The objective was to represent reviews numerically based on the importance of words within the dataset.

KMeans Experiments
Different numbers of clusters were tested using silhouette score.

🧠 3. Semantic Embeddings
Sentence embeddings were generated using:
all-MiniLM-L6-v2

Each review was converted into a 384-dimensional semantic vector.

🤖 4. LLM-Based Cluster Profiling
After creating semantic clusters, representative reviews were passed to an LLM to interpret the discovered groups.
For each cluster, the LLM was asked to produce:
- Business-specific cluster name
- Cluster description
- One-sentence summary
- Positive patterns
- Negative patterns
- Business/customer interpretation
The prompt was designed to prevent the model from inventing information.

🏷️ 5. LLM Classification
The next stage converts business-defined review categories into a classification problem.
The project uses the following categories:
Setup and Programming
Touchscreen and Interface
Device Compatibility
Software and App
TV and Media Control
Design and Ergonomics
Battery and Charging
General Product Experience

Two approaches were compared:
Zero-Shot Classification
The LLM receives:
- Review
- Category definitions
and selects exactly one category.
Few-Shot Classification
The LLM receives:
- Review
- Available categories
- Examples of previously labelled reviews
The goal was to determine whether providing examples improves classification performance.

📈 6. Zero-Shot vs Few-Shot Evaluation
A labelled evaluation dataset was created for testing the classification approaches.
The evaluation uses:
- Accuracy
- Precision
- Recall
- F1-score
- Classification report

Results
Approach	Accuracy	Weighted F1
Zero-Shot	  ~33%	   ~0.33
Few-Shot	  ~21%   	 ~0.23

7. Feature-Based Sentiment Analysis
The final NLP task focuses on understanding what customers feel about specific product features.
Instead of assigning only one sentiment to the entire review, the system extracts:

📌 Project Takeaway
This project demonstrates how Traditional NLP, Machine Learning, Semantic Embeddings, and Large Language Models can work together rather than compete with each other.
A practical NLP system does not have to choose between:
Traditional ML
      OR
LLMs

Instead, the better question is:
Which technique is best suited to each part of the problem?

In this project:
- Traditional NLP provided the baseline.
- Embeddings improved semantic representation.
- Clustering discovered broad patterns.
- LLMs helped interpret clusters.
- Zero-shot and few-shot prompting enabled flexible classification.
- Feature-based sentiment converted reviews into actionable product insights.
- Evaluation helped determine what actually worked.
The main lesson is simple:
Use the simplest technique that solves the problem well — and use LLMs where they genuinely add value.

