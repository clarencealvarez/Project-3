# Project 3: Web APIs & NLP

![](https://logos-world.net/wp-content/uploads/2020/10/Reddit-Logo-2005-present.png)

## Problem Statement

In this project, I compare the performance of three classifier models on predicting which of two subreddits a random post belongs to. This project requires the use of natural language processing to breakdown the posts for use in the models.

The three models used are K-Nearest-Neighbors, Random Forest Classifier, and Multinomial Naive Bayes.

The metrics for success in this project will be the accuracies of the models in predicting subreddits against the null model.

## Data

Data for this project was retrieved from the ([twitch](https://www.reddit.com/r/Twitch/)) and ([youtube](https://www.reddit.com/r/Youtube/)) subreddits. 10,000 unique posts, posted up to November 3rd, 2021, were retrieved for cleaning. The only predictor variable used was the `'selftext'` column, which contains the body of the post. After transformations, the full dataframe contained 18,753 observations with 34,031 features. Features included one-, two-, and three-word phrases found in the body of the post.

## Analysis

Below is a table of the accuracies of the models. All performed better than the null model. K-Nearest Neighbors showed the biggest degree of overfitting (predicting better on the training data than the validation data), whereas the differences for Random Forest Classifier and Multinomial Naive Bayes were only a few percentages.

|Model|Accuracy|
|---|---|
|K-Nearest Neighbors|88%|
|Random Forest Classifier|91%|
|Multinomial Naive Bayes|91%|

## Conclusion & Recommendation

In selecting a model to best predict whether a random post belongs to the twitch or youtube subreddit, I recommend choosing the Random Forest Classifier model. The reason for this is two-fold:

1. It performed better than the KNN classifier, with a lower degree of overfittedness.
2. It had virtually the same accuracy on the validation data as the Multinomial Naive Bayes model, but also includes the option of further analyzing the most important words and phrases that contributed to predictions. In general, I believe this option gives users more value than a minute increase in accuracy or reduction in overfittedness.

The table of feature importances can be found [here](./data/rfc_gs_fi.csv).