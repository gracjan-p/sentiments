# Twitter Sentiment Analysis Project

This project focuses on cleaning, analyzing a dataset, and comparing different algorithms for natural language processing. The dataset used is 'Twitter posts data' from Kaggle, which contains a variety of casual expressions, making it suitable for sentiment analysis.

## Process Overview

The project includes the following steps:

1. Data overview and analysis
2. Data cleaning and preprocessing
3. Building and evaluating AI models

## Libraries Used

- Pandas
- Seaborn
- SciKit Learn
- NLTK

## Data Overview

The dataset is divided into training, testing, and validation sets:
- `train.csv`
- `test.csv`
- `val.csv`

These are combined into a single DataFrame for processing. A preview of the data and class distribution is provided using Seaborn for visualization.

## Data Cleaning and Preprocessing

### Dropping Outliers and Duplicates

- Calculate the length of each tweet.
- Remove tweets with lengths exceeding a threshold.
- Remove duplicate tweets.

### Downsizing Classes

The dataset is downsampled to balance the classes by taking the size of the smallest class and applying it to the rest.

### Custom Tokenizer

A custom tokenizer is built using NLTK to:
- Convert emojis to words.
- Remove mentions (@).
- Replace common abbreviations with full words.
- Apply stemming.

## Building AI Models

Two models are built and compared:
1. Complement Naive Bayes (CNB)
2. Stochastic Gradient Descent (SGD)

These models are evaluated using the original and downsampled datasets.

### Model Pipelines

- CountVectorizer with custom tokenizer
- ComplementNB
- SGDClassifier

### Model Evaluation

Models are evaluated using:
- Classification Report
- Confusion Matrix
- F1 Score

### Practical Testing

The models are tested on new sentences to evaluate their practical performance.

## Hyperparameter Optimization

A RandomizedSearchCV is used to optimize the hyperparameters of the SGDClassifier.

## Results

Both models are compared in terms of accuracy and F1 score. The Complement Naive Bayes model generally performs better with downsampled data, while SGD shows promising results with further hyperparameter tuning.

## Conclusion

Despite the raw and casual nature of the dataset, it is possible to create a sentiment classifier. However, the effectiveness of the classifier depends on the complexity of the sentence structure and context.

## Instructions for Running the Project

1. Ensure you have the required libraries installed:
   ```bash
   pip install pandas seaborn scikit-learn nltk
