# Song Lyrics Genre Classification Project

## Overview

This project is divided into two notebooks, each focusing on different approaches to classify song lyrics by genre.

### Notebook 1: Classification with Different Models

In this notebook, we aimed to test various approaches to classify song lyrics by genres. We conducted three independent experiments, training and testing different models on different subsets of the same dataset.

#### Dataset

The dataset consisted of song lyrics labeled by genres that we identified as having the least in common with each other (see EDA for details).

#### Experiment 1: Transformer with Unbalanced Data
- **Model**: Transformer
- **Data**: Unbalanced (different numbers of texts per genre)
- **Accuracy**: 93.5%
- **Observation**: The high accuracy might be due to the unbalanced data. Testing with balanced data would be interesting to see if the Transformer model performs similarly.

#### Experiment 2: LSTM with Downsampled Data
- **Model**: LSTM
- **Data**: Downsampled (1063 texts per genre)
- **Accuracy**: 78.03%

#### Experiment 3: Random Forest
- **Model**: Random Forest
- **Data**: 
  - Unbalanced: 88.6% accuracy
  - Balanced: 85.9% accuracy
- **Observation**: The decrease in accuracy with balanced data suggests that the Transformer model might also lose accuracy with balanced data.

#### Conclusion
We successfully classified song lyrics by genre using various methods and learned a lot about different Natural Language Processing (NLP) techniques.

### Notebook 2: Graph Neural Networks and Similarity Measures

In this notebook, we tested Graph Neural Networks (GNNs) using TF-IDF and cosine similarity with different thresholds, and implemented K-Nearest Neighbors (KNN) in Graph Convolutional Networks (GCNs).

#### Experiment 1: TF-IDF x Cosine Similarity - Threshold Testing
- **Thresholds and Accuracies**:
  - Threshold: 0.5 - Accuracy: 23.5%
  - Threshold: 0.1 - Accuracy: 23.4%
  - Threshold: 0.001 - Accuracy: 23.38%

#### Experiment 2: KNN in GCN
- **Process**:
  1. Extract TF-IDF features
  2. Calculate 5-KNN
  3. Create a graph
- **Accuracy**: 74.85%

#### Experiment 3: Top K Similarities using Cosine Similarity in GCN
- **Process**:
  1. TF-IDF vectorization
  2. Calculate top 5 similarities with cosine similarity
  3. Create a graph
- **Accuracy**: 70.62%

#### Experiment 4: BERT Base Uncased Embeddings with GCN
- **Process**:
  1. BERT Embeddings
  2. Adjacency Matrix - top K cosine similarities
- **Advantages of BERT**:
  - Context-aware
  - Considers the sequence of words
  - Pre-trained knowledge
  - Long-range dependencies
  - Extensive attention mechanism
  - Versatile across various domains
  - Easily adaptable
  - Robust against polysemy
- **Accuracy**: 85.55% (20 epochs)

#### Experiment 5: GAT (Graph Attention Networks) vs GCN
- **GAT**:
  - Requires more computational power
  - Provides more interpretability
  - Accuracy: 84.84% (20 epochs)

#### GCNs vs GATs
- **Observations**:
  - Smaller dataset
  - Missing importance
  - Attention mechanism of GATs not significant in this context
  - Cosine similarity metric not well-suited for GATs

## Conclusion
Through these experiments, we explored various methods to classify song lyrics by genre, comparing traditional models with advanced neural network approaches. Each method provided unique insights and performance metrics, contributing to our understanding of NLP techniques in genre classification.

You can find the data here: https://drive.google.com/drive/folders/1FinCic9UHYrJOJPSlZD9pLFWnlzvlp7d?usp=drive_link
