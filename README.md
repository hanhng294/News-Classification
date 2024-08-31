# News classification 
Classify news categories based on titles
language: python
packages: pandas, matplotlib, string, nltk, wordcloud, keras, sklearn, tensorflow
data: https://www.kaggle.com/datasets/uciml/news-aggregator-dataset

- Introduction
- Dataset information
- EDA and Visualizations
- Text preprocessing
- Machine Learning model

## Introduction

News title classification has an important application in automation, user experience, 
and recommendation system. 
The aim of this project is to build predictive model that label categories based on title content.
This is a part of text classification where deep learning model LSTM is a good candidate for predictive model.

## Dataset information
- CATEGORY : the category of the news item; one of:
-- b : business
-- t : science and technology
-- e : entertainment
-- m : health
- Title: headline of articles
the dataset also has URL, publisher, story, hostname, timestamp. However, for the purpose of this study we only focus on CATEGORY and TITLE

## EDA and Visualization:
- For EDA, we used a combinations of plots and word cloud to examine distributions and some common instances.
For more information please go to: [*Report.pdf*](https://github.com/hanhng294/News-Classification/blob/main/report.pdf)

## Text processsing:
In order for machine learning model to learn from training data, the text attributes need to be converted to integers.
This include a variation of methods for text handling: lowercasing, removing punctuations and stop words, lemmantizing before
converting to integers (tokenization, sequencing, padding). Through the tokenizing process we only keep 30,000 most common
words out of 69,293 for time efficiency
For more details: [*Report.pdf*](https://github.com/hanhng294/News-Classification/blob/main/report.pdf)

## Machine Learning model:
The data is split into 80% train set and 20% test set, stratifying according to category to ensure equal distribution
(as there is existing imbalance in distributions among categories)
LSTM is compiled with loss as categorical crossentropy due to the classification problem, the metrics is accuracy.
We achieved roughly 0.95 for train set and 0.9 for validation set 
