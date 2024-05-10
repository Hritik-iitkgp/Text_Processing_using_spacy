# Project: Quora Retrieval System

This project implements a retrieval system for Quora, aiming to find the most similar existing questions (documents) in the Quora database for a given new question (query). The system leverages advanced text processing techniques and evaluation metrics to deliver accurate and efficient recommendations.

## Data:

Dataset: 'Query_Doc' containing three CSV files:
'query': 100 query IDs and texts.
'docs': 10,000 document IDs and texts.
'qdrel': 130 query and document ID pairs representing similar questions.
Source: QueryDoc
Tasks:

## 1. Data Preprocessing:

Cleaning: Removal of non-alphanumeric characters and whitespaces from documents and queries.
Spelling Correction: Utilizes spaCy to rectify spelling errors in both queries and documents. Corrected and original queries are printed for user insight.
Tokenization: Words are extracted from documents using spaCy.
Vocabulary Generation:
Filters out infrequent (less than 5 documents) and overly frequent (more than 85% of documents) words, creating a tailored vocabulary for the task.
TF-IDF vectors are computed for each document and query (may or may not involve scikit-learn).
## 2. Initial Retrieval and Evaluation:

Cosine Similarity: For each query, its TF-IDF vector is compared with document vectors using cosine similarity.
Top-k Retrieval: Retrieval of the top 5 and top 10 most similar documents for each query.
Evaluation: Precision@k scores (P@1, P@5, P@10) are calculated to assess retrieval accuracy, averaged across all queries.
Performance Improvement:

## 3. Stemming: Exploration of stemming's impact on vocabulary size and retrieval performance (Task 2.1).
Lemmatization: Examination of lemmatization's influence on vocabulary size and retrieval performance (Task 2.2).
Vocabulary Size Comparisons: Reporting on the sizes of the original vocabulary, stemmed vocabulary, and lemmatized vocabulary (Task 2.3).
Performance Discussion: Analysis of whether stemming or lemmatization improves retrieval accuracy and the reasons behind the observed results (Task 2.4).

## 4. Advanced Techniques and Evaluation:

NER and POS Tagging: Integration of spaCy for named entity recognition (NER) and parts-of-speech (POS) tagging (Task 3.1).
Weighted TF-IDF: Assigning higher weights to nouns (multiplier of 2) and named entities (multiplier of 4) within TF-IDF vectors for increased emphasis (Task 3.2).
Evaluation with Weighted TF-IDF: Reporting on retrieval performance metrics using weighted TF-IDF vectors and analyzing the results (Task 3.3).
Efficiency and Performance Improvements (Optional): Optional explorations to enhance efficiency or performance, including details about the changes and their motivations (Task 4).

# Project Structure:

The project is likely to be organized into modules/scripts for various tasks:
Data preprocessing and cleaning.
Vocabulary generation.
TF-IDF vectorization.
Cosine similarity calculation.
Retrieval and evaluation.
Performance improvement techniques (stemming, lemmatization, NER, POS tagging, weighted TF-IDF).
Optional efficiency/performance optimizations (Task 4).


## Retrieval Performance on Quora Dataset

| Task | Technique | Avg Precision@1 | Avg Precision@5 | Avg Precision@10 |
|---|---|---|---|---|
| Task 1 | Baseline (TF-IDF) | 0.48 | 0.74 | 0.77 |
| Task 2 | Stemming | 0.57 | 0.81 | 0.83 |
| Task 2 | Lemmatization | 0.34 | 0.56 | 0.64 |
| Task 3 | POS Tagging | 0.35 | 0.55 | 0.59 |
| Task 4 | Stemming & Lemmatization | 0.57 | 0.82 | 0.83 |
