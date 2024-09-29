# Naive Bayes Classifier Implementation

This document outlines the implementation of a Naive Bayes classifier using a dataset that predicts whether to play tennis based on various weather features. We will also delve into the mathematical concepts underpinning the Naive Bayes algorithm.

## Table of Contents
1. [Introduction to Naive Bayes](#introduction-to-naive-bayes)
2. [Mathematical Foundation](#mathematical-foundation)
3. [Implementation Steps](#implementation-steps)
   - [1. Import Libraries](#1-import-libraries)
   - [2. Load the Dataset](#2-load-the-dataset)
   - [3. Split the Dataset](#3-split-the-dataset)
   - [4. Initialize Parameters](#4-initialize-parameters)
   - [5. Calculate Class Priors](#5-calculate-class-priors)
   - [6. Calculate Prior Probabilities](#6-calculate-prior-probabilities)
   - [7. Calculate Likelihoods](#7-calculate-likelihoods)
   - [8. Calculate Posterior Probability](#8-calculate-posterior-probability)
   - [9. Determine the Final Prediction](#9-determine-the-final-prediction)
4. [Conclusion](#conclusion)
5. [Author Information](#author-information)

## Introduction to Naive Bayes

Naive Bayes is a family of probabilistic algorithms based on Bayes' Theorem, primarily used for classification tasks. It operates under the assumption of feature independence, which simplifies the computation of probabilities.

## Mathematical Foundation

The Naive Bayes algorithm applies Bayes' Theorem, which is defined as:

\[
P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)}
\]

Where:
- \(P(A|B)\) is the **posterior probability**: the probability of class \(A\) given the feature \(B\).
- \(P(B|A)\) is the **likelihood**: the probability of feature \(B\) given class \(A\).
- \(P(A)\) is the **prior probability**: the initial probability of class \(A\) before seeing the feature.
- \(P(B)\) is the **evidence**: the total probability of feature \(B\).

In the context of Naive Bayes for a given feature vector \(X = (x_1, x_2, \ldots, x_n)\), the posterior probability for a class \(C\) is computed as:

\[
P(C|X) \propto P(C) \cdot P(X|C) = P(C) \cdot P(x_1|C) \cdot P(x_2|C) \cdots P(x_n|C)
\]

The assumption of independence allows us to multiply the individual likelihoods of each feature given the class.

## Implementation Steps

### 1. Import Libraries

First, we import the necessary libraries to handle data manipulation and numerical operations.

### 2. Load the Dataset

The dataset containing weather information and the target variable indicating whether to play tennis is loaded.

### 3. Split the Dataset

The dataset is separated into features (`X`) and the target variable (`y`).

### 4. Initialize Parameters

We determine the training size and the number of features. Dictionaries are initialized to store:
- **Likelihoods**: Probabilities of feature values given each outcome.
- **Class Priors**: Prior probabilities of each class (Yes or No).
- **Prior Probabilities of Features**: Probabilities of each feature value across all instances.

### 5. Calculate Class Priors

For each unique outcome in `y`, we count the occurrences and update the `class_prior` dictionary.

### 6. Calculate Prior Probabilities

We iterate through each feature and calculate the prior probability for each unique feature value, updating the `pred_priors` dictionary.

### 7. Calculate Likelihoods

For each feature and each outcome, we calculate the likelihood of each feature value occurring given the outcome and update the `likelihoods` dictionary.

### 8. Calculate Posterior Probability

To predict for a new instance, we calculate the posterior probabilities for each outcome using Bayes' theorem.

### 9. Determine the Final Prediction

Finally, we find the outcome with the highest posterior probability, indicating whether to play tennis based on the given weather conditions.

## Conclusion

This implementation of the Naive Bayes classifier demonstrates the application of Bayes' theorem in a practical scenario. By leveraging the assumption of independence among features, we can efficiently calculate the probabilities needed for classification tasks. This method is particularly effective for datasets with categorical features, making it widely used in text classification and spam detection.

If you have any questions or would like further clarifications on any part of this implementation, feel free to ask!

## Author Information

This Naive Bayes classifier implementation was created by **Syed Mansoor ul Hassan Bukhari**.

- **GitHub**: [CyberFantics](https://github.com/CyberFantics)
- **LinkedIn**: [Mansoor Bukhari](https://www.linkedin.com/in/mansoor-bukhari-77549a264/)
- **Email**: digital.creator380@gmail.com
