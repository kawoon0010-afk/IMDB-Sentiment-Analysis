# IMDB Sentiment Analysis

## Project Overview

This project is an improved version of my original BSc Artificial Intelligence assignment, **Sentiment Analysis of Movie Reviews**. Both versions use the IMDB movie review dataset to explore sentiment classification with Natural Language Processing (NLP) and machine learning.

**[View my original university project report on Dropbox](https://www.dropbox.com/scl/fi/dmlmftbe92c74jg89nljt/Sentiment-analysis-movie-reviews-assessment.pdf?rlkey=ya0k667h533lpyv0vop5k9uxx&st=8sy3pw7n&dl=0)**



## Original Project vs Improved Version

| Area | Original Project | Improved Version |
|---|---|---|
| Dataset | IMDB movie reviews | Same dataset |
| Tokenization | Custom tokenization and NLTK `word_tokenize()` | Simple splitting and NLTK `TreebankWordTokenizer()` |
| Classification | Naïve Bayes and SVM | `MultinomialNB` and `LinearSVC` |
| TF-IDF | Fitted before train/test splitting in some original code | Fitted on training data only to avoid data leakage |
| Evaluation | Some results evaluated on training data | Consistent held-out test evaluation |
| ROC analysis | Some curves based on class predictions or training data | ROC AUC based on model scores on held-out test data |
| Organisation | Four separate notebooks | Consolidated research notebook |

## Key Improvements

1. **Reduced data leakage:** Split the data before fitting TF-IDF, so test documents do not influence vocabulary or IDF weights.
2. **More consistent evaluation:** Compare models on the same held-out test set using accuracy, F1 score and ROC AUC.
3. **Linear SVM:** Use `LinearSVC` for efficient classification of high-dimensional text features.
4. **Reproducibility:** Present the approaches and evaluation together in a single notebook.

## Results

The improved models were evaluated on **10,000 held-out reviews**.

| Tokenizer | Model | Test accuracy | F1 score | ROC AUC |
|---|---|---:|---:|---:|
| Simple split | LinearSVC | **88.97%** | **0.8904** | **0.9576** |
| NLTK Treebank | LinearSVC | 88.96% | 0.8903 | 0.9575 |
| Simple split | MultinomialNB | 85.45% | 0.8550 | 0.9282 |
| NLTK Treebank | MultinomialNB | 85.41% | 0.8546 | 0.9281 |

### Brief Discussion

`LinearSVC` achieved the highest test accuracy (88.97%), around **3.5 percentage points** above `MultinomialNB`. The two tokenizers gave nearly identical results under the tested settings. The original report recorded a maximum accuracy of 89.655%, but that figure is **not directly comparable** with the improved pipeline because preprocessing and evaluation differ.

## Conclusion

This portfolio demonstrates Python-based text preprocessing, TF-IDF feature extraction, machine learning classification, and held-out evaluation. These skills may also be applied to financial documents, including ESG disclosures, with suitable domain-specific data and labels.

## Original Project

**Dropbox link:** [Open original project files](https://www.dropbox.com/scl/fo/rn4p5ojbvnrx0fyltwrap/AENvYcMHKfBUCGVfS4Tb47U?rlkey=lv5ca8te8ha7gvq4r9whglau9&st=7jz865t1&dl=0)

The original university report and four notebooks can be accessed through this link once it is replaced with the actual shared Dropbox URL.
