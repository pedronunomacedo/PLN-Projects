# Sentiment Analysis of Financial News

## Overview
This project aims to perform sentiment analysis on financial news articles using various machine learning techniques. The dataset utilized for this task is the "Sentiment Analysis - Labelled Financial News Data from Economic Times," accessible on [Kaggle](https://www.kaggle.com/datasets/aravsood7/sentiment-analysis-labelled-financial-news-data). It comprises annotated financial news articles categorized with sentiment polarity (positive, negative).

## Base of the Project: project_base.ipynb
The project started with a base notebook [project_base.ipynb](project_base.ipynb) focusing on a fundamental sparse vector encoding approach using TF-IDF bigram representations. A hyperparameter-tuned pipeline was employed to train a classifier for text sentiment analysis. Three general-purpose lexicons (VADER, AFINN, SentiWordNet), along with a specific one, [Loughran-McDonald Master Dictionary](https://sraf.nd.edu/loughranmcdonald-master-dictionary/), tailored for binary sentiment classification (on [prepare_lexicon.ipynb](data/prepare_lexicon.ipynb)), were utilized. Predictions from these lexicons were incorporated as features, enhancing the overall performance of the classifiers.

## Data Preprocessing
Data preprocessing steps, including cleaning and exploration, are detailed in the [data_understanding.ipynb](data_understanding.ipynb) notebook. Techniques such as removing special characters, punctuation, and stopwords were applied. Additionally, the distribution of sentiment labels was analyzed to identify potential class imbalances.

## Classification Models
The project explored both sparse embeddings (TF-IDF vectorizers) and dense vectors for sentiment analysis. The approaches included:
1. **Sparse Embeddings (TF-IDF Vectorizers):** Transforming text data into TF-IDF vectors and using them as features for classification.
2. **Dense Vectors:**
   - **Word2Vec:** Utilizing Word2Vec embeddings to capture semantic relationships between words.
   - **Pretrained Embeddings:**
     - **Bankfin:** Trained WordVectors with 100 dimensions (21 Mb).
     - **Fintext:** Pre-Trained (still trainable) model with 300 dimensions (5.6 Gb).

## Additional Experiments
Several additional experiments were conducted to delve deeper into different aspects of the data and models:
- **Segment-Level Analysis:** Investigating individual segments such as headlines, synopses, and full texts to assess their impact on classification performance. for eavery single field (header, synopsis, full_text), a respective notebook ([headlines_only.ipynb](headlines_only.ipynb), [synopsis_only.ipynb](synopsis_only.ipynb) and [fulltext_only.ipynb](fulltext_only.ipynb)) was created to verify performance.
- **Error Analysis:** Identifying common sources of misclassification and potential areas for model improvement.
- **Hyperparameter Tuning:** Optimizing the performance of the classification models through hyperparameter tuning.
- **Pipeline Modeling:** Exploring different models using a pipeline approach to streamline training and evaluation.
- **Lexicon Integration:** Incorporating lexicons such as SentiWordNet, AFINN, and VADER to enhance model training with extra features.

