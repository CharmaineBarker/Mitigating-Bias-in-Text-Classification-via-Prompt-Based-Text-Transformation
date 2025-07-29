# Mitigating Bias in Text Classification via Prompt-Based Text Transformation
Code, datasets, and models for the paper "Mitigating Bias in Text Classification via Prompt-Based Text Transformation"

This is the work for the paper submitted to RANLP 2025. We generated a dataset of Dinseyland reviews simplified using different prompts, and that is released here. The code used for model building and evaluation, as well as McNemar's Test.

The sample of reviews was taken from a Kaggle dataset here [Disneyland Reviews](https://www.kaggle.com/datasets/arushchillar/disneyland-reviews). Each review was summarised by [ChatGPT](https://chat.openai.com/) using the 3.5-turbo model. The dataset is released here as [DinseylandReviews](DinseylandReviews.csv), and it contains the following features:

* `reviewID`- The ID of the original review, retained from the original Disneyland dataset for reproducibility.
* `rating`- The 1-5 star rating given by the reviewer, preserved in this dataset for evauluation of sentiment retention.
* `branch`- The Disneyland branch the review was discussing.
* `reviewerLocation`- The country of origin of the reviewer, used here as the protected attribute.
* `rawText`- The original raw review text.
* `nerText`- The review after being processed by NER-based anonymisation
* `simpleText`- The version of the review outputted when the model was prompted with "Simplify this text in 50 tokens or less".
* `removedText`- The version of the review outputted when the model was prompted with "Remove author nationality cues and use globally neutral English without idioms or slang in 50 tokens or less".
* `englishText`- The version of the review outputted when the model was prompted with "Make this sound like it was written by an Englishman in 50 tokens or less".
* `formalText`- The version of the review outputted when the model was prompted with "Rephrase this for a professional audience using formal language in 50 tokens or less".

A number of tests were completed on this data such as sentiment analysis to check the reviews kept the same meaning and classification of the reviews by the protected characteristic. The code used for model training and evaluation is seen in [DisneyDataModels](DisneyDataModels.ipynb). Text was preprocessed, and five machine learning models were used- Naïve Bayes, Logistic Regression, Support Vector Classifier, Random Forest, and XGBoost. Word Importance was also assessed within this notebook. The statistical tests were performed using the code seen in [DisneyDataMcNemarsTest](DisneyDataMcNemarsTest.ipynb). Code for importing of datasets and results dictionaries has been removed for anonymity.

Our Generated Dataset License: CC BY-NC-SA
