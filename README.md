Sequential Sentence Classification
Objective: Building a Deep Learning Model for Sequential Sentence Classification, to convert “Harder to Read” text into “Easier to Read” text.

Dataset Details
The PubMed 20k RCT dataset is based on PubMed for sequential sentence classification. The dataset consists of approximately 20,000 abstracts of randomized controlled trials. Each sentence of each abstract is labeled with its role in the abstract using one of the following classes: background, objective, method, result, or conclusion. This dataset aims to enhance tools for efficiently skimming through literature, particularly in the medical field.

Sample Abstracts

Dataset Analysis
Fig 1: Distribution of Sentences per Abstract

Fig 2: Distribution of Number of Tokens in a Sentence

Fig 3: Distribution of Character Sequence Lengths

Table 1: Dataset Overview

|V| represents the vocabulary size.
The training, validation, and test sets are detailed with the number of abstracts and sentences.
Distribution Insights:

Fig 1: Most abstracts have between 7 to 15 sentences.
Fig 2: Majority of tokens per sentence range between 0 to 55.
Fig 3: Most character sequences are between 0 to 200 characters long.
Fig 4: Number of Sentences per Label in Train, Test, and Validation Sets

Performance Benchmarks
Experiments Conducted:
Naïve Bayes with TF-IDF Encoder (Baseline Model)
Conv1D with Token Embedding
Pretrained Feature Extractor (Using Universal Sentence Encoder)
Conv1D with Character Encoding
Fig 5: Bar Chart Comparison on Validation Set for Model Metrics

Naïve Bayes with TF-IDF Encoder: Uses TF-IDF to convert sentences to numbers and MultinomialNB for classification.
Conv1D with Token Embedding: Converts text inputs into numerical sequences using token embedding and applies a 1D Convolution layer.
Pretrained Feature Extractor (USE): Uses Universal Sentence Encoder for tokenization and convolution layer.
Conv1D with Character Encoding: Splits sequences into characters, creates feature vectors for each character, and applies character embedding layer.
Table 2: Model Metrics for Different Models on Validation Dataset

Conv1D with Token Embedding consistently outperforms other models with higher accuracy (82.45), precision (82.22), recall (82.45), and F1 score (82.15).
Fig 6: Bar Chart Comparison on Test Set for Model Metrics

Table 3: Model Metrics for Different Models on Test Dataset

Conv1D with Token Embedding is the top performer in the test set as well.
Fig 7: F1 Score Comparison on Validation Set for Different Models

Fig 8: F1 Score Comparison on Test Set for Different Models

Conv1D with Token Embedding shows the highest F1 score, indicating strong performance in both validation and test sets.
Fig 9: Confusion Matrix for Best Performing Model (Conv1D with Token Embedding)

Table 4: Classification Metrics for Conv1D with Token Embedding Model

Observations:

The model excels in classifying Conclusions, Methods, and Results.
Challenges in distinguishing Background and Objective may be due to fewer samples and potential similarities in embeddings.
Fig 10: Most 50 Inaccurate Predictions

Top 50 Inaccurate Predictions: Highlights instances where the model struggles, potentially due to dataset biases or sample imbalances.

Conclusion
1. Conv1D with Token Embedding is the best-performing model on both validation and test datasets.
2. Challenges include distinguishing Background and Objective categories, potentially due to sample size and embedding similarities.
3. The confusion matrix supports these findings, with notable confusion between Background and Objective classes, and consistent behavior in Methods and Results classes.

