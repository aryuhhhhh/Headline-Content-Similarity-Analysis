# 📰 Headline-Content-Similarity-Analysis

An NLP project analyzing Indian news articles to detect potential clickbait or misleading headlines by quantifying the **semantic similarity** between the article title and its body content.

The analysis employs **Sentence Embeddings** (using a pre-trained transformer model) and **Cosine Similarity** to generate a single metric that flags poorly summarized or deceptive content.

## ✨ Features

* **Semantic Similarity Score:** Calculates a cosine similarity score (0.0 to 1.0) for 926 Indian news articles.
* **Clickbait Detection:** Identifies articles where the headline poorly represents the body content (low similarity score).
* **Clustering:** Groups low-similarity articles using **K-Means clustering** to identify common themes or patterns in potential clickbait.
* **Interactive Dashboard:** A Streamlit application for visualizing results and testing new headlines.

## 🛠️ Technology Stack

* **Language:** Python
* **Libraries:** `pandas`, `numpy`, `scikit-learn`, `SentenceTransformers` (for embeddings), `streamlit` (for the dashboard).
* **Model:** `all-MiniLM-L6-v2` (for generating embeddings).

## 🚀 How to Run the Dashboard

To run the interactive analysis dashboard locally:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YourUsername/Headline-Content-Similarity-Analysis.git](https://github.com/YourUsername/Headline-Content-Similarity-Analysis.git)
    cd Headline-Content-Similarity-Analysis
    ```

2.  **Install dependencies:**
    *(The full list of packages is in the `requirements.txt` file.)*
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Streamlit application:**
    ```bash
    streamlit run app/app.py
    ```
    This will open the dashboard in your web browser. Upload the `data/news_similarity_results.csv` file when prompted to see the results of the analysis.

## 📊 Key Results (Example)

| Metric | Value |
| :--- | :--- |
| **Total Articles Analyzed** | 926 |
| **Average Similarity** | 0.575 |
| **Lowest Similarity Score** | -0.109 |
| **Clickbait Candidates (Similarity < 0.45)** | 240 |

### Top 3 Lowest-Scoring Headlines

*(This section confirms the analysis successfully flags deceptive or generalist titles.)*

1.  `maharashtra sec asks eci to delay voter roll revision until after local body elections` (Score: **-0.109**): **Content was an unrelated stock market snippet.**
2.  `letters to editor` (Score: **-0.070**): **Content was an editorial piece on US-China tariffs.**
3.  `erin downgraded to formidable category 4 hurricane, nhc says` (Score: **-0.069**): **Content was an unrelated tech/business snippet.**

***

## 💡 Next Steps

* Explore clustering visualization to understand different "types" of low-similarity articles.
* Experiment with other pre-trained transformer models (e.g., larger ones) to see how the similarity scores change.
* Build a labeled dataset to train a supervised machine learning classifier (like logistic regression or a neural network) for binary (clickbait/not clickbait) prediction.
