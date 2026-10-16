# Multi-Class News Headline Classification

**Comparative Analysis of Classical Machine Learning and Deep Learning Models**

A CSE440 NLP project investigating automatic classification of news headlines into **Science & Technology, Business, Sports, and World News**. The study compares three preprocessing strategies, two text-representation approaches, and eight classifiers to determine which approach works best for short-text categorization.

## Key results

**Best model: TF-IDF + Logistic Regression** — **93.28%** test accuracy and **93.24%** macro F1-score, obtained from the project experiments and documented in the accompanying report.

| Model | Test accuracy | Macro F1 |
|---|---:|---:|
| TF-IDF + Logistic Regression | **93.28%** | **93.24%** |
| TF-IDF + DNN | 92.21% | 92.14% |
| Skip-gram + SimpleRNN | 88.03% | 87.94% |
| Skip-gram + GRU | 91.35% | 91.34% |
| Skip-gram + LSTM | 91.35% | 91.34% |
| Skip-gram + Bidirectional SimpleRNN | 87.37% | 87.39% |
| Skip-gram + Bidirectional GRU | 91.15% | 91.14% |
| Skip-gram + Bidirectional LSTM | 91.71% | 91.71% |

## Methodology

- **Exploratory analysis:** class distribution, headline length, word cloud, bigrams, and trigrams.
- **Preprocessing:** no preprocessing, extreme cleaning, and optimum/balanced cleaning.
- **Text features:** TF-IDF unigrams/bigrams and 100-dimensional Word2Vec Skip-gram embeddings.
- **Training:** Logistic Regression; deep feed-forward network; SimpleRNN, GRU, LSTM and their bidirectional variants.
- **Evaluation:** accuracy, precision, recall, macro F1-score, learning curves, and confusion matrices.

**Main finding:** balanced preprocessing combined with TF-IDF provided the strongest test results on this dataset; the more complex deep learning approaches did not exceed the Logistic Regression baseline.

## Repository contents

| File | Description |
|---|---|
| `News_Headline_Classification.ipynb` | Original experiment notebook with code and saved outputs; renamed for readability, no code or results rewritten |
| `Project_Report.pdf` | Full project methodology, results, analysis, and references |
| `requirements.txt` | Python libraries referenced by notebook |
| `.gitignore` | Excludes local caches, generated datasets, saved models and other large artifacts |

## Getting started (Google Colab recommended)

1. Open `News_Headline_Classification.ipynb` in Google Colab.
2. Obtain the **original datasets**, which are **not included** in this repository. Upload them to Colab as `/content/Training_data_3.xlsx` and `/content/Test_data.xlsx`, or adjust the notebook's paths.
3. Install the libraries listed in `requirements.txt` when necessary. The original notebook includes a `gensim` installation cell; a Colab environment may already have many other libraries installed.
4. Run the notebook **in order**. Some later cells also read intermediate files from `/content/`, such as `train_none.csv`, `train_extreme.csv`, `train_optimum.csv` and corresponding test CSVs. Generate these files in earlier notebook cells, then ensure they are saved at the paths expected by later cells (or change those paths). Prediction CSVs are also generated and reused later in the notebook.
5. Neural network training can be resource-intensive; using a Colab GPU runtime may help.

**Dataset & execution:** The experiments were conducted in Google Colab, and the resulting model performance is documented in the notebook outputs and project report. To run the notebook again, obtain the original Excel datasets and update the file paths as needed for your environment.

## Technologies

Python, Jupyter/Google Colab, pandas, NumPy, scikit-learn, TensorFlow/Keras, Gensim, NLTK, Matplotlib, Seaborn, and WordCloud.

## Report

See [Project_Report.pdf](Project_Report.pdf) for full methodology and experiment results.
