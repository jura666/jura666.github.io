---
layout: 	FUNCTION OF MACHINE LEARNING
title: BLACK BOX MACHINE LEARNING
date: 2018-07-17 00:08:30
tags: ML
---
## What is Machine Learning for?
Common theme is to solve a prediction problem:
>give an input x,
>predict an 'appropriate' output y.

### Example 1:Spam Detection:
>Input: Incoming email
>Output: 'SPAM' or 'NOT SPAM'

A binary classification problem, because only 2 possible outputs.

### Example 2:Medical Diagnosis
>Input: Symptoms(fever, cough, fast, breathing, shaking, nausea(恶心))
>Output: Diagnosis(Pneumonia（肺炎）, flu, common cold, bronchitis(支气管炎)...)

A multiclass classification problem: choosing one of several [discrete] outputs.

#### How to express uncertainty?
Probabilistic classification or, soft classification:

  p(pneumonia) = 0.7

  p(flu) = 0.2

  ...


### Example: Predicting a Stock Price
>Input: History of stocks prices
>Output: Predict stock's price at close of next day.

A regression problem: because the output is number.

(Regression is not just 'linear regression' from basic statistic.)


### Rule-Based Approach

![Rule-Based Approach](https://i.imgur.com/lJbiHk4.png)

Issues with rule-based systems:

- Very labor intensive to build
- Rules work very well for areas they cover
	- but cannot generalize to unanticipated input combinations
- Don't naturally handle uncertainty.

### Learning from trained data of this form is called supervised learning

#### A machine Learning algorithm:
- Input: Training data
- 'Learns' from the training data
-  Output: A 'prediction function' that produces output y given input x.

### Machine Learning Approach:
![MLApproach](https://i.imgur.com/bo8wAQh.png)

#### Most common ML problem types:
- Classification
- Multiclass
- regression

- Prediction function
	- prediction output y given input x
- training data 
	- a set of(input x, output y) pairs
- supervised learning algorithm
	- takes training data and produces prediction function

## Feature Extraction
### Definition:
Mapping raw input x to Rd is called feature extraction or featurization.  

