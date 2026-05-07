# Autonomous-Tagging-for-Stack-Overflow-Questions

## Overview
This project focuses on building an automated tagging system for Stack Overflow questions using Machine Learning techniques. The system predicts relevant tags for a question based on its title and body text.

The problem is treated as a **multi-label text classification** task because a single question can belong to multiple tags simultaneously.

Example:

Question:
"How to create a REST API using Flask?"

Predicted Tags:
`python`, `flask`, `rest-api`

---

# Problem Statement
Automatically predict relevant tags for Stack Overflow questions using textual content from the question title and body.

The goal is to improve:
- Content organization
- Search efficiency
- Discoverability of relevant discussions
- User experience on developer platforms

---

# Objectives
- Build an automated tagging system
- Handle multi-label classification effectively
- Compare different classical ML models
- Evaluate models using suitable metrics

---

# Dataset Description

## Input Features
- Question Title
- Question Body

## Output Labels
- Tags

## Dataset Characteristics
- High-dimensional textual data
- Sparse feature representation after vectorization
- Multiple tags per question

---

# System Architecture

## Pipeline Overview
1. Data Loading
2. Merge Questions & Tags Dataset
3. Filter Top 100 Most Frequent Tags
4. Text Cleaning
5. Data Filtering
6. Feature Extraction using TF-IDF
7. Label Encoding using MultiLabelBinarizer
8. Train-Test Split
9. Model Training
10. Predict Relevant Tags

---

# Data Preprocessing

The following preprocessing steps were applied:

- Merged multiple tags for each question
- Merged Questions and Tags datasets using Question ID
- Removed HTML tags
- Removed stopwords
- Filtered top 100 most frequent tags
- Removed entries with negative scores
- Removed outliers with scores greater than 500

These steps helped improve data quality and reduce noise.

---

# Feature Engineering

## TF-IDF Vectorization
Text data was converted into numerical vectors using TF-IDF (Term Frequency–Inverse Document Frequency).

### Benefits
- Captures importance of words
- Converts text into sparse numerical representation
- Reduces effect of less informative frequent words


max_features = 1000
min_df = 0.0
max_df = 1.0
